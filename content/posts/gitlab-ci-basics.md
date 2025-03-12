---
title: "Gitlab CI Basics"
date: 2025-03-12T08:33:21+01:00
draft: false
---

# Getting Started with GitLab CI: The Basics

GitLab CI is a powerful tool that helps automate your software development workflows. It integrates directly with GitLab repositories, making it easy to set up continuous integration and continuous deployment (CI) pipelines.

In this article, you'll learn the basics of GitLab CI, including how to define and run a simple pipeline using `.gitlab-ci.yml`.

## What is GitLab CI?

GitLab CI automates the process of building, testing, and deploying code. It follows a pipeline-based approach where each change goes through multiple stages before being deployed to production.

Key concepts:
- **Pipeline**: A set of jobs executed in a sequence or in parallel.
- **Jobs**: Individual tasks such as building code, running tests, or deploying.
- **Stages**: Groups of jobs that run sequentially (e.g., `build`, `test`, `deploy`).
- **Runners**: Compute instances that execute jobs.

## Setting Up GitLab CI

To enable CI in your GitLab repository, create a `.gitlab-ci.yml` file at the root of your project. This file defines the pipeline configuration.

### A Simple GitLab CI Pipeline

Create a `.gitlab-ci.yml` file with the following content:

```yaml
stages:
  - build
  - test
  - deploy

build-job:
  stage: build
  script:
    - echo "Building the application"
    - mkdir build
    - touch build/app

test-job:
  stage: test
  script:
    - echo "Running tests"
    - exit 0  # Simulate passing tests

deploy-job:
  stage: deploy
  script:
    - echo "Deploying the application"
  only:
    - main  # Deploy only when changes are pushed to the main branch
```

### Explanation of the Pipeline
1. **`stages`**: Defines three stages: `build`, `test`, and `deploy`.
2. **`build-job`**:
   - Runs in the `build` stage.
   - Simulates building an application.
3. **`test-job`**:
   - Runs in the `test` stage.
   - Simulates running tests.
4. **`deploy-job`**:
   - Runs in the `deploy` stage.
   - Executes only when changes are pushed to the `main` branch.

## Running the Pipeline

When you push your changes to GitLab, the pipeline automatically starts. You can check the status of your jobs under **CI > Pipelines** in GitLab.

## Adding a Docker Runner

To run CI jobs, GitLab uses **runners**. If you're using GitLab SaaS, shared runners are available. For self-managed GitLab, install a runner:

```bash
# Install GitLab Runner
curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh | sudo bash
sudo apt install gitlab-runner

# Register the runner
sudo gitlab-runner register --url https://gitlab.com/ --registration-token YOUR_TOKEN
```

## Conclusion

GitLab CI simplifies software development by automating build, test, and deployment workflows. With a basic `.gitlab-ci.yml`, you can set up a pipeline and ensure code quality. 
