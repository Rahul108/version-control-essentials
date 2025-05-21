# Version Control Essentials: Git and GitHub

This guide provides a concise overview of essential version control concepts using Git and GitHub, including committing, branching, merging, and pull requests.

## Installation

1.  **Install Git:**
    Visit the official Git website to download and install the appropriate version for your operating system: [https://git-scm.com/](https://git-scm.com/)

2.  **Initialize Your Project:**
    Open your terminal or command prompt and navigate to your project directory. Then, initialize a Git repository using the following command:
    ```bash
    mkdir <project-name>
    cd <project-name>
    git init
    ```
    * **Note:** If the `init.defaultBranch` configuration is not set globally, the default initial branch name will be `master`.

3.  **Add a README File:**
    Create a `README.md` file in your project directory. This file should contain a description of your project, its purpose, and any relevant information for users or collaborators.

4.  **Link to a Remote GitHub Repository:**
    * **Create a GitHub Repository:** Go to [https://github.com/new](https://github.com/new) and create a new repository for your project.
    * **Link Local Repository:** In your local project directory, run the following command, replacing `<git-remote-url>` with the URL of your newly created GitHub repository:
        ```bash
        git remote add origin <git-remote-url>
        ```
        This command establishes a connection between your local Git repository and the remote repository on GitHub, naming the remote as `origin`.

5.  **Commit the changes:**
    ```
    git add .
    git commit -m "<meaningful message which describes the changes in brief>"
    
    // e.g:
    git commit -m "docs: initalize project with README.md"       
    ```
    You can also follow [Conventional Commits specification](https://www.conventionalcommits.org/en/v1.0.0/#summary) as per project requirement.

6.  **Add new Branch:**
    ```
    git branch <new branch name>
    git checkout <new branch name>
    ```

    you can also create and checkout at the same time by
    ```
    git checkout -b <new branch name>
    ```

6.  **Add a Workflow:**
    GitHub Actions allows you to automate tasks such as running tests, building your project, or deploying code by defining workflows in your repository.

    * Create a workflow file in .github/workflows/ directory of your repository, e.g., .github/workflows/main.yml.

    * Define triggers (like push or pull_request) and specify jobs and steps inside the workflow YAML file.

    * use official actions (e.g., actions/checkout) or custom shell commands to perform tasks.

    For example, to create a workflow that runs on every push to the main branch, your workflow file might look like this:
    ```
        name: Example Workflow

        on:
        push:
            branches:
            - main

        jobs:
        example-job:
            runs-on: ubuntu-latest
            steps:
            - uses: actions/checkout@v4
            - run: echo "Hello, world!"

    ```

    Once committed and pushed, the workflow will run automatically based on the trigger.

    For more details and quickstart guides, see the official documentation: [GitHub Actions Quickstart](https://docs.github.com/en/actions/writing-workflows/quickstart)




