Java 

# Self-Introduction

Hi, my name is Yang Li. I’m a full stack software engineer based in San Jose, with a strong focus on Java, Spring Boot, and React. My background is in building scalable microservices and cloud-native applications for both B2B and B2C scenarios.  
In my most recent roles, I’ve developed RESTful APIs, built event-driven architectures, and containerized deployments on AWS, always with an eye toward reliability and performance.  
I enjoy collaborating in Agile teams and always strive to deliver clean, maintainable code that drives business results. Outside of work, I’m passionate about learning new tech stacks and solving real-world problems through automation.

---

# Likely Resume Deep-Dive (简历拷打) Questions & Excellent Answers

---

## 1. **Q: Can you walk me through a recent project where you used microservices architecture? What challenges did you face and how did you overcome them?**

**A:**  
Absolutely. At Signal Electronic Maintenance LLC, I led the design of a microservices architecture for our retail platform, deploying over 15 Spring Boot services on AWS ECS. One of the biggest challenges was real-time data consistency, especially for inventory and order processing.  
To solve this, I implemented an event-driven approach using Apache Kafka, which let services communicate asynchronously and ensured reliable updates. We also had to coordinate schema evolution, so I introduced Avro for message serialization, making versioning easier.  
Another challenge was securing our endpoints for different user roles. I set up OAuth2 and JWT-based authentication, and fine-grained access control with Spring Security. These steps helped the team scale the system without running into bottlenecks or security gaps.

---

## 2. **Q: Your resume mentions optimizing Oracle 19c database performance. Can you elaborate on what you did and the impact?**

**A:**  
Sure! The original API response times were slow due to inefficient queries and table scans. I started by profiling slow queries and added custom indexing and materialized views for commonly accessed data.  
I also rewrote some business-critical queries in PL/SQL to handle more logic within the database, reducing round trips. As a result, we brought the average API latency down from 950ms to 180ms—about an 81% improvement. This had a direct impact on user experience and system scalability.

---

## 3. **Q: Tell me about a time you improved infrastructure costs using cloud or DevOps tools.**

**A:**  
At Aivres Systems, I containerized several applications using Docker and moved our deployment pipeline onto AWS EKS. By leveraging managed services like S3 for storage and DocumentDB for NoSQL, we reduced manual maintenance and infrastructure overhead.  
Automating our CI/CD with Jenkins helped us catch issues early and speed up delivery. Overall, these efforts cut our infrastructure costs by roughly 35% and gave us more predictable deployments.

---

## 4. **Q: How do you ensure code quality and reliability in your teams?**

**A:**  
I’m a strong believer in testing and code reviews. I usually set up comprehensive unit and integration tests—on my last team, we reached 85% code coverage using JUnit and Mockito.  
I also advocate for peer code reviews with Git, which helps catch bugs early and spreads best practices. In Agile sprints, I like to work closely with QA to ensure acceptance criteria are testable and well-defined.

---

## 5. **Q: Can you give an example of using event-driven design in your experience?**

**A:**  
Of course. In the Signal retail project, we used Apache Kafka to decouple order processing, inventory updates, and customer notifications.  
For instance, when an order is placed, the order service publishes an event to a Kafka topic. Other microservices—like inventory or notification—consume these events and react accordingly. This pattern let us build scalable, loosely coupled services, and made it easier to add new features without touching existing code.

---

## 6. **Q: What’s your approach to building secure web applications?**

**A:**  
I always start by implementing robust authentication and authorization. For example, I use OAuth2 and JWT for stateless authentication and Spring Security for access control.  
I also make sure to follow best practices like encrypting sensitive data, validating user inputs, and regularly updating dependencies. Security isn’t just a checklist—it’s something I try to build into every layer from the start.

---

## 7. **Q: How do you keep up with new technologies or frameworks?**

**A:**  
I’m pretty proactive—whether it’s reading tech blogs, taking online courses, or working on side projects. I also like to participate in code reviews or open-source contributions to see different approaches.  
For example, I recently experimented with GraphQL integrations in React and backend services, which gave me a broader view beyond just REST APIs.

---

## 8. **Q: Describe a time you worked with a cross-functional team.**

