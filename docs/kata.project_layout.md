## Set up the project directory structure

The typical directory layout of a Java app looks like:

```
./
  src/
    main/
      java/
        org/
          my/
            package/
              Foo.java
    test
      java/
        org/
          my/
            package/
              FooTest.java
```

Notice how (1) everything is under `src/`, and (2) the layout of `src/test` mirrors `src/main`.  The mirrored directory structure is intended to help with navigability of the project.  If you know that Foo.java is in package org.my.package, the you know that the test file is in the exact same place in the `src/test` directory.

Notice also that under `src/main` are nested directories: `org/my/package`.  This is a package, which is Java's mechanism for organizing code into logic units.  (You can think of packages as loosely similar to namespaces in C# or modules in Ruby.)  A Java file must always begin by declaring the package it belongs to.  Slashes are replaced with periods. Example:

```java
package org.my.package

public class Foo {
  // ...
}
```

Sensible package identifiers start with the organization's website in reverse.  For example, if my website was iowashoes.com, my package would start out as `com.iowashoes`.

### Kata and requirements

**Recommendation**: use a program other than Intellij for this kata.  VSCode, Atom, Sublime, or even just Terminal can be used.

Create the initial layout of the project using the typical directory layout specified above.

The layout must:
- Include a sensible package identifier in both `src/main` and `src/test`.  Examples: `src/main/com/your/package`, `src/test/com/your/package`.
- Include a Java class file in `src/main/com/your/package`.  The Java class file should have a class; the class can be empty.
- Include a Java test class file in `src/test/com/your/package`.  The Java test class should have a class; the class can be empty.

Commit and push when you're done.