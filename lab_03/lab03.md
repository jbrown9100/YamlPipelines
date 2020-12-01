# Lab 03
## Introduction 
In lab we will explore the use of jobs.

## Tasks
1. Modify your YAML file to add your jobs as seen below.

```yaml
trigger:
- none

variables:
  world: the whole world

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
    variables:
      world: traditional world
    steps:
    - task: PowerShell@2
      inputs:
        targetType: 'inline'
        script: |
          # Write your PowerShell commands here.
          Write-Host "Hello $(world)"
```

2. Save and commit your change.
3. Ensure that your pipeline runs.
4. What was the message displayed in the log from each of the Write-Host commands?


## Will the pipeline run automatically? Why or why not? What modification would cause the pipeline to auto-**trigger**?
## How did each of the jobs run? In what order?
## How did the pipeline treat the variable **world** for each job?