**A:**  
At both Aivres and Signal, I collaborated with product managers, designers, and DevOps engineers. In Agile sprints, I’d participate in stand-ups and planning, help clarify requirements, and pair with frontend or DevOps team members to deliver features end-to-end.  
I find that good communication and willingness to understand other roles really speeds up development and improves the final product.

---

## 9. **Q: What’s your process for troubleshooting production issues?**

**A:**  
First, I check the logs and monitoring dashboards (like AWS CloudWatch) to narrow down the scope. If it’s a microservices issue, I look for communication breakdowns—like failed Kafka messages or API timeouts.  
I always try to reproduce the problem locally or in staging, write regression tests if possible, and then roll out a fix with proper CI/CD controls to minimize risk.

---

## 10. **Q: Why did you choose Java and Spring Boot for your backend work?**

**A:**  
Java’s stability and ecosystem make it ideal for scalable enterprise apps, and Spring Boot greatly simplifies configuration and microservice development.  
I find that with features like auto-configuration, dependency injection, and the large number of mature libraries, I can deliver production-ready systems faster and with fewer bugs.

---









# Java 面试八股文整理（学习路线顺序版）

---

## 1. OOP 基础（面向对象）

### Q: What is OOP?

A:  
OOP stands for Object-Oriented Programming. It's a way of organizing code using objects and classes. The core concepts are **encapsulation, inheritance, and polymorphism**.

---

### Q: What is encapsulation?  
A:  
Encapsulation is about hiding implementation details and exposing only what’s necessary. For example, in an ATM, users just interact with the interface; they don’t need to know the internal logic. In Java, we use access modifiers (`private`, `protected`, `public`) and getters/setters to control access.

---

### Q: What is inheritance?  
A:  
Inheritance lets a subclass reuse fields and methods from its parent class, which promotes code reusability. For example, a `Dog` class can inherit from an `Animal` class and override methods like `eatFood()` to customize behavior.

---

### Q: What is polymorphism?  
A:  
Polymorphism means the same method can behave differently for different objects. For example, both `Dog` and `Cow` inherit from `Animal` and override the `eat()` method—`Dog` eats meat, `Cow` eats grass. When you call `eat()` on an `Animal` reference, the actual method called depends on the object's runtime type.

---

### Q: What is a class?  
A:  
A class is like a blueprint in Java, defining fields and methods.

---

## 2. Java 基础语法

### Q: What's the difference between `final`, `finally`, and `finalize`?  
A:  
- `final`: Used to prevent inheritance (class), method overriding (method), or re-assignment (variable).
- `finally`: A code block in try-catch that always runs.
- `finalize()`: Called before the object is garbage collected, used to clean up resources.

---

### Q: What is serialization?  
A:  
Serialization converts a Java object into a byte stream for storage or network transfer; deserialization restores it back to an object.

---

### Q: What is abstraction?  
A:  
Abstraction hides complex implementation details and shows only the essentials. In Java, abstraction is achieved using abstract classes and interfaces.

---

### Q: What is an interface?  
A:  
An interface defines a contract of abstract methods that implementing classes must follow. Interfaces can have static and default methods but no constructors.

---

### Q: Difference between interface and abstract class?  
A:  
- One class can implement multiple interfaces but can only extend one abstract class.
- Abstract classes can have both abstract and concrete methods; interfaces only have abstract, default, or static methods.
- Interfaces don't have constructors.

---

## 3. 集合与容器

### Q: What is Java Collection Framework?  
A:  
It’s a set of classes and interfaces in `java.util` for storing and managing groups of objects. Major interfaces are `List`, `Set`, `Queue`, and `Map`. Examples: `ArrayList`, `HashSet`, `HashMap`.

---

### Q: List vs Set vs Map?  
A:  
- **List** (e.g., `ArrayList`): Ordered, allows duplicates.
- **Set** (e.g., `HashSet`): Unordered, unique elements.
- **Map** (e.g., `HashMap`): Key-value pairs.

---

### Q: Array vs Collection?  
A:  
Arrays are fixed in size, only hold one data type (primitive or object), and don't support dynamic resizing. Collections (like `ArrayList`, `HashMap`) are dynamic and provide more flexible ways to store and manipulate groups of objects.

