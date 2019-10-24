## Welcome

Hi. My name is Michał. I am passionate Java Developer eager to constantly expand his programming knowledge. Huge fan of functional programming, test-driven development and clean code.

In this blog, I am going post and explain variety of Java (and not only) interview questions.

## 1. What is the best way to implement Singleton pattern in Java?

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

More real-life example:

```java

public enum ObjectMapperSingleton {

  INSTANCE;

  private ObjectMapper objectMapper;

  ObjectMapperSingleton() {
    objectMapper = new ObjectMapper();
  }

  public ObjectMapper get() {
    return objectMapper;
  }

  public static void main(String[] args) {

    ObjectMapper firstObjectMapper = ObjectMapperSingleton.INSTANCE.get();
    ObjectMapper secondObjectMapper = ObjectMapperSingleton.INSTANCE.get();

    System.out.println(firstObjectMapper == secondObjectMapper);
  }
}

```

Note that only creation of `ObjectMapperSingleton` object is thread-safe. Thread-safety of exposed methods, has to 
be handled explicitly by the developer. 
