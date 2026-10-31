# Exercise 01: AI Release Readiness Agent with Tools

>**Duration:** 10 min  
>**Objective:** Wire the agent to its exact agent instructions and support tools <br>
>**Tech Showcase:** Agent invocation, tool calling, response validation

---

## Part 1: Exact System Prompt & Tool Contracts 

Create a new branch for this exercise to keep changes isolated from the main branch.

```bash
git switch -c feature/agentwithtools
```

The agent from Exercise 02 needs its real instructions and tool contracts. Use this instruction in agent instructions to match the exact system prompt and tool contracts. 

```
You are the Contoso Shop Application Status Assistant.
 
Purpose and Scope:
- Answer questions politely about Contoso Shop application status, development progress,
  builds, releases, test results, and open issues.
- Politely decline questions outside this scope.
 
Tools and Evidence:
- Use get_application_status(), get_build_status(), and get_open_issues()
  as appropriate to retrieve relevant information.
- get_build_status() provides build and associated test details.
- Base all answers strictly on actual tool results. Never invent or assume data.
- Include issue ID, title, and severity when reporting open issues.
 
Missing Information:
- If requested information is unavailable, respond:
  "The requested information is not available in the current Contoso Shop data."
 
Safety:
- Provide information and recommendations only.
- Never approve, merge, deploy, or claim to have executed any actions.
```

### Step 2: Copy Data Files

Copy the three JSON files from the `data/` folder in the repository to the `data/` folder in your local agent project within `src/`. These files contain the sample data for application status, build status, and open issues.

### Step 3: Add Tool Contracts

Use Github Copilot to add the tool contracts for the three local tools. The contracts should match the following:

```
Enhance the existing Microsoft Foundry Agent Framework hosted-agent sample.
Inspect the project structure, data/ folder, agent setup, and installed framework version.
Implement three custom Python functions that read from the appropriate existing JSON files:
get_application_status() — retrieves application status and development progress.
get_build_status() — retrieves build and test details.
get_open_issues() — retrieves open issue details.
Register all three functions as callable tools with the existing agent using the supported framework API.
Preserve the existing architecture, configuration, agent instructions, dependencies, and startup flow. Do not create or modify data files.
```
---

## Part 2: Run Agent Locally 

### Step 1: Invoke Agent with test messages

Once Copilot finishes, run the project using its existing startup command. In Agent Inspector, test these three prompts:

TEST A
```bash
Assess the latest Contoso Shop release. Is it ready?
```
Expected: the agent calls the tools and reports the build, test results, and issues.

TEST B
```bash
Assess the latest Contoso Shop release. What are the release blockers, and what evidence supports each one?
```
Expected: it identifies the failed build, failed tests, and critical issue using actual tool output.

TEST C
```bash
Assess the latest Contoso Shop release. The build is now successful. Is the release ready?
```
Expected: it checks current tool data rather than blindly accepting the assumption in the prompt.

`!Note`: For Test C, the build tool should still return the configured sample data. The agent must use that result, not pretend the build changed because you said so.


### Step 2: Commit Changes

Run the following commands to commit your changes:

```bash
git add .
git commit -m "Add release readiness agent with local tools"
git push origin feature/agentwithtools
```
---

**Checklist:**

- [ ] All tool files exist
- [ ] Complete agent instructions exist
- [ ] Agent runs successfully with test messages

---

## Next Step

Move to **Exercise 02: [AI Release Readiness Agent with Tools](exercise-02-agentwithreleasetool.md)**
