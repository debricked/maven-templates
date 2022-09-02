<img src="https://debricked.com/build/images/blueLogo.d39f7709.svg" alt="debricked" width="50%"  align="top"/>  

# Maven templates
Here you find templates for integrating your Maven repository with us.

In order for us to analyse all dependencies in your Maven project, a file containing the resolved dependency tree has to be created prior to scanning.

This can be done by running the Maven `dependency:tree` plugin and storing the output in a file called `.debricked-maven-dependencies.tgf`.  
All examples in this repository generate that tree file.  
The command that is run prior to scanning is:
```sh
mvn dependency:tree -DoutputFile=.debricked-maven-dependencies.tgf -DoutputType=tgf
```
### Performance tip
Does your `.debricked-maven-dependencies.tgf` take a long time to create?  
Make sure to **cache** `.debricked-maven-dependencies.tgf` or the [Maven local repository](https://www.baeldung.com/maven-local-repository#Repository) between runs where your build is the same!

Different CI/CD tools offer different support for this. Below you can find docs on how set this up:
- GitHub Actions: [docs](https://github.com/actions/cache)
- CircleCI: [docs](https://circleci.com/docs/2.0/caching/)
- BuildKite: [docs](https://github.com/buildkite/maven-example) (In BuildKite docker volumes comes in handy)
- GitLab CI/CD: [docs](https://docs.gitlab.com/ee/ci/caching/)
- Azure Pipelines: [docs](https://docs.microsoft.com/en-us/azure/devops/pipelines/release/caching?view=azure-devops#maven)

## GitHub Actions [![Debricked scan](https://github.com/debricked/example-maven-integration/actions/workflows/debricked.yml/badge.svg)](https://github.com/debricked/example-maven-integration/actions/workflows/debricked.yml)
- Add Debricked token variable. [Read more](https://debricked.com/docs/integrations/ci-build-systems/github.html#github-actions)
- [See template](.github/workflows/debricked.yml)

## CircleCI [![CircleCI](https://circleci.com/gh/debricked/maven-templates/tree/main.svg?style=svg)](https://circleci.com/gh/debricked/maven-templates/tree/main)
- Add Debricked token variable. [Read more](https://debricked.com/docs/integrations/ci-build-systems/circle-ci.html)
- [See template](.circleci/config.yml)

## BuildKite [![Build status](https://badge.buildkite.com/cfc0283e07b5b5ca5aa08cc7539af3e95cabff1ed988c0cb8a.svg)](https://buildkite.com/debricked/debricked-maven-templates)
- Add Debricked token variable. [Read more](https://buildkite.com/docs/pipelines/environment-variables#defining-your-own)
- [See template](.buildkite/pipeline.yml)  

## GitLab CI/CD
- Add Debricked token variable. [Read more](https://debricked.com/docs/integrations/ci-build-systems/gitlab.html#integrating-using-an-access-token)
- [See template](.gitlab-ci.yml)

## Azure Pipelines
- Add Debricked token variable. [Read more](https://debricked.com/docs/integrations/ci-build-systems/azure-devops.html)
- [See template](azure-pipelines.yml)

## Argo Workflows
- Add Debricked token variable. [Read more](https://debricked.com/docs/integrations/ci-build-systems/argo-workflows.html)
- [See template](argo.yml)

## Travis CI
- Add Debricked token variable. [Read more](https://debricked.com/docs/integrations/ci-build-systems/travis.html)
- [See template](.travis.yml)
