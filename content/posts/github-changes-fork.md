+++
title = 'Github Changes - Fork'
date = 2020-09-26
draft = false
tags = ['git', 'github']
description = 'Step-by-step guide on how to fork a repository, make changes, and submit a pull request using Git and GitHub'
+++


### Cloning a Repository:

1. **Fork the Repository:**

    - Go to the GitHub page of the repository you want to contribute to.
    
    - Click the "Fork" button in the top right corner. This creates a copy of the repository under your GitHub account.
    
2. **Clone Your Fork:**
    
    - On your forked repository, click the "Code" button.
        
    - Copy the URL provided (e.g., `https://github.com/your-username/repository.git`).
        
    - Open a terminal on your local machine.
        
    - Navigate to the directory where you want to store the project.
        
    - Run the following command:
        
        `git clone https://github.com/your-username/repository.git`
        

### Making Changes:

3. **Create a Branch:**
    
    - Change into the project's directory:
        
        `cd repository`
        
    - Create a new branch for your changes. It's a good practice to name your branch descriptively:
        
        `git checkout -b feature-branch`
        
4. **Make Changes:**
    
    - Make the necessary changes to the code using your preferred editor.
    
1. **Commit Changes:**
    
    - Add the changes to the staging area:
        
        `git add .`
        
    - Commit the changes:
        
        `git commit -m "Description of changes"`
        
6. **Push Changes to Your Fork:**
    
    - Push the changes to your fork on GitHub:
        
        `git push origin feature-branch`
        

### Submitting a Pull Request:

7. **Create a Pull Request:**
    
    - Go to your fork on GitHub.
    - You should see a banner with a button to "Compare & pull request." Click on it.
    - Add a title and description to your pull request, explaining what changes you made.
    - Click on "Create pull request."
8. **Review and Merge:**
    
    - The repository maintainers will review your changes. They may ask for modifications.
    - Once the changes are approved, they will merge your pull request.

Congratulations! You've successfully cloned a repository, made changes, and submitted a pull request.