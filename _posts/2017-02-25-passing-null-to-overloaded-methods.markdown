---
layout: post
title:  "Passing null to overloaded methods"
date:   2017-02-25 21:00 +0200
comments: true
img: java-logo.jpg
tags: [java]
---
Assume we have an overloaded method that looks like this:

```java
public String retrieveValue(String text) {
    return text;
}

public int retrieveValue(int number) {
    return number;
}
```

Pretty nice overloading, eh?! What could go wrong, for retrieveValue(null) method? In the above code, nothing, because the method with the String signature will be invoked, as the one with the int signature is just of type primitive, so, it’s almost obvious for the compiler.

**However**, can you imagine what would happen, if the second method accepted an argument of [Integer](http://docs.oracle.com/javase/7/docs/api/java/lang/Integer.html?is-external=true)?
```java
public String retrieveValue(String text) {
    return text;
}

public int retrieveValue(Integer number) {
    return number;
}
```

Integer is the wrapper class of int and what generally stands for the wrapper classes of primitives is that they can also accept null values. So, calling **retrieveValue(null)** in this case will just confuse the compiler, ‘cuz it’s just ambiguous for him which method to pick up, since both of them can accept a null value argument.

Therefore, there will be a compilation error of:

```
Ambiguous method call. Both
retrieveValue (String) in TestClass and
retrieveValue (Integer) in TestClass match
```
Cheers!

