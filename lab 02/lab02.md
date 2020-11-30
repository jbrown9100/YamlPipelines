# Lab 02
## Introduction 
In lab we will explore the use of variables.

## Tasks
1. In your repository create a branch called <b>lab02</b> from lab01.
2. Make lab02 your working branch.
3. Create a second yaml file and add the following content.

```yaml
trigger:
- lab02

variables:
  world: the whole world

steps:
- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: |
      # Write your PowerShell commands here.
      Write-Host "Hello $(world)"
```

4. Save and commit your change.

## Will the pipeline run automatically? Why or why not?

5. Ensure that your pipeline runs.
6. What was the message displayed in the log from the Write-Host command?