---

### Q: Explain common Collection implementations you have used.  
A:  
- `ArrayList`: Dynamic array, fast random access.
- `LinkedList`: Doubly-linked, fast insert/delete.
- `HashMap`: Key-value, fast lookup.
- `HashSet`: Unique elements.
- `TreeMap`: Sorted map.
- `PriorityQueue`: Elements sorted by priority.

---

### Q: Comparable vs Comparator?  
A:  
- **Comparable**: For natural ordering, implements `compareTo()`.
- **Comparator**: For custom ordering, implements `compare()` and passed into sorting methods.

---

### Q: Deep copy vs shallow copy?  
A:  
Shallow copy duplicates references (changes affect both), deep copy duplicates everything (fully independent). Use `Cloneable` and override `clone()` for deep copy.

---

## 4. 关键字与特性

### Q: What does `transient` keyword do?  
A:  
Fields marked as `transient` are not serialized—useful for sensitive or unnecessary data.

---

## 5. 设计模式

### Q: What is Singleton?  
A:  
A pattern ensuring only one instance of a class exists.  
- **Eager Singleton**: Instance created at class loading, thread-safe.
- **Lazy Singleton**: Instance created when needed, must handle thread safety.

---

### Q: Observer Pattern?  
A:  
One-to-many dependency; when one object changes, all dependents are notified. Useful for event systems.

---

### Q: Prototype Pattern?  
A:  
Allows you to create object copies via cloning (`Cloneable` + `clone()`), useful for making many similar objects efficiently.

---

## 6. Java 进阶特性

### Q: Process vs Thread?  
A:  
A process is an independent unit with its own memory; threads are lightweight units within a process, sharing memory.

---

### Q: What is thread safety?  
A:  
Making sure shared resources are accessed safely across multiple threads (e.g., using `synchronized`, locks, or thread-safe collections like `ConcurrentHashMap`).

---

### Q: What is garbage collection?  
A:  
Automatic memory management—Java frees up memory used by objects no longer referenced.

---

## 7. Spring & 相关技术栈

### Q: Difference between Spring Framework and Spring Boot?  
A:  
- **Spring Framework**: Full-featured but needs manual config and external server.
- **Spring Boot**: Built on Spring, adds auto-configuration, embedded server, makes setup faster and easier.

---

### Q: What are IOC and DI?  
A:  
IOC (Inversion of Control): Object creation and dependency management is handled by the container, not the object itself.  
DI (Dependency Injection): Dependencies are injected by the container (usually via constructor or annotation).

---

### Q: What is AOP?  
A:  
Aspect-Oriented Programming. Allows adding functionality (like logging) without modifying original code, using annotations (e.g., `@Before`).

---

### Q: What is MVC?  
A:  
Model-View-Controller.  
- Model: Data and logic, includes DAO (Data Access Object) and DVO (Data Value Object).
- View: UI, no business logic.
- Controller: Receives input, calls models/views.

---

### Q: What is Spring Data JPA?  
A:  
A Spring framework that simplifies JPA usage, automates common data access.

---

### Q: Hibernate `get()` vs `load()`?  
A:  
- `get()`: Immediately hits DB, returns object or null.
- `load()`: Returns proxy, DB hit delayed until used, throws exception if object missing.

---

## 8. 数据库

### Q: Primary key vs foreign key?  
A:  
Primary key uniquely identifies a record; foreign key references another table’s primary key.

---

### Q: SQL vs NoSQL?  
A:  
- SQL: Relational, fixed schema, table-based, better for multi-row transactions.
- NoSQL: Non-relational, dynamic schema, document/key-value based, better for unstructured data.

---

### Q: What is a transaction and ACID?  
A:  
A transaction is a sequence of DB operations that succeed or fail together.  
- **Atomicity**: All or nothing.  
- **Consistency**: DB remains valid.
- **Isolation**: Transactions don't interfere.
- **Durability**: Committed data survives failures.

---

## 9. 其他常用技术

### Q: What is API?  
A:  
Application Programming Interface—set of rules for how systems communicate.

