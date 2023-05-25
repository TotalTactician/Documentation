# Securing our codebase using Github
![image](https://github.com/TotalTactician/Documentation/assets/81526735/9a3519c7-ad15-4d04-bf6a-ddb14ede43be)
By [Sylvester Snijders](https://github.com/AsterosTheGreat) and [Joey Remmers](https://github.com/Joeyicetera)

## Contents
- [Introduction](#introduction)
- [How should we promote security in our Github repositories in order to protect our codebase?](#how-should-we-promote-security-in-our-github-repositories-in-order-to-protect-our-codebase)
- [How can we utilize github settings to reduce the amount human errors getting into the codebase?](#how-can-we-utilize-github-settings-to-reduce-the-amount-human-errors-getting-into-the-codebase)
- [How can we utilize testing tools to ensure the quality of our code?](#how-can-we-utilize-testing-tools-to-ensure-the-quality-of-our-code)
- [How can we utilize workflows to enforce the quality of code added to the codebase?](#how-can-we-utilize-workflows-to-enforce-the-quality-of-code-added-to-the-codebase)
- [Sources](#sources)

## Introduction
As software development thrives in an interconnected world, GitHub has emerged as a vital platform for hosting and collaborating on code repositories. However, the accessibility and collaborative nature of GitHub also bring security challenges. In this paper we will look into the tools that github provides.

## How should we promote security in our Github repositories in order to protect our codebase?

## How can we utilize github settings to reduce the amount human errors getting into the codebase?

## How can we utilize testing tools to ensure the quality of our code?

## How can we utilize actions to enforce the quality of code added to the codebase?
With github action you can automaticly run build, test and deploy jobs for easy CI/CD, with this automation you reduce the number of human errors and ensure that no broken code can be merged. You implement this using workflows. A workflow is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule. these triggers include but are not limited to: branch actions, actions regarding issues and on actions regarding members. 

Sometimes you might just want to update the version of one dependency in a manifest and generate a pull request. However, if the updated version of this direct dependency also has updated dependencies, your pull request may have more changes than you expected. The dependency review for each manifest and lock file provides an easy way to see what has changed, and whether any of the new dependency versions contain known vulnerabilities. By adding the dependency reviews action in your workflow, at a pull request, and changing any dependencies that are flagged as vulnerable, you can avoid vulnerabilities being added to your project. By default, the dependency review action check will fail if it discovers any vulnerable packages. A failed check blocks a pull request from being merged when the repository owner requires the dependency review check to pass. (About dependency review - GitHub Docs)

While working with external services you have to work with authentication. These sensitive values should never be stored as plaintext in workflow files, but rather as secrets. Secrets are encrypted variables that you create in an organization, repository, or repository environment. The secrets that you create are available to use in GitHub Actions workflows. GitHub uses a [libsodium sealed box](https://libsodium.gitbook.io/doc/public-key_cryptography/sealed_boxes) to help ensure that secrets are encrypted before they reach GitHub and remain encrypted until you use them in a workflow. (Encrypted secrets - Github Docs)


## Sources
- [About dependency review - GitHub Docs](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review)
- [About workflows - Github Docs](https://docs.github.com/en/actions/using-workflows/about-workflows)
- [Security hardening for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)
- [Encrypted secrets - Github Docs](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
