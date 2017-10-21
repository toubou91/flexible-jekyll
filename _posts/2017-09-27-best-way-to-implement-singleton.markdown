---
layout: post
title:  "The best way to implement a Singleton"
date:   2017-09-27 22:40 +0200
comments: true
tags: [design-patterns, java]
---
OWH. MY. GOD.

The more I study about OCPJP, the more I make clear how stranger I am to this language.

Guys, herewith I share with you the code-snippet:

```java
public enum Employee {
    INSTANCE;
}
```

Owh, sorry, April’s fool in September, that wasn’t a code snippet, it was an implementation of the [Singleton](https://www.tutorialspoint.com/design_pattern/singleton_pattern.htm) pattern.

Below you can read Joshua’s Block view about this, from his [Effective Java](https://www.amazon.com/Effective-Java-2nd-Joshua-Bloch/dp/0321356683) book:

_This approach is functionally equivalent to the public field approach, except that it is more concise, provides the serialization machinery for free, and provides an ironclad guarantee against multiple instantiation, even in the face of sophisticated serialization or reflection attacks. While this approach has yet to be widely adopted, a single-element enum type is the best way to implement a singleton._
