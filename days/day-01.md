# Create a GitHub Repo and Commit

- **Step 1:** Initialize Git in your project folder
- **Step 2:** Add files and make your first commit
- **Step 3:** Create a new repository on GitHub (via CLI)

## Initialize Git in your Project Folder

```sh
cd path/to/your/project-folder
```
Navigate to your project directory 
```sh
git init
```
It transforms the Directory into Git Repository, allowing Git to track changes within it.

## Add files and make your first commit

```sh
git add .
```
It adds all new, modified, and deleted files in the current directory and its subdirectories to the staging area (also known as the index).
```sh
git commit -m "Initial Commit"
```
It captures a snapshot of the currently staged changes, creating a new point in the project's history.

## Create a new repository

```sh
gh repo create project-folder --public --source=. --remote=origin --push
```
`gh repo create`

- Tells GitHub CLI to create a new repository.

`project-folder`

- The name of the repository you want to create on GitHub.

`--public`

- Makes the repo public (visible to everyone).

- Alternatives:

    - `--private` → repo visible only to you (and collaborators).

    - `--internal` → (for GitHub Enterprise).

`--source=.`

- Tells GitHub CLI to use the current directory (.) as the source for the repo.

`--remote=origin`

- After creating the repo, it automatically sets the remote name to origin.

- `origin` is the conventional name for the remote pointing to GitHub.

- Equivalent to running:

    ```sh
    git remote add origin https://github.com/<your-username>/my-repo-name.git
    ```


`--push`

- Pushes your local commits to the GitHub repo immediately.

- Equivalent to:

    ```sh
    git push -u origin main
    ```
==Note==: Instead of manually creating a repo in GitHub + copying the URL + adding remote + pushing, this one command automates it.

**`Difficulty: ⭐ Beginner`**