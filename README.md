# pay-code-analysis-config
Configuration files for code analysis tools used on GOV.UK Pay repositories

## What’s in this repository

This repository contains configuration files for a number of code analysis tools used to analyse GOV.UK Pay repositories. While individual repositories contain their own copies of these files, the ones here are the canonical ones. For the sake of consistency, changes should be made only to the files here and then copied to the other repositories.

## Configuration files

| Tool                                             | Description                  | File name                        | Applicable repositories                                    |
| ------------------------------------------------ | -----------------------------|----------------------------------|------------------------------------------------------------|
| [PMD](https://pmd.github.io/)                    | Cross-language code analyser | [ruleset.xml](ruleset.xml)       | Any containing Java source code or non-generated XML files |
| [Hadolint](https://github.com/hadolint/hadolint) | Linter for Dockerfiles       | [.hadolint.yaml](.hadolint.yaml) | Any containing Dockerfiles                                 |

## Codacy

[Codacy](https://www.codacy.com/) provides code analysis as a service. It runs code analysis tools like those listed above either on demand or as part of a build pipeline.

We have an organisation on Codacy called _govuk-pay_ with a number of projects added to it.

For each project, Codacy has a _Code patterns_ page, which allows us to choose which code analysis tools to run and how each tool is configured. By default, each tool is set to use the _Tool pattern list_ option, which presents a list of patterns with checkboxes to enable or disable each one.

However, we prefer to use the _Configuration file_ option, which makes Codacy look for an appropriate configuration file for the tool in the project root. This approach is more flexible because it allows us to easily use the same configuration for a tool whether it is run by Codacy or another method (such as on a developer’s own computer).

Codacy will only look for configuration files in the root of the project being analysed. Therefore, to use a configuration file, it has to be copied to the root of the target project. The files in this repository are named such that they will be picked up by Codacy if placed in the project root.

Note that Codacy does not appear to support the _Configuration file_ option for all code analysis tools. See the _I have my own tool configuration file_ section of Codacy’s [Code Patterns](https://support.codacy.com/hc/en-us/articles/207994335-Code-Patterns) help document for details of which tools can be used with the _Configuration file_ option and what the configuration files need to be named.

## Licence

[MIT License](LICENSE)

## Responsible disclosure

GOV.UK Pay aims to stay secure for everyone. If you are a security researcher and have discovered a security vulnerability in this code, we appreciate your help in disclosing it to us in a responsible manner. We will give appropriate credit to those reporting confirmed issues. Please e-mail gds-team-pay-security@digital.cabinet-office.gov.uk with details of any issue you find, we aim to reply quickly.
