## Welcome

Hi. My name is Michał. I am passionate Java Developer eager to constantly expand his programming knowledge. Huge fan of functional programming, test-driven development and clean code.

In this blog, I am going post and explain variety of Java (and not only) interview questions.

## 1 What is the best way to implement Singleton pattern in Java?

The best way to implement Singleton pattern in Java is to use `Enum`. 

```java

public enum SingletonExample { INSTANCE }

```

### Pros:
* easy to implement
* out-of-the-box serialization
* thread-safe

### Cons:
* does not support lazy initialization
