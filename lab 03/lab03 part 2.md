# Lab 03
## Introduction 
In lab we will explore the use of jobs.

## Tasks
1. Add a dependency to **job B** on **job A**

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
    dependsOn: A
    condition: succeeded()
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

## How did each of the jobs run? In what order?