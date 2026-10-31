# Exercise 04: Agent Evaluation

>**Duration:** 10 min  
>**Objective:** Evaluate the agent's functionality and performance <br>
>**Tech Showcase:** GitHub Actions, Automated Testing

---
## Part 1: Generate Agent Evaluation with Foundry

### Step 1: Generate Evaluation Suite 

In foundry tool kit, select *Developer Tools* -> *Monitor* and then choose *Evaluation* to generate a new evaluation suite for the agent.

### Step 2: Configure Evaluation Suite  

Configure the evaluation suite by selecting parameters like Intent resolution, Tool call, relevance, fluency and F1 score.

Select the suitable model and you can import existing evaluation cases or use sample cases provided by the tool.

## Part 2: Generate Agent Evaluation with GitHub Copilot

### Step 1: Generate Evaluation Suite

Generate an evaluation suite for the agent using the current project configuration and existing Foundry setup with Github Copilot.


```text
Implement an LLM-as-judge evaluation suite for my existing Microsoft Foundry AI Release Readiness Assistant.

Inspect the existing project, then create the files directly. 

Requirements:
1. Create an `evals/` folder containing a JSON dataset with 10 release-readiness test cases. Cover passed and failed builds, failed tests, critical issues, multiple blockers, no blockers, missing evidence, and conflicting or incomplete tool results.
2. Each case must include the input scenario, expected release status, expected blockers, and evidence the agent must report.
3. Create an evaluator script that runs the cases against the existing agent using the project's current Foundry configuration and evaluates the responses using the same deployed Foundry model as an LLM judge.
4. Score correctness, groundedness, safety, and relevance from 1–5. Save individual scores, explanations, and aggregate results to a JSON report.
5. Fail the evaluation if any safety score is below 4, any overall case score is below 3, or the average score for any dimension is below 4.
6. Keep the evaluation separate from the hosted agent's normal execution. Reuse existing dependencies, SDKs, endpoint configuration, and authentication where compatible. Do not hardcode credentials, print secrets, or add another model deployment.
7. Preserve the working agent, tools, hosting protocol, entry point, CI workflow, and existing tests. Do not add deployment behavior.
8. Add a short README with the exact command to run the evaluation, required environment variables, and how to interpret failures.

Run any feasible local validation, fix implementation errors, and summarize all files created or modified. If the current agent cannot be invoked programmatically with the existing configuration, implement the evaluator around the supported invocation path and clearly identify any remaining setup needed.

Make the smallest practical implementation. 

---

### Step 2: Verify Evaluation Cases

Run the evaluation cases using the exact command specified in the proposed evaluation plan.

```bash
python evals\run_evaluation.py
```
---

## Part 2: Agent Evaluation CI

### Step 1: Configure CI for Agent Evaluation with GitHub Copilot

Create a GitHub Actions workflow to run the agent evaluation automatically for pull requests and pushes to the main branch. Use GitHub Copilot to assist in generating the workflow YAML file if needed. Ensure the workflow installs dependencies, sets up the environment, and executes the evaluation command specified in the evaluation README.

```text
Create a separate GitHub Actions workflow named `.github/workflows/run-agent-evals.yml` for my existing LLM-as-judge evaluator.

First inspect the actual evaluator script, evaluation dataset, dependency files, and existing `ci.yml`. Use the real paths and commands from the repository.

Requirements:

- Add a `workflow_dispatch` trigger so I can run evaluations manually.
- Set up Python using the project's compatible version and install dependencies using its existing dependency configuration.
- Run the evaluator script and preserve its non-zero exit code when evaluation thresholds fail.
- Use GitHub Actions secrets or variables for the existing Foundry endpoint, model deployment configuration, and authentication as required by the evaluator. Never hardcode credentials.
- Do not assume secret names or authentication requirements; document the exact values that must be configured based on the existing code.
- Upload the generated evaluation JSON report as a workflow artifact, including when evaluation fails, if the report exists.
- Add a reasonable timeout and avoid printing credentials.
- Do not modify `ci.yml`, the agent implementation, or the evaluation logic.
- Do not deploy the agent.
- Add comments explaining how to enable pull-request evaluation as a merge gate after Azure access and credentials are restored.
- Validate the YAML and summarize the files changed.
Create the workflow now; do not stop at analysis.
```

Now go to actions in your GitHub repository to verify that the new workflow appears and can be triggered manually. Check the workflow run logs to ensure it executes the evaluation correctly and uploads the report as an artifact.

---

**Checklist:**

- [ ] Agent evaluation workflow runs successfully and uploads the evaluation report as an artifact
- [ ] Manual trigger for the agent evaluation workflow works correctly
- [ ] Evaluation cases run successfully and produce expected results

---

## Next Step

Move to **Exercise 05: [Agent UI](exercise-05-web-ui-optional.md)**
