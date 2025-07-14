## Motivation

At Stripe, our interview process has some interviews where you write
code, typically on your laptop.

We've noticed that more often than not, we've had to spend a significant
portion of the interview helping candidates setup a maven-based Java
environment on their personal laptops.

We've created a (rather ad-hoc) maven project to help candidates
determine if their laptops were setup to write Java, so interviews can
be about evaluating the candidate, and not the way their environment is
setup.

# Getting ready

If you can run these commands, your development environment is probably
ready for Stripe's Java interview questions:

```bash
$ java -version
$ git clone [the project's URL]
$ cd [into the project]
$ ./mvnw clean compile exec:java
```

Or to run the default goal:
```bash
$ ./mvnw
```

# About This Project

## Requirements

* **Java 17** or later
* **Maven 3.9.10** or later (or use the included Maven wrapper)

## Running

### Using Maven wrapper (recommended)
The project includes a Maven wrapper, so you don't need to install Maven separately:

```bash
./mvnw clean compile exec:java
```

### Development
```bash
# Clean, compile, test, and run
./mvnw clean test exec:java

# Just compile and run
./mvnw compile exec:java

# Run tests
./mvnw test

# Package as JAR
./mvnw package
```

## Dependencies & configuration

Don't read into the chosen libraries too much.
We've added them to help alleviate two main problems that may be seen
after maven is setup:
- Maven works correctly with third-party dependencies
- Maven's classpath is setup correctly

### Included dependencies

- **[Guava] 33.4.0-jre** - Google's core libraries for Java
- **[JUnit 4] 4.13.2** - Testing framework

## I prefer Gradle/Pants/Ivy/Makefiles/Bespoke Bash Scripts, do I need to use this?

If you prefer different configuration files, that's awesome.
Some interview questions may ask to implement something from nothing,
and some may want to watch you interact with a pre-existing codebase.
For the former, it doesn't matter what you use, as long as you're able
to get things setup quickly.

Concerning the latter: Maven tends to be the most common format Java
libraries are distributed as.
Because of that, all pre-existing codebases we use in our interviews use
maven.
We aren't really specifically interested in how you write Maven project
files, but want you to quickly get them up and running.

## Useful references
- [Installing Maven](https://maven.apache.org/install.html)
  - [using Homebrew, on OS X](https://formulae.brew.sh/formula/maven)
  - [more instructions for Windows](https://maven.apache.org/guides/getting-started/windows-prerequisites.html)
- [Apache Maven FAQ](https://maven.apache.org/general.html)

[Guava]: https://github.com/google/guava
[JUnit 4]: https://junit.org/junit4/
[Maven]: https://maven.apache.org/
