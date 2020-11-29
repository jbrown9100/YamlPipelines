# Introduction 
In lab one we will create the basis for our yaml pipeline.

# Lab 01
1. In your repository create a branch called lab01.
2. Make lab01 your working branch.
3. Add a file with the ".yml" extension in your branch and add the following content to the file.

```yaml
trigger:
- none

steps:
- task: PowerShell@2
  inputs:
    targetType: 'inline'
    script: |
      # Write your PowerShell commands here.
      Write-Host "Hello World"
```