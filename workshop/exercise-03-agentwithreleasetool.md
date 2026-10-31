# Exercise 02: AI Release Readiness Agent with Tools

>**Duration:** 10 min  
>**Objective:** Wire the agent to its exact agent instructions and support tools <br>
>**Tech Showcase:** Agent invocation, tool calling, response validation

---

## Part 1: Exact System Prompt & Tool Contracts 

Create a new branch for this exercise to keep changes isolated from the main branch.

```bash
git switch -c feature/release-readiness-report
```

Enhance the existing AI Release Readiness Assistant with a structured release-readiness report

```
Enhance the existing AI Release Readiness Assistant with a structured release-readiness report.

Requirements:

- Use the existing build-status, test-results, and open-issues tools.
- Return these sections: Overall Status, Evidence, Blockers, and Recommended Next Steps.
- Mark the release BLOCKED if the build fails, any tests fail, or a critical issue is open; otherwise mark it READY based on the available checks.
- Base every finding on actual tool results. Never invent evidence.
- Preserve the existing Microsoft Foundry Agent Framework architecture, hosting protocol, entry point, tools, and dependency files.
- Do not add dependencies, external services, GitHub integrations, or deployment behavior.
- Add or update tests for the readiness decision logic where practical.
- Run the available tests and fix any failures.
Keep the change small and explain which files were modified.
```
Now you should have:

- Structured release-readiness report implemented
- Tests for the readiness decision logic exist

---

## Part 2: Run Agent Locally 

### Step 1: Invoke Agent with test messages

Once Copilot finishes, run the project using its existing startup command. In Agent Inspector, test these three prompts:

TEST A
```bash
Assess the latest Contoso Shop release and provide the structured report.
```
Expected: The agent provides a structured release-readiness report with sections for Overall Status, Evidence, Blockers, and Recommended Next Steps.


### Step 2: Commit Changes

Run the following commands to commit your changes:

```bash
git add .
git commit -m "Add structured release readiness report"
git push origin feature/release-readiness-report
```
---

### Step 3: Copilot Automated Code Review

Enable Copilot Automated Code Review for this repo.

Follow [Creating a branch protection rule](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/managing-a-branch-protection-rule#creating-a-branch-protection-rule) with:

- Require pull requests to automatically request Copilot code review, if available.
- After all, keep the Enforcement status to **Active**, and click on **Create rule**.

or manually assign Copilot code review to pull requests.

---

**Checklist:**

- [ ] Structured release-readiness report implemented
- [ ] Tests for the readiness decision logic exist
- [ ] Agent runs successfully with test messages

---

## Next Step

Move to **Exercise 03: [CI Generation](exercise-03-CIgeneration.md)**
