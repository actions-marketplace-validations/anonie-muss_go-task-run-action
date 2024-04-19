# go-task-run-action

Install task (https://taskfile.dev/) and run the specified tasks

## Input
```yaml
inputs:
  version:
    description: Version of task to install
    required: false
    default: "latest"
  tasks:
    description: "Tasks to run"
    required: true
```

## Usage
```yaml
name: Run checks

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  checks:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v4

    - name: checks
      uses: anonie-muss/go-task-run-action@latest
      with:
        tasks: install_tools checks
```


