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

In the rapidly evolving landscape of software development, securing codebases is paramount to protect valuable intellectual property and sensitive data. GitHub, a widely adopted platform for collaborative coding, offers a comprehensive set of features and best practices to bolster codebase security. By combining these measures, developers can establish a robust security framework, ensuring the integrity and confidentiality of their code.

## How should we promote security in our Github repositories in order to protect our codebase?

## How can we utilize github settings to reduce the amount human errors getting into the codebase?

To fortify user authentication, developers should implement Two-Factor Authentication (2FA) and encourage the use of strong, unique passwords. 2FA adds an extra layer of security by requiring users to provide a unique code generated on their mobile devices. This mitigates the risk of unauthorized access and helps prevent breaches. Coupled with strong passwords, this authentication mechanism significantly enhances codebase security.

In addition to user authentication, safeguarding codebases also involves protecting branches and code history. By restricting branch deletion and force push operations, codebase administrators prevent accidental or malicious modifications to critical branches. This preservation of code history not only ensures data integrity but also provides a valuable audit trail for tracking changes and identifying potential security vulnerabilities.

Moreover, GitHub's collaborative features, such as code review and pull requests, play a pivotal role in maintaining code quality and security. Leveraging these features, developers can propose changes and subject them to rigorous code reviews by their peers. Through collaborative discussions and thorough evaluations, security vulnerabilities, code quality issues, and bugs can be identified and resolved before changes are merged into the codebase. This approach promotes a culture of accountability and enhances the overall security posture of the codebase.

By embracing GitHub's branch protection rules, developers can establish strict controls over the merging process. These rules enforce requirements such as mandatory reviews, approvals, and passing status checks before changes can be merged into critical branches, including the main branch. By adhering to these safeguards, developers can prevent unauthorized or hasty modifications, reducing the risk of introducing faulty or insecure code into the codebase.

Furthermore, GitHub offers built-in security features like Vulnerability Alerts and Code Scanning. These tools analyze the codebase for known security vulnerabilities and promptly notify repository administrators. By proactively addressing these vulnerabilities, developers can fortify their codebase against potential exploitation and enhance the overall security resilience of their software projects.

To maintain confidentiality and control access to codebases, administrators can fine-tune visibility settings. GitHub allows repositories to be configured as public, private, or restricted to specific collaborators or teams. Limiting visibility ensures that sensitive or proprietary code remains accessible only to authorized individuals, minimizing the risk of unauthorized access or unauthorized distribution of intellectual property. (Sources: ChatGPT and Official Github Documentation)

## How can we utilize testing tools to ensure the quality of our code?

## How can we utilize workflows to enforce the quality of code added to the codebase?

## Sources
- [ChatGPT](https://chat.openai.com/)
- [Official Github Documentation](https://docs.github.com)