---

### Q: What is REST API?  
A:  
A web API design style using HTTP methods (GET, POST, PUT, DELETE) for CRUD operations.

---

### Q: GET vs POST?  
A:  
- **GET**: Fetch data, data in URL, less secure.
- **POST**: Create/modify data, data in body, more secure.

---

### Q: XML vs JSON?  
A:  
Both are used for data storage and transmission. XML is verbose with tag-based structure, JSON is lighter, uses key-value pairs, better for web data interchange.

---

### Q: What is CI/CD?  
A:  
Continuous Integration / Continuous Delivery or Deployment. Automates building, testing, deploying software to make releases faster and more reliable.

---

### Q: What is Docker?  
A:  
Docker is a platform for packaging, deploying, and running apps in containers. Commands include `docker build`, `docker run`, `docker ps`, `docker stop`, etc.

---

### Q: What is Elastic Beanstalk?  
A:  
AWS service for deploying and managing apps easily—handles scaling, load balancing, and monitoring automatically.

---

### Q: What is Kafka Topic and Partition?  
A:  
A **Topic** organizes messages by category (e.g., `user-logs`). A **Partition** splits a topic for scalability and parallelism; messages within a partition keep order.

---

### Q: What is Mockito (Mock/Spy)?  
A:  
Mockito is a Java testing framework for mocks (simulate objects) and spies (wrap real objects but allow partial mocking).

---

### Q: What is microservice fault tolerance?  
A:  
System's ability to keep working even if some services fail—ensures one failure doesn’t crash the whole app.

---

### Q: What is Spring Security?  
A:  
A framework for authentication, authorization, and security in Spring apps—protects web apps and APIs.

---## 

Arrays vs Collections in Java: Differences & Usage

### Q: What's the difference between arrays and collections in Java? Which ones have you used in your projects?

A:  
Sure! Arrays in Java have a fixed size – once you create them, you can't change their length. Collections, like `ArrayList` or `HashSet`, are dynamic – you can add or remove elements as needed. In my daily work, I usually go with collections because they're much more flexible. For example, if I don't know how many items I'll have up front, I just use an `ArrayList` or `HashMap`. Arrays are only really useful for things like working with primitive data types for performance, or if I need something super lightweight.

---

### Q: Can you walk me through the main types of collections you've used in Java?

A:  
Definitely. Here are some collections I use often and real-world examples:

- **ArrayList**: It's my go-to for dynamic lists. For instance, if I'm processing user data fetched from a database, I use `ArrayList` because the size isn't fixed and I need fast random access.
- **LinkedList**: I use this less often, but it's handy when I need to frequently add or remove elements from the beginning or middle of the list, like in queue implementations.
- **HashMap**: Super useful for key-value pairs. For example, if I'm caching user sessions or storing configs, I use `HashMap` for fast lookups.
- **HashSet**: Whenever I need to store unique elements only, like filtering out duplicate IDs from a data stream.
- **TreeMap**: If I need my keys sorted (like when showing items in alphabetical order), I use `TreeMap`.
- **LinkedHashMap**: Great when I want to maintain insertion order, like preserving the order of recently accessed items.
- **PriorityQueue**: Useful for scheduling tasks based on priority, such as a job scheduler where higher priority tasks should be executed first.

---

## Java Collections Framework

### Q: Can you explain the Java Collections Framework and how different interfaces like List, Set, and Map relate to each other?

A:  
Sure! The Java Collections Framework is basically a set of interfaces and classes that help us manage groups of objects. At the top, you've got `Collection` (which covers things like `List`, `Set`, and `Queue`) and then `Map` for key-value pairs. For example, `List` lets you store ordered, duplicate items, so I use `ArrayList` for that. `Set` stores only unique items, like `HashSet`. And `Map` is all about storing key-value pairs, so `HashMap` is really common in web apps for storing things like user info.

In a real project, I might use an `ArrayList` to hold a list of users, a `HashSet` to keep track of unique email addresses, and a `HashMap` for mapping user IDs to their profiles. It's all about picking the right tool for the job, depending on whether I care about order, uniqueness, or key-value lookups.





