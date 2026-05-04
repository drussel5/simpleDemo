# AGENTS.md

## Cursor Cloud specific instructions

This is a simple Spring Boot CLI application (no web layer, no database). It prints "Hello Spring Boot!" on startup and exits.

### Java Version

The project requires **Java 23** (`pom.xml` declares `<java.version>23</java.version>`). The default VM has Java 21, so Java 23 (Eclipse Temurin) is installed at `/usr/lib/jvm/jdk-23.0.2+7`. `JAVA_HOME` is set in `~/.bashrc`. Verify with `java -version`.

### Build & Run

All commands use the Maven Wrapper (`./mvnw`) — no global Maven install is needed.

- **Build:** `./mvnw clean compile`
- **Test:** `./mvnw test` (single context-load integration test)
- **Run:** `./mvnw spring-boot:run` (prints "Hello Spring Boot!" then exits)
- **Package:** `./mvnw clean package` (produces JAR in `target/`)

### Notes

- There is no web server, no REST API, and no database. The app starts, prints a message, and shuts down.
- Mockito warnings about dynamic agent loading on Java 23 are expected and harmless.
