# Exercise 01: Foundry Toolkit Setup & Agent Scaffold

>**Duration:** 15 min  
>**Objective:** Use Foundry Toolkit to scaffold the agent project locally  
>**Tech Showcase:** Foundry Toolkit CLI

---

## Part 1: Foundry Toolkit Installation 

### Step 1: Install Foundry Extension 

In VS Code Extension Marketplace `ctrl+shift+x`, search for and install the **Foundry Toolkit** extension.

Then:
- Open Foundry Toolkit panel (left sidebar)
- Sign in with Azure account

---
## Part 2: Agent Scaffold

### Step 1: Create or connect to foundry resource

**In Foundry Toolkit panel:**
1. Select **My Resources** section,
2. Click **"Settings"** button
3. Select **"Switch Project"** to select existing or create a new foundry project

### Step 2: Create Agent with Developer Tools

**In Foundry Toolkit panel:**
1. Scroll to **Developer Tools** section
2. Click **"+ Create Agent"** button
3. Select **"Agent framework"** card
4. Enter Project Name and Model (e.g., "IT Support Agent" and "GPT-4")

This will scaffold the agent project with the specified name and model.
It includes basic agent scaffolding with the necessary files and structure to start development.


### Step 3: Setup and Run Agent 

Set the environment variables for your Foundry project and Azure AI model deployment:

```bash
azd env set AZURE_AI_MODEL_DEPLOYMENT_NAME <your_azure_ai_model_deployment_name>
azd env set FOUNDRY_PROJECT_ENDPOINT <your_foundry_project_endpoint>
```
Create a new environment named `dev` (or any preferred name) for your project.

```bash
az login
azd ai agent run
```

You should see the agent running successfully.

### Step 4: Test the Agent

Foundry Toolkit: Open Agent Inspector, then send a chat message.
Or via azd CLI in a second terminal (same folder): azd ai agent invoke --local "Hi"

### Step 5: Commit Changes

After verifying that the agent runs successfully, add `**gitignore**` and commit your changes to your version control system:

```bash
git add .
git commit -m "Initial scaffold of basic Agent"
git push origin main
```
---

**Checklist:**
- [ ] Foundry Toolkit installed and signed in
- [ ] Foundry project created or connected
- [ ] Agent scaffold created and running successfully
 

---

## Next Step

Move to **Exercise 03: [Add AI Release Readiness Assistant](exercise-03-agentwithtools.md)**