## Java Reflection 面试笔记

### Q: What is reflection in Java, and when would you use it?

A:  
Reflection in Java is a feature that allows you to inspect and manipulate classes, methods, and fields at runtime—even if you don’t know their names at compile time. I’ve used reflection mainly in situations where I need to build generic frameworks or libraries, such as serialization libraries, ORMs, or for writing unit tests where I need to access private fields or methods.  
For example, with reflection, you can dynamically create objects, call methods, or access fields—even private ones.

---

### Q: Can you give some practical use cases for Java reflection?

A:  
Definitely. Here are a few real-world cases:
- **Frameworks:** Most modern Java frameworks (like Spring, Hibernate) use reflection under the hood to wire up dependencies, inject beans, or map objects to database tables.
- **Testing:** In unit testing, reflection lets you access and modify private fields or invoke private methods to improve test coverage.
- **Serialization/Deserialization:** Libraries like Jackson or Gson use reflection to automatically convert between Java objects and JSON.
- **Plugins/Extensibility:** If you want to load and use classes that weren’t known at compile time (e.g., plugins), reflection is the tool for the job.

---

### Q: What are the main capabilities of reflection in Java?

A:  
Reflection provides several key features:
1. **Inspecting class information at runtime:** You can get complete class structure, including class name, fields, methods, constructors, and implemented interfaces—even if you don’t know the class at compile time.
2. **Dynamic object creation:** You can create an instance of a class at runtime using `Class.forName()` and `newInstance()`, even if you don’t know the class name at compile time.
3. **Dynamic method invocation:** You can invoke methods on an object dynamically using the `Method` class’s `invoke()` method, including private or protected methods.
4. **Accessing and modifying fields:** You can read and write the value of fields, even private ones, using the `Field` class’s `get()` and `set()` methods.

---

### Q: What are the downsides or risks of using reflection?

A:  
Reflection is powerful but comes with trade-offs:
- **Performance:** Reflective operations are slower than direct code, so they shouldn’t be overused in performance-critical paths.
- **Security:** Bypassing access control checks (e.g., accessing private fields) can break encapsulation and make your code less secure or more brittle.
- **Maintainability:** Code using heavy reflection can be harder to understand and debug. You lose compile-time type safety.
Generally, I avoid using reflection unless I’m writing frameworks or need it for special cases.

---

### Q: Can you show a simple code example of using reflection to call a method dynamically?

A:  
Sure! Here’s a quick example:

```java
Class<?> clazz = Class.forName("com.example.Person");
Object person = clazz.getDeclaredConstructor().newInstance();

Method setName = clazz.getMethod("setName", String.class);
setName.invoke(person, "Alice");

Method getName = clazz.getMethod("getName");
String name = (String) getName.invoke(person);
System.out.println(name); // Output: Alice
```

## Java & Spring 动态加载面试笔记

### Q: How do you dynamically load database drivers in Java?

A:  
In real-world projects, sometimes we need to support different databases like MySQL or Oracle, and load the appropriate driver at runtime. Java reflection is really handy for this.  
For example, in JDBC, I use `Class.forName("com.mysql.cj.jdbc.Driver")` to dynamically load the driver class based on the configuration. If the DB changes, I just change the driver class name in the config—no need to recompile.  
This approach is useful for making applications more flexible and database-agnostic.

---

### Q: Can you explain how Spring loads beans dynamically using configuration files?

A:  
Sure! Spring’s IOC (Inversion of Control) container is all about managing beans dynamically based on configuration.  
With XML or property files, you specify which beans you want, and the container loads and wires them up at runtime as needed.  
Under the hood, Spring parses the config files, uses reflection to create instances of the classes defined by their fully qualified names, and injects the required dependencies.

The process generally looks like this:
- Load all configuration from XML or properties files into memory.
- Use reflection to instantiate the class for each bean defined in the config.
- Dynamically inject properties or dependencies into those bean instances.

---

### Q: Why is this dynamic loading important in large-scale Java applications?

A:  
Dynamic loading decouples the application code from specific class implementations and dependencies. This means you can change implementations or configurations without touching your codebase—just update a config file.  
It’s especially valuable in enterprise applications where flexibility, scalability, and maintainability are key.

