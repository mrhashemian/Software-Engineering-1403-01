# Git: A Brief Overview and More

**Git** is a distributed version control system that helps developers track and manage changes in their code.
Created by **Linus Torvalds** in 2005, Git allows multiple people to work on a project simultaneously without stepping
on each other’s toes.
It keeps a complete history of all changes, making it easy to revert to earlier versions if needed.
Git is especially useful for collaborating on software development, allowing teams to create, test, and merge new
features easily.

## Best Practices in Git: Branching, Commit Messages, and More

### 1. **Importance of Creating Branches**

Working directly on the `main` (or `master`) branch can be risky. The `main` branch is typically used for stable
releases or production-ready code. Making experimental changes or developing new features directly on it can lead to
errors or unstable versions of the project. Instead, create a new **branch** for each feature or bug fix. This keeps
your work isolated, so the `main` branch remains clean.

- **Why it matters**: Branching allows parallel development. Each branch can be developed independently and only merged
  into `main` once it’s fully tested and ready.

### 2. **Naming Branches Properly**

Clear and consistent branch names help your team quickly understand the purpose of a branch. A good naming convention
might include the type of work and a brief description, like:

- `feature/user-authentication`
- `bugfix/fix-login-issue`

- **Why it matters**: Well-named branches improve collaboration and make it easier to manage a project, especially in
  large teams.

### 3. **Committing Regularly**

Frequent commits allow you to track your progress and make it easier to identify where things went wrong if a bug
arises. Commit **small, logical changes** regularly, rather than saving everything for one large commit at the end.

- **Why it matters**: Regular commits create a more detailed project history and provide checkpoints you can return to
  if necessary.

### 4. **Writing Clear Commit Messages**

A good commit message should describe **what** the change does and **why** it was necessary. Avoid vague messages like "
fix bug" or "update." Instead, use descriptive messages like:

- `Fix login error caused by incorrect token validation`
- `Add new user authentication flow`

- **Why it matters**: Clear commit messages make the project’s history easier to understand for both you and your
  teammates, making it easier to trace specific changes.

## Essential Git Commands

[Here](commands.md), we've provided a list of basic Git commands for you. Git is a vast tool with many commands, and
this is just a small portion of what it can do.

