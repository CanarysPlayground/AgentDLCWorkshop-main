# AI Release Readiness Agent Workshop

## The Agent You Will Build

Imagine a release manager at Contoso Shop who must decide, before each release, whether the build is safe to ship. Today that means checking the CI dashboard, the test reports, and the issue tracker by hand, then writing a summary for stakeholders.

The AI Release Readiness Assistant automates that review. Over the workshop you will build an agent that:

1. **Gathers evidence** by calling local tools for build status, test results, and open issues.
2. **Assesses readiness** based only on those tool results, never on invented data.
3. **Reports clearly** with an Overall Status, Evidence, Blockers, and Recommended Next Steps.
4. **Hands the decision back to humans**, recommending actions without approving, merging, or deploying.

By the end, you will have a tool-grounded agent that is structured, tested, reviewed through GitHub, protected by CI and security checks, and measured with Foundry evaluations.

## Workshop Story

| Step | Exercise | What you do | Platform focus |
| --- | --- | --- | --- |
| 1 | [Foundry Toolkit Setup & Agent Scaffold](exercise-00-foundryagentsetup.md) | Connect to a Foundry project, scaffold an agent, run it locally, and try it in Agent Inspector. | Microsoft Foundry Toolkit |
| 2 | [AI Release Readiness Agent with Tools](exercise-01-agentwithtools.md) | Add the agent instructions and local tools for build status, test results, and open issues. Verify that its findings come from tool results. | Foundry Agent Framework and GitHub Copilot |
| 3 | [Structured Release Readiness Report](exercise-02-agentwithreleasetool.md) | Ask the agent to return Overall Status, Evidence, Blockers, and Recommended Next Steps; add tests for readiness logic where practical. Enable Copilot code review for pull requests. | GitHub Copilot and GitHub pull requests |
| 4 | [CI and Security Checks](exercise-03-CIgeneration.md) | Inspect the repository, create and verify CI for pull requests and pushes, and enable the available code and secret scanning features. | GitHub Actions and GitHub security |
| 5 | [Agent Evaluation](exercise-04-agentevaluation.md) | Create an evaluation suite in Foundry Toolkit, then use Copilot to create an LLM-as-judge evaluation for release-readiness cases. | Foundry evaluation and GitHub Copilot |
| 6 | [Web UI](exercise-05-web-ui-optional.md) (Optional)  | Add a FastAPI backend and React chat interface for the deployed agent. It is an optional extension, separate from the core sequence. | FastAPI and React |


### Prerequisites

- [VS Code](https://code.visualstudio.com/)
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
- [Azure Developer CLI](https://learn.microsoft.com/en-us/azure/developer/azure-developer-cli/install-azd)
- [Git](https://git-scm.com/downloads)
- [Foundry Toolkit extension](https://marketplace.visualstudio.com/items?itemName=ms-windows-ai-studio.windows-ai-studio)
- [GitHub Copilot](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot)
- [Python 3.12 or later](https://www.python.org/downloads/)
- [Node.js and npm](https://nodejs.org/en/download/)

## Getting Started

Start with [Exercise 01](exercise-01-Repocreation&Advancesecurity.md) to create your repository and enable advanced security checks. Then follow the exercises in order to build, test, and enhance your agent.


## What the Workshop Demonstrates

- **Build an agent in Foundry:** Start from the Foundry Toolkit scaffold and use its agent development and inspection experience.
- **Ground responses in tools:** Add local tools for build status, test results, and open issues. The agent must report actual results, identify blockers, and avoid inventing evidence.
- **Shape a useful agent response:** Return a structured readiness report and cover readiness decision logic with tests where practical.
- **Use GitHub in the development workflow:** Work with branches and pull requests, request Copilot code review, and configure GitHub Actions CI.
- **Add repository checks:** Enable available code scanning and secret scanning, then verify the relevant workflow runs.
- **Evaluate agent quality:** Configure Foundry evaluation metrics and build a separate Copilot-assisted LLM-as-judge evaluation for release-readiness scenarios.