---

### Q: Can you show a simple example of specifying a bean in a configuration file and loading it in Java?

A:  
Absolutely! Here’s a basic example:

**In the config file:**

**In Java:**

```java
Properties config = new Properties();
config.load(new FileInputStream("config.properties"));

String className = config.getProperty("className");
Class<?> clazz = Class.forName(className);
Object bean = clazz.getDeclaredConstructor().newInstance();

String methodName = config.getProperty("methodName");
Method method = clazz.getMethod(methodName);
method.invoke(bean);
```



## Java Annotations (注解) 面试笔记

### Q: Can you explain how Java annotations work under the hood?

A:  
Sure! An annotation in Java is basically a special kind of interface that extends `java.lang.annotation.Annotation`. When we define an annotation, the compiler generates a corresponding class file for it.

At runtime, we can use reflection to retrieve and process annotation metadata from class files. If the annotation has `@Retention(RetentionPolicy.RUNTIME)`, it’s available at runtime for reflective access—this is how frameworks like Spring or JUnit work their magic.  
Under the hood, annotations are often handled by dynamic proxy objects implementing methods like `invoke` to return annotation values, which are stored in a map internally.

---

### Q: How do you define a custom annotation in Java?

A:  
It’s pretty straightforward. You use the `@interface` keyword to declare it, just like:
```java
public @interface MyAnnotation {
    String value();
}
```



### Q: What are the different annotation retention policies, and why do they matter?

A:
 There are three retention policies:

- **SOURCE**: Annotation is only kept in the source code and discarded by the compiler (`@Retention(RetentionPolicy.SOURCE)`). Useful for things like code linting or documentation.
- **CLASS**: Annotation is saved in the `.class` file but isn’t available at runtime (`@Retention(RetentionPolicy.CLASS)`). Common for compile-time tools.
- **RUNTIME**: Annotation is saved in the `.class` file **and** is available via reflection at runtime (`@Retention(RetentionPolicy.RUNTIME)`). This is what most frameworks need for things like dependency injection or runtime configuration.

------

### Q: How does Java actually store and access annotation information?

A:
 When you compile Java code, the compiler writes annotation metadata into the attribute section of the class file. At runtime, the JVM or reflection APIs (like `getAnnotations()`) read this metadata to retrieve annotation details.

For runtime annotations, you’ll find them stored in the `RuntimeVisibleAnnotations` section of the class file. If they’re not meant to be available at runtime, they’ll go in `RuntimeInvisibleAnnotations` or just get discarded.

------

### Q: What’s a real-world scenario where you created or used a custom annotation?

A:
 In one of my projects, I created a custom `@AuditLog` annotation to automatically log method invocations for sensitive operations. I combined it with an AOP (Aspect-Oriented Programming) approach, using reflection to inspect methods at runtime and log user actions transparently, which really improved both security and maintainability.





 根据你上传的长图内容，**提炼出面试常问问题+口语化英文回答**，并覆盖：

- Java异常体系和用法
- `==` vs `equals`
- `hashCode`和`equals`关系
- String/StringBuilder/StringBuffer区别
- Java 8新特性（Lambda、Stream、Optional、接口默认方法等）

适合做复习笔记/面试自述，**Markdown格式**如下：

------

~~~markdown
## Java 面试八股（异常、Object方法、字符串、Java8新特性）

---

### Q: Can you explain the Java exception hierarchy? What’s the difference between checked and unchecked exceptions?

A:  
Sure! In Java, all exceptions inherit from `Throwable`. There are two main branches: `Error` (serious problems like OutOfMemoryError, usually not caught by apps) and `Exception` (recoverable situations).
- **Checked exceptions** (like `IOException`, `SQLException`) must be declared or handled with try-catch. They are checked by the compiler.
- **Unchecked exceptions** (like `NullPointerException`, `IndexOutOfBoundsException`) inherit from `RuntimeException`. They don’t have to be declared or caught—they typically signal programming bugs.
In real projects, I use checked exceptions for expected error conditions and unchecked exceptions for bugs or API misuse.

---

