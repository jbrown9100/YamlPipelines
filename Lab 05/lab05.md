# Lab 05
## Introduction 
In lab we will explore the use of stages.

## Tasks
1. In the primary YAML file add the following stages sections.
2. Modify your orginal file as follows

```yaml
trigger:
- none

variables:
  world: the whole world

stages:
  - stage: Build
    jobs: 
      - template: lab04-template.yml
        parameters: 
          world: A different kind of world!
  
  - stage: Deploy
    jobs:
      - deployment: scriptDeploy
        displayName: Run my script
        environment: 'Dev'
        strategy:
          runOnce:
            deploy:
              steps:
                - task: PowerShell@2
                  inputs:
                    targetType: 'inline'
                    script: |
                      # Write your PowerShell commands here.
                      Write-Host "Hello $(world)"
```

3. Save and commit both files.
4. Ensure that your pipeline runs.

## How did the pipeline treat the variable **Stages**?