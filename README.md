# Introduction 
Learn the basics of Azure DevOps YAML pipelines

# Getting started
## YAML pipelines in Azure DevOps Lab one
For lab one we will create the beginning shell of a YAML pipeline.
The key components of the YAML pipeline structure are:

The triggers represents the means by which the pipeline is activated. it comes in the forms of 
1. triggers - branch triggers
- attributes are branches, tags and paths.  The attributes can be combined and each has the sub-attributes of include or exclude.
```yaml
trigger:
- master
- develop
```
- PR - pull request triggers

```yaml
pr:
- master
- develop
```
- Schedules - on a schedule based on cron syntax

|Unit|Values|
|----|-----|
|Minutes	|0 through 59|
Hours	|0 through 23|
Days	|1 through 31
Months	|1 through 12, full English names, first three letters of English names
Days of week	|0 through 6 (starting with Sunday), full English names, first three letters of English names

```yaml
schedules:
- cron: "0 0 * * *"
  branches:
    include:
    - releases/*
```