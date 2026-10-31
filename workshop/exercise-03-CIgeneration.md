# Exercise 03: CI and Security Checks

>**Duration:** 10 min  
>**Objective:** Create CI, Code Quality, and Security checks <br>
>**Tech Showcase:** GitHub Actions, CI/CD, Code Scanning, Secret Scanning

---

## Part 1: Inspect and create CI

### Step 1: Inspect the Repository

Before creating CI, it's important to understand the current state of the repository, including its structure, dependencies, and existing workflows. This will help ensure that the CI setup aligns with the existing project configuration.

In Copilot, inspect the repository to understand its structure and the existing setup before adding CI.

```text
Inspect my existing Microsoft Foundry AI Release Readiness Assistant repository. Do not modify any files yet.

Identify:
1. The agent entry point and its existing tools.
2. The Python version, dependency manager, and dependency files (`requirements.txt`, `pyproject.toml`, or both).
3. The exact dependencies and commands needed to install the project.
4. Existing tests and the correct command to run them.
5. Existing GitHub Actions workflows and Foundry deployment configuration.

Recommend the smallest suitable GitHub Actions CI workflow for pull requests and pushes to the main branch.

If the project uses requirements.txt, explain that setup. If it uses pyproject.toml, inspect its build-system, dependencies, and any tool-specific configuration before recommending installation commands. If both files exist, determine their roles before choosing a setup.

Preserve the existing Microsoft Foundry Agent Framework architecture and working tools. Do not add dependencies, change manifests, or create files yet.

Return the findings, the recommended commands, and any assumptions that need verification.
```

Depending on Project.toml or requirements.txt, copilot should recommend the appropriate installation commands and CI setup, review the inspection findings, and ensure the recommendations align with the existing project structure and dependencies.

---

### Step 2: Verify CI  

Go to your GitHub repository and select the Actions tab. Look for the workflow named CI.
Verify that it runs successfully for PRs and pushes to the main branch.
If it fails, inspect the workflow logs to identify and fix any issues with Copilot.

---

## Part 2: Code Quality and Security Checks

### Step 1: Code Scanning

From Github.com, navigate to your repository and select the Security & Quality tab. 
Enable the available code scanning with default code QL configuration.

Verify that the code scanning is enabled and configured correctly. You should see a workflow for code scanning in the Actions tab of your repository.

### Step 2: Secret Scanning

From Github.com, navigate to your repository and select the Security & Quality tab.
Enable the available secret scanning feature.

Verify that secret scanning is enabled and configured correctly. You should see alerts for any detected secrets in your repository.

### Step 3: Verify Code Scanning Workflow Updates

From the Actions tab of your repository, locate the workflow responsible for code scanning.
Verify that it runs successfully for pull requests and pushes to the main branch.
If it fails, inspect the workflow logs to identify and fix any issues.

---

**Checklist:**

- [ ] CI workflow runs successfully for PRs and pushes to the main branch
- [ ] Code scanning workflow runs successfully for PRs and pushes to the main branch
- [ ] Secret scanning is enabled and configured correctly

---

## Next Step

Move to **Exercise 04: [Agent Evaluation](exercise-04-agentevaluation.md)**
