# How to Fork a Repo and Create a Branch

**Usecase:** When you want to contribute to an open-source project (or any repo you don't have write access to). You cannot push changes directly to that project.

**The Workflow:**

1.  **Fork** the repository (create a copy under your own account).
2.  **Clone** your fork to your local machine.
3.  **Create a new branch** to make your changes safely.
4.  (Later) Push your branch to your fork and open a Pull Request.

Today, we'll cover the first three steps using GitHub CLI.

## Step 1: Fork and Clone the Repository

```sh
gh repo fork https://github.com/upstream-owner/project-name --clone=true
```

This single `gh` command automates the entire "Fork and Clone" process.

`gh repo fork`

  * Tells GitHub CLI to create a copy (a "fork") of a repository under your GitHub account.

`https://github.com/upstream-owner/project-name`

  * The URL of the "upstream" repository you want to contribute to.
  * **Example:** `https://github.com/activepieces/activepieces`

`--clone=true`

  * This is the helper flag. After successfully forking the repo on GitHub, `gh` will *automatically* clone your new fork (e.g., `https://github.com/<your-username>/project-name`) to your local machine.

**Note:** This one command replaces manually:

1.  Clicking the "Fork" button on the GitHub website.
2.  Going to your profile to find the forked repo.
3.  Copying your fork's URL.
4.  Running `git clone <your-fork-url>`.

-----

## Step 2: Create a New Branch for Your Changes

Now that you have the code locally, you must create a new branch *before* you start making changes. This isolates your work from the `main` branch.

```sh
cd project-name
```

Navigate into the newly cloned project directory.

```sh
git switch -c feat/my-new-feature
```

This `git` command creates a new branch and switches to it in one step.

  * `git switch`: The modern Git command for changing branches.
  * `-c`: The "create" flag. It tells `git switch` to create a new branch before switching.
  * `feat/my-new-feature`: The name of your new branch. Using prefixes like `feat/` (feature) or `fix/` is a common convention.

**Note:**
You will very often see the older command `git checkout -b <branch-name>` used. It does the exact same thing.

```sh
git checkout -b feat/my-new-feature
```

You are now on a new, safe branch and ready to make your changes.

**`Difficulty: ⭐ Beginner`**