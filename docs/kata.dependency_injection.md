## Weave it all together with Dependency Injection

Dependency injection is the principle of *providing* instances rather than letting the class new up its own dependencies.  This simplifies architecture and produces more modular code.  Here's an example.

```java

// The class (Car) is newing up its own dependencies (Driver).
public class Car {
    private Driver driver;

    public Car() {
        driver = new Driver();
    }

    public void go() {
        driver.wakeUp();
        driver.hitTheAccelerator();
    }
}
```

With constructor-based dependency injection:

```java
// The class (Car) now receives the object it depends on through its constructor.
// The constructor-based injection pattern is well suited to the immutable service pattern.
// Immutable services cannot have their dependencies changed after construction.
// They tend to be less verbose as they do not have getters and setters.
public class Car {
    private Driver driver;

    public Car(Driver driver) {
        this.driver = driver;
    }

    public void go() {
        driver.wakeUp();
        driver.hitTheAccelerator();
    }
}
```

If we "Spring-ify" the above, so that Spring knows to use dependency injection, we get this:

```java
// The Service annotation marks this class as a bean for instantiation in Spring's internal list of classes to instantiate.
@Service
public class Car {
    private Driver driver;

    // The Autowired annotation tells Spring to look up instances of the parameters required, Driver in this case.
    // In fact, since this is the only constructor, Spring does not require the @Autowired annotation.
    @Autowired
    public Car(Driver driver) {
        this.driver = driver;
    }

    public void go() {
        driver.wakeUp();
        driver.hitTheAccelerator();
    }
}
```

Of course, a Driver object must be provided to Spring as well:

```java
@Service
public class Driver {
    public Driver() { }

    public void wakeUp() { /* ... */ }

    public void hitTheAccelerator() { /* ... */ }
}
```

### Kata requirements

If you've followed the katas up to this point, then you should have a Java class marked with a `@Controller` and Java interface that extends 
`CrudRepository`.  You might notice that the interface does not have an annotation on it.  This is okay, as Spring will automatically look for interfaces in your code base that extend `CrudRepository` and instantiate them for you.

Ensure that wherever the `main` method is located is marked as the starting point.  You should have completed this in the Spring Boot kata.  If not, make sure the class containing `main(...)` is marked with `@SpringBootApplication`.

1. Create a service called `CustomerService` and mark it as a bean.  The service's constructor should take in the CRUD interface you created in "Hook up a relational database using Spring Data".
2. Add [Mockito](https://site.mockito.org/) as a dependency in build.gradle (for mocking) and then test-drive a new method in the service that calls to the repository's `findByLastName` method.
3. In the Controller class, created in "Rapidly stand up a REST API using Spring Boot", test-drive adding `CustomerService` and calling the method in it.  The endpoint should return the list of Customers in the database.
4. Run the application and hit the endpoint.  Does it return what you expect it to?
