+++
title = 'Naming Conventions Git Branches'
date = 2020-10-01T18:16:16-05:00
draft = false
tags = ['git']
Description = 'CheatSheet'
ShowToc = true
+++

## Basic Rules
- **Lowercase and Hyphen-separated**: Stick to lowercase for branch names and use hyphens to separate words. For example, feature/new-login or bugfix/header-styling.
- **Alphanumeric Characters**: Use only alphanumeric characters (a-z, 0–9) and hyphens. Avoid punctuation, spaces, underscores, or any non-alphanumeric character.
- **No Continuous Hyphens**: Do not use continuous hyphens. feature--new-login can be confusing and hard to read.
- **No Trailing Hyphens**: Do not end your branch name with a hyphen. For example, feature-new-login- is not a good practice.
- **Descriptive**: The name should be descriptive and concise, ideally reflecting the work done on the branch.

## Branch Prefixes
Helps identify the purpose of the branches.  
- **Feature Branches**: These branches are used for developing new features. Use the prefix feature/. For example, feature/login-system.
- **Bugfix Branches**: These branches are used to fix bugs in the code. Use the prefix bugfix/. For example, bugfix/header-styling.
- **Hotfix Branches**: These branches are made directly from the production branch to fix critical bugs in the production environment. Use the prefix hotfix/. For example, hotfix/critical-security-issue.
- **Release Branches**: These branches are used to prepare for a new production release. They allow for last-minute dotting of i’s and crossing t’s. Use the prefix release/. For example, release/v1.0.1.
- **Documentation Branches**: These branches are used to write, update, or fix documentation. Use the prefix docs/. For example, docs/api-endpoints.

## Including Jira Ticket Numbers
This makes it easy to track the work done on a specific ticket. For example, if working on a ticket numbered “T-999 for adding a new email system, the branch name could be feature/T-999-new-email-system.




