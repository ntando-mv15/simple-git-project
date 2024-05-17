# Git and GitHub Project

## Introduction

This project demonstrates a basic Git and GitHub workflow, including common Git commands and a simple branching strategy. 

## Git Commands

Here are some basic Git commands used in this project:

### Initializing a Git Repository

**Command:**
```sh
git init
```
**Explanation:**
Initializes a new Git repository in the current directory `simple-git-project`.

Created a README.md file to add details of this project to. 

### Checking the Status

**Command:**
```sh
git status
```
**Explanation:**
Shows the status of changes as untracked, modified, or staged. The output detailed that my READMe.md file was untracked.


### Adding Files to the Staging Area

To allow git to track my file and all the changes made to it, I used the `git add` command.

**Command:**

```sh
git add READMe.md
```
**Explanation:**
This step also adds the specified file to the staging area, preparing them to be committed.

### Committing Changes

**Command:**

```sh
git commit -m "Add READMe.md"
```
**Explanation:**
Makes a record of the changes in the staging area to the repository with a descriptive message that lets collaborators (if any) know why changes were made.


### Viewing Differences

**Command:**
```sh
git diff
```
**Explanation:**
Shows the changes between the working directory and the staging area.

### Pushing Changes to GitHub

Created a repository `simple-git-project` on Github where all my code will be stored remotely. 

I proceed to push my code directly to the master branch of my repository:

**Example:**
```sh
git push -u origin master
```
**Explanation:**
Uploads local commits to the remote repository.

## Git Branching Strategy

This project follows a simple branching strategy to manage new features and prepare a release. The new features include scripts to greet user and bid farewell to user and a script combining both.

Branches in Git are independent lines of development that allow you to work on different features or versions of a project simultaneously. They enable you to isolate changes, experiment with new features, and collaborate with others without affecting the main codebase.

### Step-by-Step Workflow

#### Step 1: Create and Work on Feature Branches

Feature branches are branches created to work on a specific feature or functionality. They help in keeping the main development branch (e.g., master) stable while new features are being developed.

1. **Created a New Branch**:
   ```sh
   git checkout -b feature-greeting
   ```

   **Explanation:**
   Creates and switches to a new branch named `feature-greeting`.

2. **Added Feature**:
   Created a new file `greet.py` with code for the greeting feature.

3. **Added and Commit Changes**:
   ```sh
   git add greet.py
   git commit -m "Add greeting feature"
   ```

4. **Pushed the Feature Branch to GitHub**:
   ```sh
   git push -u origin feature-greeting
   ```

Repeated the above steps for other features (e.g., `feature-farewell` and `feature-combined-greeting-farewell`).

#### Step 2: Create a Release Branch

Once all feature branches are completed and tested, they are merged into a release branch (e.g., release-1.0).
The release branch serves as a staging area for final testing before merging into the main branch (master).

1. **Created a Release Branch**:
   ```sh
   git checkout master
   git pull origin master
   git checkout -b release-1.0
   ```
   **Explanation:**
   Moved me back into the `master` branch, and updated this branch locally with the changes made to our remote branches. Creates a release branch `release-1.0` from the `master` branch.



2. **Merge Feature Branches into Release Branch**:
   ```sh
   git merge feature-add-greeting
   git merge feature-add-farewell
   git merge feature-combined-greeting-farewell
   ```
    This approach of merging feature branches into a release branch first and then merging the release branch into master ensures a cleaner and more manageable workflow, especially when working on multiple features simultaneously.


3. **Push the Release Branch to GitHub**:
   ```sh
   git push -u origin release-1.0
   ```

#### Step 3: Create a Pull Request and Merge

Creating a pull request (PR) from the release branch to the master branch is an important step to ensure a smooth transition of new features into the main codebase. By focusing on a single pull request from the release branch to the master branch, you streamline the process and avoid redundancy, especially since the feature branches have already been merged into the release branch locally.

1. **Create a Pull Request on GitHub**:
   - Went to my repository on GitHub.
   - Clicked on the "Pull Requests" tab.
   - Clicked the "New Pull Request" button.
   - Set the base branch to `master` and the compare branch to `release-1.0`.
   - Filled in the title and description.

2. **Suggested Pull Request Title and Description**:

    **Title:**
    ```
    Release 1.0 - Merge Release Branch to Master
    ```

    **Description:**
    ```markdown
    ## Overview
    This pull request merges the `release-1.0` branch into the `master` branch. This release includes several new features and improvements. 

    ## Features
    - **Greeting Feature**: Added a new script `greet.py` to print a greeting message.
    - **Farewell Feature**: Added a new script `farewell.py` to print a farewell message.
    - **Combined Greeting and Farewell**: Added a new script `combined.py` to print both greeting and farewell messages.

    ## Changes
    - `greet.py`: A new script to greet the user.
    - `farewell.py`: A new script to bid farewell to the user.
    - `combined.py`: A new script that combines both greeting and farewell messages.

    ## Testing
    All new features have been tested locally and are functioning as expected. Please review the changes and ensure all new scripts are working correctly.

    ## Additional Notes
    Please ensure that any feedback or requested changes are addressed before merging this PR into the `master` branch. Once merged, this release will be ready for production deployment.

    ```
By following these steps, you ensure that all individual feature changes are properly reviewed and tested before being integrated into the main codebase. This helps maintain the quality and stability of the master branch.

3. **Squash and Merge the Pull Request**:
   - Once the pull request is approved, use the "Squash and merge" option to merge the changes.
   - This combines all the commits from the `release-1.0` branch into a single commit on the `master` branch.

**Why Squash and Merge?**
- **Cleaner History**: It creates a single commit, making the history of the master branch clean and easier to understand.
- **Simplified Review**: Reviewers can see all changes in a single commit, which simplifies the review process.

By following this workflow, I ensured that my project remains organized and my commit history stays clean, making it easier for others to follow and contribute to your project.

---