### Q: How do you throw and catch exceptions in Java? What is the use of `throws`?

A:  
You throw exceptions with the `throw` keyword, like `throw new Exception("msg")`, and catch them with try-catch blocks.  
If a method might throw a checked exception, you declare it with `throws` in the method signature so callers are aware.  
Example:
```java
public void myMethod() throws IOException {
    // code that may throw IOException
}
~~~

You can also have a `finally` block to execute cleanup code, which runs whether or not an exception was thrown.

------

### Q: What’s the difference between `==` and `equals()` in Java?

A:
 `==` checks if two references point to the same object in memory. `equals()` checks for value equality, so it can be overridden by classes for custom comparisons (like `String` or `List`).
 For example:

```java
String a = new String("abc");
String b = new String("abc");
a == b; // false, different objects
a.equals(b); // true, same value
```

So for objects, always use `equals()` for value comparison.

------

### Q: Why do we need to override `hashCode()` when overriding `equals()`? What’s the relationship?

A:
 Whenever you override `equals()`, you should override `hashCode()`. This is because collections like `HashMap` and `HashSet` use hash codes to quickly find objects. If two objects are equal according to `equals()`, they must have the same hash code. Otherwise, data structures like `HashMap` won’t work as expected.

------

### Q: What’s the difference between String, StringBuilder, and StringBuffer in Java?

A:

- **String**: Immutable, any modification creates a new object.
- **StringBuilder**: Mutable, not thread-safe, but faster for single-threaded string manipulations (like lots of appends).
- **StringBuffer**: Mutable and thread-safe (uses synchronized methods), but slower than StringBuilder.
   In real work, I use `StringBuilder` for efficient string concatenation in single-threaded contexts, and `StringBuffer` if I need thread safety (which is rare these days).

|             | String             | StringBuilder | StringBuffer |
| ----------- | ------------------ | ------------- | ------------ |
| Mutable     | No                 | Yes           | Yes          |
| Thread-safe | No                 | No            | Yes          |
| Performance | Slow (for changes) | Fast          | Medium       |

------

### Q: What are some new features in Java 8? Can you explain lambda expressions, streams, and optional?

A:
 Java 8 introduced many cool features:

- **Lambda expressions**: Allow passing behavior as parameters, making code more concise.
   Example: `(a, b) -> a + b`

- **Stream API**: Makes it easier to process collections in a functional way (map, filter, reduce, etc).
   Example:

  ```java
  list.stream().filter(x -> x > 10).forEach(System.out::println);
  ```

- **Optional**: A container to avoid null pointer exceptions.
   Example: `Optional.ofNullable(obj).ifPresent(System.out::println);`

- **Default and static methods in interfaces**: Interfaces can now have concrete methods.
   Example:

  ```java
  interface MyIntf {
      default void print() { System.out.println("hi"); }
  }
  ```

------

### Q: Can you explain the try-catch-finally execution order, especially with return statements?

A:
 If there’s a return in the try block, the finally block still executes **after** the return, but before the method actually returns to the caller. If both try and finally have returns, the return in finally takes precedence (but this is discouraged and can be confusing).

------

整理自你上传的内容，这一部分涉及**Java常用集合(List/Set/Map/Queue)、遍历、排序、转换、比较器、线程安全集合、队列种类等**。以下是**英文八股问答+真实口语化答案**，Markdown格式，适合面试高频问题笔记！

------

~~~markdown
## Java Collection 面试八股（List, Set, Map, Queue等常见操作）

---

### Q: What are the main differences between List, Set, and Map in Java?

A:  
- **List** is an ordered collection that allows duplicates. Typical implementations are `ArrayList` and `LinkedList`. I use it when order matters and I might have duplicates.
- **Set** is an unordered collection with unique elements, like `HashSet` or `TreeSet`. I use it when I only want unique values, such as filtering duplicates.
- **Map** stores key-value pairs, like `HashMap` and `TreeMap`. It’s useful for looking up values by key, such as caching or mapping IDs to objects.

---

### Q: How do you iterate over a List, Set, or Map in Java? What are the best practices?

A:  
- For `List` or `Set`, I usually use enhanced for-loops or streams:
  ```java
  for (String s : list) { ... }
  list.forEach(s -> ...);
