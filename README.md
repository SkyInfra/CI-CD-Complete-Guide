# CI/CD Complete Guide

A hands-on learning repository documenting my journey from **modern software delivery fundamentals to production-oriented Jenkins and DevSecOps pipelines**.

I'll use this repository to build clear notes, understand the reasoning behind each tool, and record practical labs as I work through the course. The goal is to understand how the pieces fit together—not simply collect commands.

> **Status:** Learning in progress  
> **Main focus:** Jenkins, CI/CD, Docker, Maven, SonarQube, and DevSecOps  
> **Working environment:** macOS (MacBook Air) and Ubuntu/AWS environments when required

## Course roadmap

The learning path follows the course chapters in [Course Outline](./Course-Outline.md), with timestamps linked directly to the video.

| Section | Main topics |
| --- | --- |
| Day 1 — Modern SDLC & Build Automation | SDLC, Agile/DevOps, compiled vs. interpreted languages, build workflows |
| Day 2 — CI/CD & Branching | CI, CT, Continuous Delivery/Deployment, Git, GitFlow, trunk-based development, image promotion |
| Day 3 — Jenkins Basics | Jenkins architecture, installation options, Docker-based setup |
| Day 4 — Freestyle Jobs | JENKINS_HOME, controller vs. agents, practical jobs |
| Day 5 — Dockerized Flask CI/CD | Docker-outside-of-Docker, build, push, and deploy workflow |
| Day 6 — Jenkins Pipelines | Pipeline fundamentals and production-style Jenkinsfile |
| Day 7 — Multibranch Pipelines | Branch discovery and trunk-based CI/CD |
| Maven | Build tools, pom.xml, lifecycle, plugins, Jenkins integration |
| SonarQube & DevSecOps | Code quality, SAST, DAST, SCA, SBOM, security pipeline |
| DevSecOps Mega Project | Jenkins controller/agent, Trivy, SonarQube, ECR, image build and deployment |
| Jenkins Shared Libraries | Reusable pipeline code, library structure, private Git repositories |

## How I document each topic

Each set of notes will aim to include:

1. **Concept:** what it is, explained in beginner-friendly language.
2. **Why it matters:** the real engineering problem it solves.
3. **How it works:** components, flow, and architecture.
4. **Practical example:** a realistic scenario.
5. **Commands and configuration:** with explanations and expected results.
6. **Troubleshooting:** errors, causes, and fixes encountered during practice.
7. **Evidence:** screenshots or terminal output for completed labs.

I'll write the notes in my own words and distinguish explanations from actual lab results. A topic will only be marked complete after I have studied it; a lab will only be marked complete after I have run and verified it.

## Planned repository structure

```text
CI-CD-Complete-Guide/
├── 01-Modern-SDLC-and-Build-Automation/
├── 02-CI-CD-and-Branching-Strategies/
├── 03-Jenkins-Basics-and-Installation/
├── 04-Jenkins-Freestyle-Jobs/
├── 05-Dockerized-Flask-CI-CD-Project/
├── 06-Jenkins-Pipelines/
├── 07-Multibranch-Pipelines/
├── 08-Maven-for-DevOps/
├── 09-SonarQube-and-DevSecOps/
├── 10-DevSecOps-Mega-Project/
├── 11-Jenkins-Shared-Libraries/
├── Resources/
├── Course-Outline.md
└── README.md
```

Folders and notes will be added as the learning work progresses.

## Tools covered

- **Jenkins** — automation server and pipeline orchestration
- **Git & GitHub** — version control, collaboration, and source triggers
- **Docker** — reproducible build and runtime environments
- **Maven & Java** — application build lifecycle and dependency management
- **SonarQube** — code quality and static analysis
- **Trivy** — filesystem and container image vulnerability scanning
- **Amazon ECR / AWS** — container image storage and cloud deployment labs
- **Linux & shell scripting** — the environment and commands behind automation

## Learning source

This repository follows the chapter sequence of **Jenkins Basics to Production** by **Josh (Cloud with Josh / Precode Camp)**. It is a personal learning companion: explanations, examples, configurations, and lab evidence will be documented in my own words rather than copied as a transcript.

## Progress tracker

- [ ] Day 1 — Modern SDLC and Build Automation
- [ ] Day 2 — CI/CD Concepts and Branching Strategies
- [ ] Day 3 — Jenkins Basics and Installation
- [ ] Day 4 — Jenkins Freestyle Jobs
- [ ] Day 5 — Dockerized Flask CI/CD Project
- [ ] Day 6 — Jenkins Pipelines
- [ ] Day 7 — Multibranch Pipelines
- [ ] Maven for DevOps
- [ ] SonarQube and DevSecOps
- [ ] DevSecOps Mega Project
- [ ] Jenkins Shared Libraries

## Author

**SkyInfra** — Software Engineering student | Cloud & DevOps learner  
GitHub: [@SkyInfra](https://github.com/SkyInfra)
