## Gradle as a dependency management system

If you've used Gulp, Yarn, RubyGems, or Pip, then you should find Gradle to be relatively easy to use.

Gradle is both a dependency management tool and build management tool.  Dependencies are libraries pulled in from external artifact repositories like Maven Central or possibly a corporate/private repository.  The `build.gradle` file is the centerpiece of a Gradle project, much like `package.json` is to a Yarn/NPM project.

## Artifact repositories

Artifacts are bundled packages that provide a library for use by other libraries or applications.  Usually artifacts are simple Java Archives (JAR files).

A system that hosts and publishes artifacts is call a "repository".

If you look in the `repository` block of the `build.gradle` file, you will see that the project sources its dependencies from the Maven Central public repository. (Maven, the namesake of the repository, is another dependency and build management tool for Java projeccts.)  Another popular repository is JCentral.  Google also provides a public repository.  There is typically little differences between the public repositories.

## Dependency declaration

The `build.gradle` file has a `dependencies` block where dependencies can be specified.  A single line specifies the dependency and it looks like this:

```groovy
implementation 'PACKAGE_ID:ARTIFACT_ID:VERSION'
```

For example, to install Apache's Common Lang3 dependency, you would specify it this way in the `dependencies` block:

```groovy
implementation 'org.apache.commons:commons-lang3:3.8.1'
```

## Search for dependencies on the interwebz

Artifact repositories will usually have a web interface that you can use to search for artifacts.  Maven Central has a search frontend here: https://search.maven.org/.

The best way to search is with the package id (like `org.apache`) and/or the artifact id.  For example, to find the Common Lang3 dependency above, you could search `org.apache commons` on search.maven.org.

### Kata requirements

1. Install JUnit (either 4 or 5) by locating it on search.maven.org.  Note that there are several "mirrored" versions of JUnit that you probably don't want.  Look for the JUnit artifact whose package begins with `org.junit`.
2. Install Spring Boot.  Note that this is actually kind of tricky.  Spring Boot itself is a massive collection of Spring dependencies.  Head to [the Gradle section of the Spring Boot guide](https://spring.io/guides/gs/spring-boot/#scratch) for help on this.  Replace `compile(...)` with `implementation`.  The two commands are synonymous but `implementation` is preferred.
3. Run `gradle build`.  This will pull down JUnit and Spring Boot.

Commit your `build.gradle` file and push it up.

Next kata: [Use Gradle as a build and release management system](kata.dependency_management.md).
