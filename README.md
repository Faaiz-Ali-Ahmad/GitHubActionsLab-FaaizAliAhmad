# GitHub Actions Lab - Faaiz

## Workflow 1: Dependent Jobs (build -> test -> deploy)
**Purpose:** Demonstrates job dependencies using `needs`.  
- The `build` job runs first.
- The `test` job waits for `build` to succeed.
- The `deploy` job waits for `test` to succeed.

**Key concepts:**
- `on: push` to trigger on pushes to `main`
- `runs-on` to define the runner environment
- `needs` to enforce job execution order

## Workflow 2: Multi-Platform Testing (Ubuntu, Windows, macOS)
**Purpose:** Demonstrates running multiple independent jobs in parallel across different OS runners.  
Each job:
- Checks out the repository using `actions/checkout@v4`
- Prints OS information
- Runs an OS-specific command
- Creates a file and prints its contents

**Key concepts:**
- `on: pull_request` to trigger on PRs to `main`
- No `needs` = jobs run in parallel
- `runs-on` for OS selection (ubuntu-latest, windows-latest, macos-latest)

## Challenges and Fixes
- **Hidden .github folder in IDE:** Created folders manually in NetBeans using New → Folder.
- **Windows commands differ from Linux/macOS:** Used PowerShell commands (`systeminfo`, `Out-File`, `Get-Content`) instead of `uname`/`cat`.
