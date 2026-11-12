# Day 1 — Modern SDLC and Build Automation

> **Course section:** Day 1 — Modern SDLC Explained  
> **Video:** [Jenkins Basics to Production — Cloud with Josh / Precode Camp](https://www.youtube.com/watch?v=uHNOqKdqQas)  
> **Covered timestamps:** 00:07:35–00:58:50

## Scope of these notes

The course outline shared for this lesson contains topic titles and timestamps, not a word-for-word transcript. This guide follows every Day 1 topic in that outline and expands it into a revision reference. Examples and explanations are learning notes, not exact quotations from the instructor.

## 1. Modern SDLC Explained

**Timestamp:** [00:07:35](https://www.youtube.com/watch?v=uHNOqKdqQas&t=455s)

### What is SDLC?

SDLC stands for **Software Development Life Cycle**. It is the structured process a team follows to plan, build, test, release, operate, and improve software.

Think of it as the complete journey of a software product: from the first idea to a running application that is continuously maintained and improved.

### Why do we need an SDLC?

Without a defined process, teams may build features users do not need, misunderstand requirements, discover bugs late, make inconsistent releases, struggle with hand-offs, or find it difficult to maintain software.

An SDLC gives the team a repeatable way to coordinate work, manage quality, reduce risk, and deliver value.

### Traditional and modern software delivery

A traditional process may separate development, testing, and operations into distinct hand-off stages. This can create long feedback loops: developers finish their work, pass it to another team, and problems may only appear later.

Modern software delivery aims for smaller changes, faster feedback, collaboration, automation, and continuous improvement. Agile practices help teams deliver work incrementally. DevOps encourages development and operations to share responsibility for delivering and running software.

**Important distinction:** Agile is a way of organizing and delivering work in short feedback-driven cycles. DevOps is a culture and set of practices that bring development and operations together. Automation supports both, but neither is simply a tool.

### Real-world example

Imagine an online shopping application. A product owner identifies a need for order tracking. The team clarifies requirements, designs the feature, implements the API and application changes, tests the workflow, releases it, monitors errors and performance, and uses customer feedback to improve it. The cycle repeats as the product evolves.

## 2. SDLC Phases — End-to-End View

**Timestamp:** [00:09:18](https://www.youtube.com/watch?v=uHNOqKdqQas&t=558s)

Organizations may use different names or combine phases, but these activities are common.

### 2.1 Planning and requirement analysis

The team identifies the problem, users, goals, scope, constraints, and expected behavior.

Questions include: What problem are we solving? Who will use the software? What must it do? What are the security, performance, and availability expectations?

**Outputs:** requirements, user stories, acceptance criteria, and a prioritized backlog.

### 2.2 Design

The team decides how the system should be structured. Design may cover application architecture, components, database schema, data flow, APIs, user experience, security boundaries, and infrastructure.

**Outputs:** architecture diagrams, technical designs, API definitions, and database designs.

### 2.3 Development / implementation

Developers turn the design into source code. Work is normally managed through version control such as Git. Good practices include small changes, meaningful commits, code reviews, and consistent coding standards.

**Output:** source code and configuration committed to a repository.

### 2.4 Build

The source code and dependencies are processed into something that can be tested or run. Depending on the technology, this may compile source code, resolve dependencies, run build tasks, package files, or create a container image.

**Output:** a build artifact, package, executable, or container image.

### 2.5 Testing and quality assurance

The team checks whether the software behaves as expected.

- **Unit tests:** check small pieces of code in isolation.
- **Integration tests:** check that components work together.
- **System / end-to-end tests:** check complete user workflows.
- **Acceptance tests:** check whether requirements are satisfied.
- **Performance tests:** examine response time and behavior under load.
- **Security tests:** look for vulnerabilities and insecure behavior.

Testing can be automated, manual, or a combination. Finding defects earlier usually makes them cheaper to fix.

### 2.6 Release and deployment

A **release** is a version approved to be made available. **Deployment** is the act of installing or making that version run in an environment.

Common environments:

- **Development:** active development and early testing.
- **Testing / QA:** verification by the test team.
- **Staging:** a production-like environment for final checks.
- **Production:** the environment used by real customers.

The exact environment names and promotion process vary by organization.

### 2.7 Operations and monitoring

After deployment, the application must be operated and observed. Teams monitor availability, error rates, latency, CPU, memory, storage, network usage, logs, traces, and business metrics.

Monitoring helps teams discover failures and understand application behavior in real use.

### 2.8 Maintenance and feedback

The team fixes defects, patches dependencies, improves performance, responds to feedback, and adds features. Those changes start another cycle.

### SDLC flow to remember

    Plan
      ↓
    Requirements
      ↓
    Design
      ↓
    Develop
      ↓
    Build
      ↓
    Test
      ↓
    Release / Deploy
      ↓
    Operate & Monitor
      ↓
    Feedback and Maintenance
      └───────────────→ back to Plan

**Key idea:** SDLC is not just coding. It covers the complete life of software, including what happens before development and after deployment.

## 3. Compiled vs. Interpreted Languages — CI/CD Perspective

**Timestamp:** [00:36:43](https://www.youtube.com/watch?v=uHNOqKdqQas&t=2203s)

This distinction matters because applications do not all produce runnable outputs in the same way.

### Compiled languages

A compiler translates source code into another form before the program runs. Depending on the language and platform, the output may be native machine code, bytecode, or another intermediate representation.

Examples:
- C and C++ commonly compile to native binaries.
- Java compiles source code into JVM bytecode, which runs on a Java Virtual Machine (JVM).

Simplified Java flow:

    Java source (.java)
           ↓ javac
    Bytecode (.class)
           ↓ JVM
    Running application

A compiled-language CI workflow may check out source code, select the compiler/runtime, resolve dependencies, compile the source, run tests, package the output, publish the artifact or build an image, and deploy the approved version.

**Important:** “Compiled” does not mean every application produces one native executable. Java normally produces bytecode and requires a compatible JVM.

### Interpreted languages

In an interpreted-language workflow, source code is commonly executed by an interpreter or runtime rather than being compiled ahead of time into a standalone native executable.

Examples commonly placed in this category:
- Python, executed by the Python runtime.
- JavaScript, executed by a runtime such as Node.js.

Simplified Python flow:

    Python source (.py)
           ↓
    Python interpreter
           ↓
    Running application

A typical CI workflow checks out source code, sets up the required runtime/version, installs dependencies, runs linting and tests, prepares a package or deployment bundle, and may build a container image.

**Important nuance:** This distinction is a useful introduction, not an absolute description of every runtime. Some interpreted-language runtimes use bytecode or just-in-time compilation internally.

### Comparison

| Area | Compiled-language example | Interpreted-language example |
| --- | --- | --- |
| Examples | Java, C, C++ | Python, JavaScript |
| Typical build activity | Compile source and package output | Set up runtime, resolve dependencies, validate and package source |
| Common output | Binary, bytecode, package, or image | Source bundle, package, or image |
| Runtime | May need a runtime such as JVM | Needs an appropriate interpreter/runtime |
| CI checks | Compilation, tests, packaging | Dependency installation, linting, tests, packaging |

Both types of applications can be tested, packaged, containerized, and deployed through CI/CD.

## 4. Build Workflows: Containerized vs. Non-Containerized Applications

**Timestamp:** [00:49:37](https://www.youtube.com/watch?v=uHNOqKdqQas&t=2977s)

### What is a build artifact?

A **build artifact** is an output produced by a build process that can be stored, tested, distributed, or deployed. Examples include a JAR file, executable, ZIP package, or container image.

### Non-containerized workflow

The application is packaged or copied to the target environment. That environment must provide the required runtime, libraries, configuration, and operating-system dependencies.

    Git repository
          ↓
    CI build and tests
          ↓
    Application artifact (for example, app.jar)
          ↓
    Artifact repository / release storage
          ↓
    Server with compatible runtime
          ↓
    Run application

**Advantages**
- Fewer container-specific components to learn and operate.
- Straightforward for an application deployed to a known server environment.
- The application artifact can be smaller than a full container image.

**Challenges**
- The target server must have compatible runtime versions and dependencies.
- Environment differences can cause “works on my machine” problems.
- Runtime installation and configuration must be managed separately.

### Containerized workflow

A container image packages the application together with its user-space runtime and required dependencies. The image is built from a Dockerfile and can run as a container on a compatible container engine.

    Git repository
          ↓
    CI checks and tests
          ↓
    Docker build
          ↓
    Container image
          ↓
    Image registry
          ↓
    Target host / container platform
          ↓
    Run container

**Advantages**
- The same image can be promoted through testing, staging, and production.
- Runtime dependencies are packaged with the application.
- Images work naturally with container platforms and repeatable deployments.

**Challenges**
- Teams must manage image size, security, registries, networking, storage, and runtime configuration.
- Secrets and environment-specific configuration should not be baked into the image.
- Containers rely on the host kernel and a compatible container runtime; they are not full virtual machines.

### Side-by-side comparison

| Concern | Non-containerized | Containerized |
| --- | --- | --- |
| Deployment unit | Application package / artifact | Container image |
| Runtime | Prepared on target server | Included in image where appropriate |
| Environment consistency | Depends more on server configuration | Image helps keep user-space dependencies consistent |
| Distribution | Artifact repository / package storage | Container registry |
| Operations | Manage host runtime and app process | Manage host/container platform and container lifecycle |

**Key point:** Containers do not remove the need for build and test. They change how the application and its runtime dependencies are packaged and delivered.

## 5. Compiled Languages: CI/CD Build Workflow

**Timestamp:** [00:50:18](https://www.youtube.com/watch?v=uHNOqKdqQas&t=3018s)

A compiled-language pipeline usually needs a build environment containing the correct compiler, build tool, and dependencies.

### Example: Java application

A common Maven-based flow:

    Developer pushes code
            ↓
    CI checks out repository
            ↓
    Set up JDK and Maven
            ↓
    Resolve dependencies
            ↓
    Compile source
            ↓
    Run tests
            ↓
    Package JAR
            ↓
    Store artifact or build container image
            ↓
    Deploy approved version

Commands commonly used in a Maven build include:

    mvn compile
    mvn test
    mvn package

A combined command often used in CI:

    mvn clean verify

- **clean** removes output from a previous build.
- **verify** runs the lifecycle through verification, including earlier phases such as compilation and tests when configured.

The exact Maven lifecycle and plugin behavior will be studied in the Maven section later in this course.

### Why compile in CI?

Compilation catches errors before a change is promoted. Automated tests provide additional confidence that the application behaves correctly. Packaging creates a versioned artifact that can be stored and deployed.

A successful compile alone does not prove that an application is correct; tests and other quality checks are still important.

## 6. Interpreted Languages: CI/CD Build Workflow

**Timestamp:** [00:53:29](https://www.youtube.com/watch?v=uHNOqKdqQas&t=3209s)

Interpreted-language projects still need a repeatable CI process even when there is no traditional compile-to-native-binary step.

### Example: Python application

A common workflow:

    Developer pushes code
            ↓
    CI checks out repository
            ↓
    Set up Python version
            ↓
    Create isolated environment
            ↓
    Install dependencies
            ↓
    Run linting and tests
            ↓
    Prepare deployment package or image
            ↓
    Publish / deploy approved version

Example commands for a simple Python project:

    python -m venv .venv
    source .venv/bin/activate
    python -m pip install -r requirements.txt
    python -m pytest

These commands are illustrative. A real project may use Poetry, uv, Pipenv, a different test runner, or a containerized build environment.

### What is the important difference?

For many interpreted applications, CI focuses on setting up the correct runtime, installing pinned dependencies, checking code quality, and running tests. The application may then be shipped as source plus dependencies, or packaged into a container image.

Do not confuse “no traditional compilation step” with “no build process.” Dependency resolution, validation, packaging, and artifact creation are still part of reliable delivery.

## 7. Why Build Automation Tools Matter

**Timestamp:** [00:56:52](https://www.youtube.com/watch?v=uHNOqKdqQas&t=3412s)

### What is build automation?

Build automation means using tools and repeatable instructions to perform software build tasks consistently instead of relying on developers to execute every step manually.

Depending on the project, automated tasks can include checking out source code, selecting tool versions, resolving dependencies, compiling or preparing code, running tests and quality checks, packaging artifacts or building images, and publishing outputs.

### Why automate?

1. **Consistency:** the same defined steps run each time, reducing differences between developer machines and CI environments.
2. **Speed:** automation reduces repeated manual work and can run checks as soon as a change is pushed.
3. **Early feedback:** developers learn that a change broke compilation or tests before it reaches production.
4. **Repeatability:** a pipeline records the steps used to produce an artifact, making the process easier to reproduce and investigate.
5. **Fewer manual mistakes:** automation reduces the risk of skipped steps, incorrect order, or inconsistent options.
6. **Team collaboration:** a shared pipeline gives developers, testers, and operations teams a common delivery process.
7. **Traceability:** build logs, test reports, artifact versions, and commit identifiers help answer what was built, from which code, and whether checks passed.

### Examples of build automation tools

| Tool | Typical role |
| --- | --- |
| Maven | Build automation and dependency management, especially in Java projects |
| Gradle | Build automation and dependency management |
| npm scripts | Run project-defined JavaScript tasks |
| Make | Automate command-based build tasks |
| Jenkins | Orchestrate CI/CD workflows and invoke build, test, and deployment tools |

**Important distinction:** Maven, Gradle, npm, and Make commonly define or execute project build tasks. Jenkins is an automation server that can orchestrate those tools as part of a wider pipeline. Jenkins does not replace every language-specific build tool.

### Manual vs. automated example

Manual approach:
1. A developer pulls the latest code.
2. Runs build commands.
3. Runs tests.
4. Packages the application.
5. Uploads the package.
6. Follows deployment steps.

Automated approach:
1. A developer pushes code to Git.
2. A CI system detects the change.
3. A pipeline runs the defined build and test steps.
4. If checks pass, the artifact is stored or promoted according to the release process.
5. The team receives the pipeline result.

Automation does not mean every change should automatically go to production. Approval gates and deployment policies can still be part of the workflow.

## 8. Day 1 — Complete Revision Summary

**Timestamp:** [00:58:50](https://www.youtube.com/watch?v=uHNOqKdqQas&t=3530s)

Remember these connections:

1. **SDLC** describes the full software journey: planning through maintenance.
2. **Modern delivery** emphasizes collaboration, smaller changes, automation, and fast feedback.
3. **Compiled and interpreted projects** have different build details, but both need repeatable validation and delivery.
4. **Non-containerized deployment** delivers an application artifact to an environment whose runtime must be prepared.
5. **Containerized deployment** delivers an image that packages the application and its user-space dependencies.
6. **Build automation** makes build and test steps consistent, repeatable, traceable, and faster.
7. **Jenkins** can orchestrate these steps; the project still uses language-specific tools to perform the actual build.

## 9. A Short Explanation You Can Say in an Interview or Revision

> “The Software Development Life Cycle is the complete process of building and maintaining software. It starts with planning and requirements, then design, development, build, testing, release, deployment, operations, monitoring, and maintenance. Modern software teams use Agile and DevOps practices to shorten feedback loops and improve collaboration between development and operations.
>
> In CI/CD, the build process depends on the application technology. A compiled project, such as Java, may compile source code into bytecode and package it as a JAR. An interpreted project, such as Python, usually sets up the required runtime, installs dependencies, and runs checks before packaging or deployment.
>
> Applications can be delivered as normal artifacts to a prepared server or as container images. Containers help make the application environment more consistent across stages. Build automation tools make tasks such as dependency installation, compilation, testing, and packaging repeatable. Jenkins can orchestrate these tools in an automated pipeline.”

Use this as a revision framework, not something to memorize word for word. Be ready to explain the examples in your own words.

## 10. Quick Self-Check

Try answering these without looking at the notes:

1. What does SDLC stand for, and why is it broader than coding?
2. What happens in the design, build, testing, deployment, and operations phases?
3. How do Agile and DevOps differ?
4. What is the typical Java source-to-runtime flow?
5. Why does a Python project still need CI even if it has no traditional compile step?
6. What is a build artifact? Give three examples.
7. What changes when an application is delivered as a container image?
8. Why should configuration and secrets be handled separately from a container image?
9. What problems can build automation reduce?
10. How is Jenkins different from Maven?

## 11. Day 1 Topic Checklist

- [x] Course introduction reviewed
- [x] Modern SDLC explained
- [x] SDLC phases and end-to-end view
- [x] Compiled vs. interpreted languages from a CI/CD perspective
- [x] Containerized vs. non-containerized build workflows
- [x] Compiled-language CI/CD workflow
- [x] Interpreted-language CI/CD workflow
- [x] Why build automation tools matter
- [x] Day 1 wrap-up

---

**Next section:** [Day 2 — CI/CD Concepts & Branching Strategies](../02-CI-CD-and-Branching-Strategies/)

**Course outline:** [All course chapters and timestamps](../Course-Outline.md)
