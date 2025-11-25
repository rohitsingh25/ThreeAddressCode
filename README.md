# Three Address Code

This repository is for a Three-Address Code (TAC) utility/tooling. TAC is an intermediate representation used by compilers to simplify analysis and optimization. This repo currently contains the third-party JAR dependencies required by the tool and a placeholder for documentation. If you want a fuller setup (source, build, examples), let me know and I can scaffold it.

## Repository Layout

- `Jar Files/` — third‑party libraries used by the project
	- `jakarta.servlet-api-5.0.0.jar`
	- `javaparser-core-3.0.0-alpha.2.jar`
	- `javaparser-core-3.25.5.jar`
	- `javax.servlet-api-3.1.0-javadoc.jar`
	- `javax.xml-1.3.4.jar`
	- `jfxrt.jar`
	- `jts-core-1.17.0.jar`
	- `lucene-core-8.5.2.jar`
	- `org.osgi.service.jdbc-1.0.0.jar`
	- `rt-4.0.3.jar`
- `README.md` — this file

## Prerequisites

- Java 11 or newer (`java` and `javac` on PATH)
- Linux/macOS/Windows shell

## Using The Dependencies

If you are adding code or using these JARs from another Java project, include everything in `Jar Files/` on your classpath.

Examples (Linux/macOS bash):

Compile your sources (if you have a `src/` folder):

```bash
javac -cp "Jar Files/*" -d out $(find src -name "*.java")
```

Run your app (replace with your main class):

```bash
java -cp "out:Jar Files/*" your.package.Main
```

On Windows PowerShell, the run command becomes:

```powershell
java -cp "out;Jar Files/*" your.package.Main
```

## What’s Here vs. What’s Missing

- Present: third‑party dependencies under `Jar Files/`.
- Missing (can be added on request):
	- Source code for TAC generation/parsing (`src/`)
	- Build tooling (Maven/Gradle) to avoid committing JARs
	- CLI or GUI entry point with examples and tests

If you want, I can convert this to a Maven/Gradle project so dependencies are declared in a `pom.xml`/`build.gradle` and fetched automatically, and scaffold a minimal TAC example using JavaParser.

## Development Notes (Optional)

- For reproducible builds, prefer Maven or Gradle over committing JARs.
- Suggested next steps:
	1. Create `src/main/java/` and add a `Main` entry point.
	2. Add a simple parser pipeline (e.g., JavaParser) to produce TAC.
	3. Replace `Jar Files/` with managed dependencies (Maven Central coordinates).

## Contributing

Open an issue describing what you want to add (e.g., examples, CLI, UI). PRs are welcome once a build tool is in place.

