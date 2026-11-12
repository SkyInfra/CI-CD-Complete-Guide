# CI/CD Complete Guide

A practical, beginner-friendly guide to **Continuous Integration (CI), Continuous Delivery/Deployment (CD), Jenkins, and automated software delivery**.

This repository is my learning journal and hands-on reference as I work through CI/CD concepts and build practical Jenkins pipelines. The goal is not just to collect commands, but to understand how each part works, why teams use it, and how it fits into a real software delivery workflow.

> **Status:** Learning in progress  
> **Primary focus:** CI/CD with Jenkins  
> **Environment:** macOS (MacBook Air), with Linux and cloud-based labs where needed

---

## What you'll find here

The repository is organized by topic so that concepts, setup instructions, integrations, and practical exercises are easy to find.

| Section | What it covers |
| --- | --- |
| [01 – CI/CD Fundamentals](./01-CI-CD-Fundamentals/) | CI, Continuous Delivery vs. Continuous Deployment, pipelines, and the software delivery lifecycle |
| [02 – Jenkins Fundamentals](./02-Jenkins-Fundamentals/) | Jenkins overview, architecture, installation, dashboard, and initial configuration |
| [03 – Jenkins Pipelines](./03-Jenkins-Pipelines/) | Jobs, pipeline concepts, Declarative and Scripted Pipelines, Jenkinsfiles, stages, and steps |
| [04 – Jenkins Integrations](./04-Jenkins-Integrations/) | GitHub integration, webhooks, credentials, Docker, and related tools |
| [05 – Practical Labs](./05-Practical-Labs/) | Hands-on exercises: first job, automated builds, CI pipeline, and deployment workflow |
| [06 – Advanced Concepts](./06-Advanced-Concepts/) | Agents, distributed builds, pipeline optimization, and Jenkins security |
| [Resources](./Resources/) | Useful commands, troubleshooting notes, references, and interview preparation |

*Sections and files will be added as I progress through the learning plan.*

---

## Learning approach

Each topic will be documented in my own words and, where useful, will include:

1. **The idea** – a clear explanation of the concept.
2. **Why it matters** – the problem it solves in a development team.
3. **How it works** – the workflow and important components.
4. **A practical example** – a realistic scenario to connect theory with practice.
5. **Commands and configuration** – explained in context, not just pasted.
6. **Common mistakes** – issues I encounter and how to troubleshoot them.
7. **Evidence** – screenshots or output from completed labs when relevant.

The notes are intended to be useful both while learning and when revisiting a topic later.

---

## Planned learning path

```text
CI/CD Fundamentals
       |
       v
Jenkins Fundamentals
       |
       v
Jenkins Jobs and Pipelines
       |
       v
GitHub, Webhooks, Credentials and Docker
       |
       v
Build, Test and Deployment Labs
       |
       v
Agents, Security and Optimization
```

This is a working roadmap, not a claim that every topic or lab is already complete. The structure may evolve as the learning plan develops.

---

## Tools and technologies

The main focus is Jenkins and the practices around it. The tools used in individual labs may include:

- **Jenkins** – automation server for building delivery pipelines
- **Git and GitHub** – source control and repository hosting
- **Docker** – containerizing applications and build environments
- **Linux and shell scripting** – commands and automation used in CI/CD
- **AWS** – cloud infrastructure for deployment-related practice, where appropriate

A tool will be added to the practical workflow when the topic requires it.

---

## Repository structure

```text
CI-CD-Complete-Guide/
├── 01-CI-CD-Fundamentals/
├── 02-Jenkins-Fundamentals/
├── 03-Jenkins-Pipelines/
├── 04-Jenkins-Integrations/
├── 05-Practical-Labs/
├── 06-Advanced-Concepts/
├── Resources/
└── README.md
```

---

## Learning source

This learning journey is based in part on a Jenkins and CI/CD tutorial by **Josh (Cloud with Josh / Precode Camp)**, alongside my own practice, notes, and additional research.

The documentation here is written in my own words. It is intended as a companion learning resource, not a transcript or reproduction of the tutorial.

---

## Progress

- [ ] Review CI/CD fundamentals
- [ ] Set up Jenkins locally
- [ ] Explore Jenkins dashboard and configuration
- [ ] Create the first Jenkins job
- [ ] Build a pipeline using a Jenkinsfile
- [ ] Connect a GitHub repository and configure a webhook
- [ ] Integrate Docker into a pipeline
- [ ] Complete an automated build and deployment lab
- [ ] Study Jenkins agents, security, and optimization

Progress will be updated as each topic and lab is completed.

---

## Author

**SkyInfra**  
Software Engineering student | Cloud & DevOps learner

GitHub: [@SkyInfra](https://github.com/SkyInfra)

---

If you are also learning CI/CD or Jenkins, feel free to explore the notes, try the labs, and share suggestions or improvements.
