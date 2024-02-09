+++
title = 'Github Changes - Clone'
date = 2022-09-26
draft = false
tags = ['git', 'github']
description = 'Step-by-step guide on how to clone a repository, make changes, and submit a pull request using Git and GitHub'
+++

If you don't want to fork the repository and prefer to clone and contribute directly to the original repository, you can follow these steps:

### Cloning and Contributing Without Forking:

1. **Clone the Repository:**
    
    - Open a terminal on your local machine.
        
    - Navigate to the directory where you want to store the project.
        
    - Run the following command:
        
        bashCopy code
        
        `git clone https://github.com/original-author/repository.git`
        
2. **Create a Branch:**
    
    - Change into the project's directory:
        
        bashCopy code
        
        `cd repository`
        
    - Create a new branch for your changes. It's a good practice to name your branch descriptively:
        
        bashCopy code
        
        `git checkout -b feature-branch`
        
3. **Make Changes:**
    
    - Make the necessary changes to the code using your preferred editor.
4. **Commit Changes:**
    
    - Add the changes to the staging area:
        
        bashCopy code
        
        `git add .`
        
    - Commit the changes:
        
        bashCopy code
        
        `git commit -m "Description of changes"`
        
5. **Push Changes to the Original Repository:**
    
    - Push the changes to the original repository:
        
        bashCopy code
        
        `git push origin feature-branch`
        

### Creating a Pull Request:

6. **Submit a Pull Request:**
    
    - Visit the original repository on GitHub.
    - You should see a banner indicating that you recently pushed a branch. Click on the "Compare & pull request" button.
    - Add a title and description to your pull request, explaining what changes you made.
    - Click on "Create pull request."
7. **Review and Merge:**
    
    - The repository maintainers will review your changes. They may ask for modifications.
    - Once the changes are approved, they will merge your pull request.

Keep in mind that this approach requires write access to the original repository. If you don't have write access, you may need to fork the repository or contact the repository owner to discuss your changes.


