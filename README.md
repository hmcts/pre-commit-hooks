# pre-commit-hooks
Repository to store pre-commit-hooks that can be used throughout any HMCTS repository.

# Pre-commit-hooks Introduction
Git hook scripts are useful for identifying simple issues before submission to code review. Hooks can be created/used to notify the commiter of issues in code such as formatting or incorrect syntax etc. 

# Pre-commit Installation
Before you can run hooks, you need to have pre-commit installed via this URL: https://pre-commit.com/#installation 

# Creating a pre-commit hook
Firstly check on [pre-commit.com](https://pre-commit.com/hooks.html) to see if a hook is already available. If not, you can create your own and add to this repository.

## Setup of new pre-commit hook
1. Apply the script that you want to run as part of your hook in the [pre-commit-hooks](https://github.com/hmcts/pre-commit-hooks/tree/master/pre-commit-hooks) folder. Ensure it is set to executable (`chmod +x file_name`) .
2. Update [.pre-commit-hooks](https://github.com/hmcts/pre-commit-hooks/blob/master/.pre-commit-hooks.yaml) with an ID for the newly created hook. See also further syntax on [new-hooks](https://pre-commit.com/#new-hooks).
3. Tag the change and create a new [release](https://github.com/hmcts/pre-commit-hooks/releases)
4. Apply your new webhook to the repository .pre-config-config.yaml [example](https://github.com/hmcts/azure-platform-terraform/blob/master/.pre-commit-config.yaml)

## Setup a repository for pre-commit hooks
1. In a repository that has not got pre-commit hooks setup, run `pre-commit install` to setup the git hook scripts
```
pre-commit install
pre-commit installed at .git/hooks/pre-commit
```
2. Creat file .pre-commit-config.yaml at root of directory and apply new webhook(s) as above.


## Sample output of pre-commit hooks
When  applying `git commit` it will run the required hooks. As per example below
```
tamops@49SVK63:/mnt/c/Users/thomast/Documents/GitHub/thomasthorntoncloud/playground/test-flag$ git commit -m "test"
app_gateway_backend_check................................................Failed
- hook id: app_gateway_backend_check
- exit code: 1

change your application to use the next gateway that is not full
```