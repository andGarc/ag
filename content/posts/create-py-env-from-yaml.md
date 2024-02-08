+++
title = 'Python Environment form a YAML file'
date = 2023-12-07
draft = false
tags = ['python']
Description = 'Create an environment form a YAML file'
+++

## Why use a yaml file
When working with Conda a YAML file can be used to list all the necessary packages of your project. 

## Steps
1. Make sure Conda is installed
	1. To check run `conda info`
2. Create a YAML file that includes all the packages and versions. You can either create a new one or export one from an existing Conda environment. 
	1. To export a YAML from an existing environment: `conda env_name export > environment.yml`

```yaml
name: my_env
channels:
  - defaults
dependencies:
  - numpy=1.18.1
  - pandas=1.0.1
  - scikit-learn=0.22.1
```

3. Create the Conda environment using the YAML file: `conda env create -f environment.yml`
4. To verify that the environment was created correctly: `conda env list`
5. Activate your environment! 
 