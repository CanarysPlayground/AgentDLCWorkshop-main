# Exercise 01: Repository Creation & Advanced Security

>**Duration:** 10 min  
>**Objective:** Set up repository and advanced security checks <br>
>**Tech Showcase:**  Code Scanning, Secret Scanning

---

## Part 1: Repository Setup

### Step 1: Create Repository

Use this repository template [Agent SDLC Workshop](https://github.com/CanarysResources/AgentDLCWorkshop/generate) to create your own copy of the workshop repository.

Save it as `**public repository**` with a name of your choice. Clone your repository locally and navigate to its directory before proceeding with the exercises. 

Repository contains Workshop exercises and fictional Contoso Shop release data. Follow the instructions in each exercise sequentially to progressively build, test, and enhance your agent throughout the workshop.

---

## Part 2: Enable Advanced Security Checks

### Step 1: Code Scanning

From Github.com, navigate to your repository and select the Security & Quality tab. 
Enable the available code scanning with default code QL configuration.

Verify that the code scanning is enabled and configured correctly. You will see a workflow for code scanning in the Actions tab of your repository.

### Step 2: Secret Scanning

From Github.com, navigate to your repository and select the Security & Quality tab.
Enable the available secret scanning feature.

Verify that secret scanning is enabled and configured correctly. You will see alerts for any detected secrets in your repository.

---

## Part 3: Local Environment Setup

Verify prerequisites are installed:

```bash
# Check Python
python --version              # 3.10+

# Check Azure CLI
az --version                  # 2.50+

# Check azd (Azure Developer CLI)
azd version                   # Required for Foundry Toolkit

# Verify git
git --version                 # 2.36+

```

---

**Checklist:**

- [ ] Repository created from template and cloned locally
- [ ] Code scanning and secret scanning enabled and verified
- [ ] Local environment verified with Python, Azure CLI, azd, and git installed

---

## Next Step

Move to **Exercise 02: [Foundry Toolkit Setup & Agent Scaffold](exercise-02-foundryagentsetup.md)**
