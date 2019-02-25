## Hook up a relational database using Spring Data

Spring Data uses the Java Persistence API (JPA) to provide a way to integrate a database with Spring applications.  Spring Data has elected to encapsulate the repository pattern.  In fact, the repository pattern is so common in software development that Spring Data literally makes it as easy as defining an interface.  Spring Data does the heavy lifting for you.

### Kata requirements

1. Begin by following Spring Data's [Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/) tutorial and integrating Spring Data into your existing REST application.  Do not worry about the "Create an Application class" section for now. Carefully note that there are some new dependencies tossed into the build.gradle file: spring-boot-starter-data-jpa and H2.  The spring-boot-starter-data-jpa dependency provides Spring Data goodies while H2 is an in-memory SQL database.
2. Once you've completed the tutorial, ponder this question: (1) is it worth testing the repository in unit or integration tests?
3. The application must be runnable from the command line.
4. The interface you create should have the method `findByLastName`.
