# HELX GitHub Actions

Welcome to the HELX GitHub Actions repository! This repository hosts a collection of GitHub Actions designed specifically for use with the Human Environmental and Life eXploratory (HeLx) platform.

## How it Works

GitHub Actions are automated workflows that you can set up in your GitHub repository to streamline your development process. The actions provided in this repository are pre-configured to perform various tasks related to HELX development, such as building, testing, and deploying applications.
To use these actions in your repository, follow these steps:

1. **Choose an Action**: Contact the DevOps team for actions to be integrated into a repository.

2. **Add the Action to Your Workflow**: In your repository, create or edit a workflow file (e.g., `.github/workflows/code-checks.yml`) and specify the action you want to use along with any required parameters.

3. **Trigger the Workflow**: Define the events that should trigger the workflow, such as pushes to specific branches or pull request events.

4. **Commit and Push**: Commit the changes to your workflow file and push them to your repository.

5. **Monitor the Workflow**: GitHub will automatically run your workflow according to the triggers you specified. You can monitor the progress and view the results in the Actions tab of your repository.

## Things to Note

1. Repository secrets are NOT stored in this repository. They are not able to be stored for security reasons. The DevOps team control all of the secret accesses. Secrets can be transfered from your repository to helx-github-actions using

2. When testing actions, make sure to comment out certain paramaters so actions will run when changes are made. (e.g., only runs on pull requests or pushs on certain branches)

## Example

Here's a simple example of how to use an action from this repository in your workflow:

## In .yaml file

name: Example Workflow

on:
push:
branches: - main

jobs:
build:
runs-on: ubuntu-latest
steps: - name: Checkout repository
uses: actions/checkout@v2 - name: Example action usage
uses: helxplatform/helx-github-actions/action-name@main
secrets: inherit
with:
parameter1: value1
parameter2: value2
