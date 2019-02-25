# getting-started-java-11
This repository provides a set of katas that builds from almost nothing to a fully functioning REST API.

Here are the katas in order:
  - Kata: [Set up the project in the classic Java project layout style](docs/kata.project_layout.md).
  - Kata: [Use Gradle as a dependency management system](docs/kata.dependency_management.md).
  - Kata: [Rapidly stand up a REST API using Spring Boot](docs/kata.spring_boot_fast.md).
  - Kata: [Hook up a relational database to the REST API](docs/kata.hook_up_rds.md) using Spring Data's powerful dynamic repository pattern.
  - Kata: [Weave it all together with Dependency Injection](docs/kata.dependency_injection.md).
  - TODO -> Kata: Hook up OAuth2 authentication, using Spring, to individual endpoints through the use of JSON Web Tokens (JWTs).
  - TODO -> Kata: Build on the OAuth2 authenication system by adding authorization through client claims.

Each kata builds on the code from the last kata.  **You are encouraged to make your own fork of this repository.**

### Required Software

1. [Install Java 11](https://www.oracle.com/technetwork/java/javase/downloads/index.html) appropriate to your operating system.
2. [Install Gradle version 5.2 or higher](https://gradle.org/install/#manually).  If you're on a Mac with Homebrew, a simple `brew install gradle` will install it in a few minutes.
3. [Install JetBrain's Intellij IDE](https://www.jetbrains.com/idea/download/).  Either the Ultimate version or the Community version can be used.
