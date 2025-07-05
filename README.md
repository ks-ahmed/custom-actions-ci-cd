# Custom Greeting GitHub Action

This GitHub Action is a simple custom action that greets a user and outputs the current time. It's designed to demonstrate how to build and use a custom JavaScript-based GitHub Action in a CI/CD pipeline.

## Project Overview

- **Name:** Custom Greeting Action  
- **Description:** Greets a user and returns the time the greeting occurred  
- **Language:** JavaScript (Node.js 20)  
- **Runtime:** GitHub Actions environment

---

## Inputs

| Input Name     | Required | Default | Description         |
|----------------|----------|---------|---------------------|
| `who-to-greet` | ✅ Yes   | `Hello` | Name to greet       |

---

## 📤 Outputs

| Output Name | Description         |
|-------------|---------------------|
| `time`      | Time of the greeting|

---

## Usage

To use this action in a GitHub Actions workflow, follow these steps:

### 1. Create or update a workflow file in `.github/workflows/greet.yml`:

```yaml
name: Custom Action CI

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps: 
    - name: checkout code
      uses: actions/checkout@main

    - name: Display greeting
      uses: ks-ahmed/custom-actions-ci-cd@main
      with:
        who-to-greet: "CoderCo Team"
    
    - name: Display greeting time
      run: echo "Greeted at ${{ steps.greet.outputs.time }}"
```

# Development Notes

  - This action uses @actions/core to handle input/output.
  - Make sure to run ncc build index.js if you're bundling dependencies.

# Install dependecnsies

`npm install`

# Optional: Build

`ncc build index.js --license licenses.txt`



