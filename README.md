# Fun To Learn

A German study tool built with Spring Boot: course-book screenshots → AI word extraction → skill-based practice games with per-skill spaced repetition.

> **Status:** early development — project skeleton.

## What it will do

- **Word bank per lesson:** nouns, verbs, adjectives, prepositions and connectors with their grammar (articles, plurals, Perfekt, cases, …).
- **AI extraction:** upload a screenshot of a course-book page; a vision model extracts the words as drafts, which are validated and approved by hand.
- **Skill-based practice:** each grammar skill (e.g. noun article, verb Perfekt) is its own game, generated from the word bank.
- **Spaced repetition:** progress is tracked per word *and* per skill (Leitner boxes), so knowing a word's meaning doesn't mean you know its article.

## Tech stack

Java 25 · Spring Boot 4 · Maven · PostgreSQL · Spring Data JPA · Flyway · Spring Security + JWT · Spring AI · JUnit 5 · Mockito · Testcontainers · Docker Compose · GitHub Actions. Frontend later: Angular.

Dependencies are added feature by feature, so not all of these are in the build yet.

## Run locally

Requirements: JDK 25+ (the wrapper downloads Maven itself).

```powershell
cd backend
.\mvnw.cmd spring-boot:run      # starts on http://localhost:8081
```

Check that it is up:

```powershell
curl.exe http://localhost:8081/actuator/health
# {"status":"UP"}
```

Run the build with all tests:

```powershell
.\mvnw.cmd verify
```

On macOS/Linux use `./mvnw` instead of `.\mvnw.cmd`.

## Project layout

```
fun-to-learn/
├── backend/        Spring Boot application (Maven)
└── .github/        CI workflow
```