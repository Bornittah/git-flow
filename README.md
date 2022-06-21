# Try Gitflow

## Learning objectives
- Follow Gitflow.

### Instructions

- Create a new repo. Initialize it with an empty README file.
    <p>
     <img src="../images/initialize-with-readme.png" alt="Initialize repo with readme" width="400px" />
    </p>
- Clone the newly created repository to your local machine.
- Add a new branch named `dev`(alternative names: `development`, `develop`).
- Make sure that the `dev` branch is pushed to GitHub.
    - `git push --set-upstream origin dev`
- Make the `dev` branch [the default branch](https://docs.github.com/en/github/administering-a-repository/managing-branches-in-your-repository/changing-the-default-branch#changing-the-default-branch).
- Create a feature branch called add-quotes
- Add a programmer.txt file with the following sentence (typo is needed there):
     - "A good programmer is someone who always looks both ways before crosing a one-way street."
- Add a solve.txt file with the following sentence:
     - "First, solve the problem. Then, write the code." – John Johnson
- Add another test.txt file. It should be empty.
- Commit all files to your feature branch.
- Push your changes to GitHub.
- Open a new pull request from `add-quotes` into `dev`.
- Make sure that you want to merge your commits into **dev** branch. You should add a comment in your opened pull request that is similar to this one:
     <p>
     <img src="../images/feature-branch-to-dev.png" alt="Initialize repo with readme" width="400px" />
    </p>
- _Keep your pull request open. you will need it in the upcoming exercises._
 - Congratulations! You have used Gitflow for the first time. **Remember to use it in all upcoming Microverse projects.**


# Resolve git conflict

## Learning objectives
- Solve simple git conflicts.

### Preparation - creating a merge confict

#### Making fixes in a new branch
- Make sure that you start from the `add-quotes` branch:
    - `git checkout add-quotes`
- Create a new branch `fix-quotes` and switch to it:
    - `git checkout -b fix-quotes`
- Make changes in your files:
     - Fix the typo in the quote about a good programmer (`crosing` should be `crossing`).
     - Remove the empty test.txt file.
     - Add a new simplicity.txt file with the following sentence:
         - "Simplicity is the soul of efficiency." - Austin Freeman
- Commit your changes.
- Push `fix-quotes` to GitHub:
    - `git push --set-upstream origin fix-quotes`.
- Open a new pull request (from `fix-quotes` to `dev` branch):
    <p>
     <img src="../images/fix-quotes-to-dev.png" alt="Pull request from fix-quites to dev branch" width="400px" />
    </p>
- Keep this pull request open.

#### Introducing changes in the first branch
- Make sure that you are in the `add-quotes` branch:
    - `git checkout add-quotes`
- Make a change in the quote about a good programmer:
    - add its author: `Doug Linder`
- Add a simplicity.txt file with the following sentence:
     - "Nature is pleased with simplicity. And nature is no dummy." - Isaac Newton
- Commit your changes.
- Push `add-quotes` to GitHub:
    - `git push --set-upstream origin add-quotes`.

#### Merging pull requests
- First, merge your pull request from the `fix-quotes` branch (it should be the pull request #2).
- Then, go to your pull request from the `add-quotes branch` (it should be the pull request #1).
- Merge option should be disabled, and you should see the list of conflicts.
  <p>
     <img src="../images/disabled-merge-conflict.png" alt="Merge button disabled due to conflicts" width="600px" />
  </p>

### Instructions

Now it is time to solve the conflict. Do it by using the command line.

- Make sure that your `dev` branch is up-to-date:
    - `git checkout dev`
    - `git pull`
- Switch to the `add-quotes` branch (if it is confusing to you, check [this issue](https://github.com/microverseinc/curriculum-transversal-skills/issues/83)):
    - `git checkout add-quotes`
- Try to merge the `dev` branch:
    - `git merge dev`
- You should see this message about a merge conflict:
    - "Automatic merge failed; fix conflicts and then commit the result."
- Check the status of your files to have clear information:
    - `git status`
- You should see the following message:
    <p>
     <img src="../images/conflict-command-line.png" alt="Conflict displayed in command line" width="400px" />
    </p>
- Open the conflicting files and decide which changes should stay.
- Commit your changes:
    - `git add <FILE NAMES>`
    - `git commit` (git is smart enough to create a merge commit message for you in this case)
- Push your changes to GitHub.
- Check your pull request. Now you should be able to merge your pull request from the `add-quotes` branch.

