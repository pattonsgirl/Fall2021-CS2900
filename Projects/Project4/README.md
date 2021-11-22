# Project 4

- [Project Setup](#Project-Setup)
- [Project Description](#Project-Description)
- [Submission](#Submission)
- [Rubric](#Rubric)

## Objectives

- for two different container engines:
  - investigate networking options
  - investigate container vulnerability scanners

## Project Setup

Your deliverable for this project is once more documentation. You can use the below as a template of what your documentation needs.

This will look really slick if you start using markdown. For example:  
`$ something I want to look command liney`

```
some sample
output text
could go in this
```

Store screenshots in a folder in your repo, then refence them:
`![a photo could go here](../../Images/markdown-demo.png)`

![a photo could go here](../../Images/markdown-demo.png)

## Project Description

1. Investigate container networking.

   - For Docker, for example, there exists three networking modes - host, none, and bridge.
   - For the two engines of your choice (of which Docker can be one choice) state:
     - What networking mode(s) are supported and their capabilities
     - What networking mode is used by default
     - How to run the container and bind a host port to the container port

2. Investigate vulnerability scanners.

   - Find a Dockerfile linter (command line tool or VSCode plugin)
     - What best practices does it search for?
   - Find a scanner that can scan images for vulnerabilities
     - You can use [Aqua Trivy](https://aquasecurity.github.io/trivy/v0.21.0/) or something else
     - Does it have any limits on what can be scanned?
     - What types of vulnerabilities are scanned?

## Submission

1. Commit and push your changes to your repository. Verify that these changes show in your course repository, https://github.com/WSU-kduncan/cs2900-YOURGITHUBNAME

2. In Pilot, paste the link to your project folder. Sample link: https://github.com/WSU-kduncan/cs2900-YOURGITHUBUSERNAME/blob/main/Projects/Project4

## Rubric

[Rubric](Rubric.md)
