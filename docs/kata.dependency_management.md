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

## Search for dependencies

### Kata requirements
