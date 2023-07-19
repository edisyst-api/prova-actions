# prova-actions

name: Greetings su una issue nuova

on: [pull_request_target, issues]

jobs:
  greeting:
    runs-on: ubuntu-latest
    permissions:
      issues: write
      pull-requests: write
    steps:
    - uses: actions/first-interaction@v1
      with:
        repo-token: ${{ secrets.GITHUB_TOKEN }}
        issue-message: "Messaggio che viene displayed on users' first issue"
        pr-message: "Message that will be displayed on users' first pull request"
