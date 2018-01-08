---
layout: post
title:  "Difference between Iterable and Iterator in Java?"
date:   2018-01-08 01:00 +0200
comments: true
tags: [java, iterable, iterator]
img: java-logo.jpg
---

### 0. Introduction
At a very first glance, those two classes, [`Iterable`](https://docs.oracle.com/javase/7/docs/api/java/lang/Iterable.html) and [`Iterator`](https://docs.oracle.com/javase/7/docs/api/java/util/Iterator.html) seem to be invented and used for the same purpose, without any crucial difference between them. However, if one dives a bit more into them, they understand the reasoning behind having two separate classes for iterating over a collection of objects.

### 1. History & Meta

- `Iterable` exists is [`java.lang`](https://docs.oracle.com/javase/7/docs/api/java/lang/package-summary.html) package, since JDK 1.5
- `Iterator` comes from the [`java.util`](https://docs.oracle.com/javase/7/docs/api/java/util/package-summary.html) package, since JDK 1.2 and was actually introduced as the successor of [`Enumeration`](https://docs.oracle.com/javase/7/docs/api/java/util/Enumeration.html) interface.

### 2. In-short
Actually, the names of the interfaces already explain their scope.
So, a class which implements the Iterable interface is iterable and the way to iterate over its elements is by using an Iterator object.

### 3. In-depth
What is in-practice accomplished using the `Iterable` interface is the usage of the foreach loop, which means that a class that implements the `Iterable` interface can be used in a foreach loop.

`Iterable` interface defines only one method, `Iterator<T> iterator()`, which returns an `Iterator` over a set of elements of type `T`.
So, we need to override that method when it is about a **custom implementation**.

### 4. Examples
Have you noticed the fore-mentioned text in bold?
Yes, there are some cases, where everything is provided out of the box for us and we can directly use a foreach loop to iterate over a collection of objects, without bothering about the Iterable, Iterator interfaces and the required overriding that needs to happen.

Does this already ring a bell?
Let's have a look at a very small example made-out of the Java docs.

### 4.1 JavaDoc example
The very best example to begin with cannot be anything else other than something taken from the java docs with a bit of salt and pepper.

```java
List<String> employees = Arrays.asList(new String[] {"John", "Mary", "Thodoris"});
for (String employee : employees) {
    System.out.println(employee);
}
```

The above has no need to worry about these two interfaces, since [`List<E>`](https://docs.oracle.com/javase/7/docs/api/java/util/List.html) is already an Iterable, because:

- List<E> IS-A [`Collection<E>`](https://docs.oracle.com/javase/7/docs/api/java/util/Collection.html)
- `Collection<E>` extends `Iterable<E>`

### 4.1.1 Digging into the Javadocs
Wait. That said, `List<E>` should override `Iterator<T> iterator()` method. Indeed [it does](https://docs.oracle.com/javase/7/docs/api/java/util/List.html#iterator()), but `List` is just an interface, so, we will not see any actual implementation over there.
Let's have a look at the most common implementation of a `List`, the [`ArrayList`](https://docs.oracle.com/javase/7/docs/api/java/util/ArrayList.html):

![first]({{site.baseurl}}/assets/img/08-01-18/1.png)

Ok, cool, so, in `Itr()` we expect to see the overriding of the `Iterator<E>` methods, aren't we?

![second]({{site.baseurl}}/assets/img/08-01-18/2.png)

Yyyyes! That's it.
So, as you see, for most of the cases, we don't have to do anything special.

### 4.2 Custom Implementation
What happens when we want to create our own custom logic for an `Iterable<T>`?

- Create a class that extends `Iterable<T>`
- Override `Iterator<E> iterator()` method of that class

And you're ready to use it in a foreach statement.

_`MyIterable.java`_

```java
public class MyIterable<T> implements Iterable<T> {

    T[] t = null;
    int count;

    public MyIterable(T[] t) {
        this.t = t;
    }

    @Override
    public Iterator<T> iterator() {

        return new Iterator<T>() {
            @Override
            public boolean hasNext() {
                return count != t.length; // the fun part!
            }

            @Override
            public T next() {
                System.out.println("Calling next() method...");
                return t[count++];
            }

            @Override
            public void remove() {
                throw new UnsupportedOperationException();
            }
        };
    }
}
```

Our main class:

```java
public static void main(String[] args) {
    Integer[] ids = {100, 4, 333};
    MyIterable<Integer> entries = new MyIterable<>(ids);
    for (Integer id : entries) {
        System.out.println(id);
    }
}
```

The above will print the following:

```
Calling next() method...
100
Calling next() method...
4
Calling next() method...
333
```
### 5. TIL
Apparently, there shouldn't be a "Today I Learned" section in a blog post, since it is obvious that in order to write something up, you either learned it for the first or [the second time](https://twitter.com/ThodorisBais/status/950213240340000768).
Here is what I learned today, regarding operators.

> We can use the `!=` operator instead of `<` whenever it is about to return a boolean value.

### 6. Closing thoughts
Isn't it fun that during a study on the fore-mentioned interfaces I also learned about a new usage of the `!=` operator?
It's not the first time this happens.
My little experience in this crazy software industry proves that it happens every single time: you start from topic A and hop to hop to hop...you end up reading about topic Z.
Sometimes it is required to have some filtering on, though.
Otherwise you end up waisting one more night of sleep, like I just did right now :simple_smile: .

What do you think? Let me know in the comments.