1. [Init](commands.md#1-init): Initialize a new Git repository in the current directory.
2. [Clone](commands.md#2-clone): Create a copy of a remote repository on your local machine.
3. [Add](commands.md#3-add): Stage changes in specified file(s) for the next commit.
4. [Commit](commands.md#4-commit): Record changes to the repository with a descriptive message.
5. [Status](commands.md#5-status): Display the state of the working directory and staging area.
6. [Push](commands.md#6-push): Upload your local changes to the remote repository.
7. [Pull](commands.md#7-pull): Fetch and merge changes from the remote repository to your current branch.
8. [Branch](commands.md#8-branch): List all branches in the repository or create a new branch.
9. [Checkout](commands.md#9-checkout): Switch to a specified branch or restore files.
10. [Merge](commands.md#10-merge): Combines changes from the specified branch into your current branch.
11. [Stash](commands.md#11-stash): Temporarily saves changes in the working directory that are not ready to be
    committed.
12. [Log](commands.md#12-log): Displays a chronological list of commits in the repository.
13. [Diff](commands.md#13-diff): Show differences between the working directory and the index or between commits.
14. [Restore](commands.md#14-restore): Discard changes in the working directory and restore files to the last committed
    state.

### Useful Git Documentation

- **Official Git Documentation**: [Git Documentation](https://git-scm.com/doc)
- **GitHub Cheat Sheet**: [GitHub Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- **Git Basics (Atlassian)**: [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)

## Merge Requests, Code Review, and Squash Commits

### 1. Merge Requests (Pull Requests)

A **merge request** (called a **pull request** on platforms like GitHub) is a process where a developer proposes to
merge changes from one branch into another, typically from a feature or bug fix branch into the `main` branch. It serves
as a formal request for review before the actual merging takes place.

**Key Points**:

- **Collaboration**: Merge requests allow team members to see the changes being proposed, leave comments, suggest
  improvements, and discuss code before it’s merged.
- **Version Control**: They ensure that new features or bug fixes don’t go directly into the main branch without proper
  review, reducing the risk of introducing bugs or unstable code into the project.

### 2. Code Review

**Code review** is the process of evaluating the changes proposed in a merge request. It is one of the most important
practices in collaborative software development because it improves code quality and fosters knowledge sharing among
team members.

**Benefits of Code Review**:

- **Improved Code Quality**: By having peers review the code, you can catch mistakes or bugs that may not have been
  obvious to the original developer.
- **Knowledge Sharing**: Team members become more familiar with different parts of the codebase.
- **Consistency**: Code reviews help maintain consistent coding standards and best practices across the team.

During the review process, reviewers can:

- Leave comments on specific lines of code.
- Ask for clarifications or suggest changes.
- Approve the merge request once everything is in order.

### 3. Squash Commits

When working on a feature or bug fix, developers often create multiple commits to track their progress. While this is
useful during development, a large number of small commits can clutter the project’s history. **Squashing commits**
means combining multiple smaller commits into a single, more meaningful commit before merging the branch into `main`.

**How to Squash Commits:**
Most platforms (e.g., GitHub, GitLab) allow you to **squash commits** as part of the merge request process.
Alternatively, you can squash commits manually using Git.

## Tags and Semantic Versioning (SemVer) in Git

In Git, **tags** are used to mark specific points in your project’s history, often to signify important milestones such
as **releases**. Tags are typically used in combination with **Semantic Versioning (SemVer)** to create meaningful
version numbers that convey the scope of changes in each release.

### What is Semantic Versioning (SemVer)?

**Semantic Versioning (SemVer)** is a versioning scheme that uses a three-part number format: `MAJOR.MINOR.PATCH`. This
format clearly communicates the significance of the changes in each new release.

1. **MAJOR**: Increased when you make incompatible API changes.
    - Example: Moving from version `1.0.0` to `2.0.0` indicates breaking changes that may require users to adjust their
      code.

2. **MINOR**: Increased when you add functionality in a backward-compatible manner.
    - Example: Going from `1.1.0` to `1.2.0` means new features were added without breaking existing functionality.

3. **PATCH**: Increased when you make backward-compatible bug fixes.
    - Example: A version update from `1.0.1` to `1.0.2` indicates a bug fix with no functional changes.

### Tagging in Git

To create a tag, you can use:

```bash
git tag v1.0.0
```

This tag can then be pushed to the remote repository using:

```bash
git push origin v1.0.0
```

### Example of Semantic Versioning in Practice:

- **v1.0.0**: The first stable release.
- **v1.1.0**: A new feature was added (e.g., support for a new API endpoint).
- **v1.1.1**: A minor bug was fixed in the existing feature.
- **v2.0.0**: A major update that introduces breaking changes (e.g., refactored core logic).

**Semantic Versioning Documentation**: [https://semver.org/](https://semver.org/)

## GitLab CI and GitHub Actions: Automating Workflows with CI/CD

**Continuous Integration (CI)** and **Continuous Deployment (CD)** are essential practices in modern software
development. They ensure that code changes are automatically tested and deployed, leading to faster development cycles
and fewer errors in production. Both **GitLab CI** and **GitHub Actions** provide powerful tools for automating these
workflows.

### 1. GitLab CI/CD

**GitLab CI/CD** is GitLab’s built-in tool for automating the process of building, testing, and deploying your code. By
defining a **`.gitlab-ci.yml`** file in the root of your repository, you can create pipelines that automatically run
whenever code is pushed or a merge request is created.

**Key Features**:

- **Pipeline Automation**: GitLab pipelines allow you to automate testing, building, and deployment steps. For example,
  you can automatically run unit tests every time a new feature is pushed.
- **Jobs and Stages**: In a GitLab pipeline, jobs are tasks that need to be executed, like running tests or deploying to
  a server. Jobs are grouped into stages, and stages are executed sequentially.
- **Runners**: GitLab uses **runners** to execute jobs. These can be hosted by GitLab or self-hosted on your own
  servers.

**Example of a Simple `.gitlab-ci.yml` file**:

```yaml
stages:
  - build
  - test
  - deploy

build_job:
  stage: build
  script:
    - echo "Building the project"

test_job:
  stage: test
  script:
    - echo "Running tests"

deploy_job:
  stage: deploy
  script:
    - echo "Deploying the project"
```

### 2. GitHub Actions

**GitHub Actions** is GitHub’s workflow automation tool that allows you to create custom CI/CD pipelines. It uses **YAML
files** stored in the `.github/workflows/` directory of your repository to define actions and workflows.

**Key Features**:

- **Event-Driven Workflows**: GitHub Actions can be triggered by various GitHub events, such as `push`, `pull_request`,
  or even scheduled events (cron jobs).
- **Reusable Actions**: Actions are individual tasks that can be combined to create a complete workflow. GitHub provides
  a large marketplace of pre-built actions, and you can create your own.
- **Matrix Builds**: GitHub Actions supports matrix builds, allowing you to run tests across multiple environments (
  e.g., different versions of Node.js or Python).

**Example of a Simple Workflow File for GitHub Actions**:

```yaml
name: CI Pipeline

on: [ push, pull_request ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14'
      - run: npm install
      - run: npm test
```

## Importance of Team Conventions

Having **team conventions**—a set of agreed-upon rules and practices for coding, commit messages, branching, and other
aspects of software development—is crucial for maintaining consistency and efficiency within a development team.

### Why Team Conventions Matter

1. **Consistency**: Uniform code styles and practices make the codebase easier to read and understand, regardless of who
   wrote the code. This consistency helps in code reviews, debugging, and maintenance.

2. **Efficiency**: Established conventions streamline the development process, reducing confusion and miscommunication.
   They also make onboarding new team members faster and more effective.

3. **Quality**: Clear guidelines on code quality, testing, and commit practices help maintain high standards and reduce
   the likelihood of bugs or technical debt.

4. **Collaboration**: Team conventions facilitate better collaboration by providing a common framework that all team
   members adhere to. This helps in integrating different parts of the project and ensures that everyone is on the same
   page.

### Examples of Team Conventions

1. **Code Style Guidelines**:
    - **Indentation**: Use 4 spaces for indentation.
    - **Brackets**: Place opening brackets on the same line as the statement.
    - **Naming Conventions**: Use camelCase for variable names and PascalCase for class names.

2. **Commit Message Format**:
    - **Structure**: Use a consistent format for commit messages, such as `[TYPE] Brief description` (
      e.g., `[FIX] Corrected typo in README`).
    - **Description**: Provide a concise summary of the changes and why they were made. Include references to related
      issues or tickets if applicable.

   *Example*:
   ```
   [FEATURE] Add user authentication
   - Implement login and registration functionality
   - Update user model to include authentication fields
   ```

3. **Branch Naming Conventions**:
    - **Feature Branches**: Use `feature/description` (e.g., `feature/user-login`).
    - **Bug Fixes**: Use `bugfix/description` (e.g., `bugfix/fix-login-error`).
    - **Hotfixes**: Use `hotfix/description` (e.g., `hotfix/critical-security-patch`).

4. **Code Review Process**:
    - **Reviewers**: Each merge request should be reviewed by at least one other team member.
    - **Approval**: Ensure that all code reviews are completed and approved before merging into the main branch.

5. **Testing**:
    - **Unit Tests**: Write unit tests for new features and bug fixes.
    - **Test Coverage**: Aim for a minimum test coverage percentage, such as 80%.
    - **Automated Testing**: Use CI/CD pipelines to run tests automatically on each commit or pull request.

## Important Tips:

We highly recommend reviewing the **Best Practices** section. Following these practices can
significantly improve your Git workflow and collaboration:

1. **Read the Best Practices**: Ensure you're familiar with best practices for efficient Git usage, as these will help
   avoid common issues.
2. **Commit Regularly**: Make sure to commit changes frequently. This keeps your work backed up and helps track
   progress.
3. **Work on Separate Branches**: Always develop new features or fix bugs on their own branches. Avoid committing
   directly to the `main` branch.
4. **Use Meaningful Names**: Whether it’s branch names or commit messages, always ensure they are clear and meaningful.
   This makes tracking changes and collaboration easier for the whole team.

## Contact Us

If you have any questions, need assistance, or encounter any challenges while using Git or implementing the workflows
and practices covered in this document, we’re here to help! 

- **Telegram**: [@mrzhashemian](https://t.me/mrzhashemian)