~~~

- For `Map`, I iterate over `entrySet()` to get both key and value:

  ```java
  for (Map.Entry<String, Integer> entry : map.entrySet()) {
      System.out.println(entry.getKey() + ":" + entry.getValue());
  }
  ```

- If I need to remove items during iteration, I use an `Iterator` to avoid `ConcurrentModificationException`.

------

### Q: How do you sort a List in Java? How do you sort a custom object list?

A:

- To sort a basic list:

  ```java
  Collections.sort(list); // For natural ordering (needs Comparable)
  ```

- To sort custom objects, either implement `Comparable` or provide a `Comparator`:

  ```java
  Collections.sort(userList, Comparator.comparing(User::getAge));
  // or with lambda:
  userList.sort((a, b) -> a.getAge() - b.getAge());
  ```

- Since Java 8, I often use streams for more readable sorting and mapping.

------

### Q: What’s the difference between Comparable and Comparator in Java?

A:

- **Comparable** is implemented by the object itself to define its natural order, using the `compareTo()` method.
- **Comparator** is a separate object that defines custom sorting logic for classes that don’t implement Comparable, or when multiple sorting strategies are needed.
- In real work, I often use `Comparator` when I want to sort the same class by different attributes.

------

### Q: How do you convert between List and Set or between List and array?

A:

- **List to Set** (remove duplicates):

  ```java
  Set<String> set = new HashSet<>(list);
  ```

- **Set to List**:

  ```java
  List<String> list = new ArrayList<>(set);
  ```

- **List to Array**:

  ```java
  String[] arr = list.toArray(new String[0]);
  ```

- **Array to List**:

  ```java
  List<String> list = Arrays.asList(arr);
  ```

- These conversions are common when removing duplicates or adapting APIs.

------

### Q: What are thread-safe collections in Java? When do you use them?

A:
 Java provides thread-safe collections like `Vector`, `Hashtable`, and synchronized wrappers (`Collections.synchronizedList(list)`). More modern options include `ConcurrentHashMap` and `CopyOnWriteArrayList`.
 I use them when I expect concurrent access from multiple threads. For example, `ConcurrentHashMap` is my go-to for concurrent key-value access without explicit synchronization.

------

### Q: Can you explain the difference between ArrayList and LinkedList?

A:

- **ArrayList** is backed by an array, supports fast random access (O(1)), but slow inserts/removals in the middle (O(n)).
- **LinkedList** is a doubly-linked list, so inserts/removals are faster at the ends, but random access is slower (O(n)).
- I typically use ArrayList unless I have many insertions/removals at the beginning or middle.

------

### Q: What is the difference between HashMap, TreeMap, and LinkedHashMap?

A:

- **HashMap** is unordered and offers O(1) lookup time.
- **TreeMap** keeps keys sorted (O(log n) operations).
- **LinkedHashMap** maintains insertion order.
   I choose HashMap for fast lookup, TreeMap when I need sorted keys, and LinkedHashMap if order matters (like caching).

------

### Q: What is a Queue and what are some implementations in Java?

A:
 A Queue is a collection for holding elements prior to processing. Key implementations:

- **LinkedList** (implements Queue)
- **PriorityQueue** (elements sorted by priority)
- **ArrayDeque** (efficient double-ended queue)
- **BlockingQueue** (thread-safe, used for producer-consumer)
   I use `PriorityQueue` for scheduling tasks, and `BlockingQueue` for multi-threaded producer-consumer patterns.

------

### Q: What is fail-fast and fail-safe in collections?

A:

- **Fail-fast** collections (like ArrayList, HashMap) throw `ConcurrentModificationException` if they detect changes during iteration.
- **Fail-safe** collections (like CopyOnWriteArrayList, ConcurrentHashMap) don’t throw exceptions and can handle concurrent modifications safely.
   I use fail-safe collections when I need to iterate and modify at the same time, usually in concurrent scenarios.

------

```
如需补充**遍历陷阱、Map特殊实现、Concurrent包底层原理**等内容，欢迎继续补充！
```
