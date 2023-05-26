# Securing our codebase using Github
![image](https://github.com/TotalTactician/Documentation/assets/81526735/9a3519c7-ad15-4d04-bf6a-ddb14ede43be)
By [Sylvester Snijders](https://github.com/AsterosTheGreat) and [Joey Remmers](https://github.com/Joeyicetera)

## Contents
- [Introduction](#introduction)
- [How should we promote security in our Github repositories in order to protect our codebase?](#how-should-we-promote-security-in-our-github-repositories-in-order-to-protect-our-codebase)
- [How can we utilize github settings to reduce the amount human errors getting into the codebase?](#how-can-we-utilize-github-settings-to-reduce-the-amount-human-errors-getting-into-the-codebase)
- [How can we utilize testing tools to ensure the quality of our code?](#how-can-we-utilize-testing-tools-to-ensure-the-quality-of-our-code)
- [How can we utilize actions to enforce the quality of code added to the codebase?](#how-can-we-utilize-actions-to-enforce-the-quality-of-code-added-to-the-codebase)
- [Sources](#sources)

## Introduction
As software development thrives in an interconnected world, GitHub has emerged as a vital platform for hosting and collaborating on code repositories. However, the accessibility and collaborative nature of GitHub also bring security challenges. Securing codebases is paramount to protect valuable intellectual property and sensitive data. GitHub, a widely adopted platform for collaborative coding, offers a comprehensive set of features and best practices to bolster codebase security. By combining these measures, developers can establish a robust security framework, ensuring the integrity and confidentiality of their code. In this paper we will look into the tools that github provides and answer the question: ***How should we promote security in our Github repositories in order to protect our codebase?***

## How can we utilize github settings to reduce the amount human errors getting into the codebase?

To fortify user authentication, developers should implement Two-Factor Authentication (2FA) and encourage the use of strong, unique passwords. 2FA adds an extra layer of security by requiring users to provide a unique code generated on their mobile devices. This mitigates the risk of unauthorized access and helps prevent breaches. Coupled with strong passwords, this authentication mechanism significantly enhances codebase security.

In addition to user authentication, safeguarding codebases also involves protecting branches and code history. By restricting branch deletion and force push operations, codebase administrators prevent accidental or malicious modifications to critical branches. This preservation of code history not only ensures data integrity but also provides a valuable audit trail for tracking changes and identifying potential security vulnerabilities.

Moreover, GitHub's collaborative features, such as code review and pull requests, play a pivotal role in maintaining code quality and security. Leveraging these features, developers can propose changes and subject them to rigorous code reviews by their peers. Through collaborative discussions and thorough evaluations, security vulnerabilities, code quality issues, and bugs can be identified and resolved before changes are merged into the codebase. This approach promotes a culture of accountability and enhances the overall security posture of the codebase.

By embracing GitHub's branch protection rules, developers can establish strict controls over the merging process. These rules enforce requirements such as mandatory reviews, approvals, and passing status checks before changes can be merged into critical branches, including the main branch. By adhering to these safeguards, developers can prevent unauthorized or hasty modifications, reducing the risk of introducing faulty or insecure code into the codebase.

Furthermore, GitHub offers built-in security features like Vulnerability Alerts and Code Scanning. These tools analyze the codebase for known security vulnerabilities and promptly notify repository administrators. By proactively addressing these vulnerabilities, developers can fortify their codebase against potential exploitation and enhance the overall security resilience of their software projects.

To maintain confidentiality and control access to codebases, administrators can fine-tune visibility settings. GitHub allows repositories to be configured as public, private, or restricted to specific collaborators or teams. Limiting visibility ensures that sensitive or proprietary code remains accessible only to authorized individuals, minimizing the risk of unauthorized access or unauthorized distribution of intellectual property. (Sources: ChatGPT and Official Github Documentation)

## How can we utilize testing tools to ensure the quality of our code?

## How can we utilize actions to enforce the quality of code added to the codebase?
Maintaining code quality and ensuring error-free deployments are crucial aspects of software development. With github action you can automaticly run build, test and deploy jobs for easy continuous integration and continuous delivery (CI/CD), with this automation you reduce the number of human errors and ensure that no broken code can be merged. You implement this using workflows. A workflow is a configurable automated process that will run one or more jobs. Workflows are defined by a YAML file checked in to your repository and will run when triggered by an event in your repository, or they can be triggered manually, or at a defined schedule. Workflows can be triggered by events such as branch creations, issue updates, or membership changes in your repository. (About workflows - Github Docs)

Sometimes you might just want to update the version of one dependency in a manifest and generate a pull request. However, if the updated version of this direct dependency also has updated dependencies, your pull request may have more changes than you expected. The dependency review for each manifest and lock file provides an easy way to see what has changed, and it scans for vulnerabilities in the project's dependencies and alerts developers. By adding the dependency review action in your workflow at a pull request and changing any dependencies that are flagged as vulnerable, you can avoid vulnerabilities being added to your project. By default, the dependency review action check will fail if it discovers any vulnerable packages. A failed check blocks a pull request from being merged when the repository owner requires the dependency review check to pass. (About dependency review - GitHub Docs)

While working with external services you have to work with sensitive values, such as API keys, database credentials, or access tokens. These should never be stored as plaintext in workflow files, but rather as secrets. Secrets are encrypted variables that you create in an organization, repository, or repository environment. The secrets that you create are available to use in GitHub Actions workflows. GitHub uses a [libsodium sealed box](https://libsodium.gitbook.io/doc/public-key_cryptography/sealed_boxes) to help ensure that secrets are encrypted before they reach GitHub and remain encrypted until you use them in a workflow. (Encrypted secrets - Github Docs)

## How should we promote security in our Github repositories in order to protect our codebase?

## Sources
- [About dependency review - GitHub Docs](https://docs.github.com/en/code-security/supply-chain-security/understanding-your-software-supply-chain/about-dependency-review)
- [About workflows - Github Docs](https://docs.github.com/en/actions/using-workflows/about-workflows)
- [Security hardening for GitHub Actions - GitHub Docs](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)
- [Encrypted secrets - Github Docs](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
- [ChatGPT](https://chat.openai.com/)
- [Official Github Documentation](https://docs.github.com)

