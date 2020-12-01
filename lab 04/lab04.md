# Lab 03
## Introduction 
In lab we will explore the use of variables.

## Tasks
1. In addition to your existing YAML file add a second ".yml" for the template content.

## Template file content
```yaml
parameters:
    world: ''

jobs:
  - job: A
    displayName: First Job
    steps:
    - task: PowerShell@2
      inputs:
        targetType: 'inline'
        script: |
          # Write your PowerShell commands here.
          Write-Host "Hello $(world)"
          
  - job: B
    displayName: Second Job
    steps:
    - task: PowerShell@2
      inputs:
        targetType: 'inline'
        script: |
          # Write your PowerShell commands here.
          Write-Host "Hello ${{ parameters.world }}"
```

2. Modify your orginal file as follows

## Primary YAML file.  This will consume your template file.
```yaml
trigger:
- none

variables:
  world: the whole world

jobs: 
  - template: lab04-template.yml
    parameters: 
       world: A different kind of world!
```

3. Save and commit both files.
4. Ensure that your pipeline runs.

## How did the pipeline treat the variable **world** for each job?