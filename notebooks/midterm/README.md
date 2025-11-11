# Module 3 - Testing Models - Titanic Dataset
## by Jarred Gastreich

# ml-modules is a collection Machine Learning projects by Jarred Gastreich

## Titanic Dataset Description
Ability to explore characteristics that contributed to the 891 surviving passengers out of the 2214 on board the Titanic.

### Dataset Features
survived: Survival status (0 = No, 1 = Yes)
pclass: Passenger class (1 = 1st, 2 = 2nd, 3 = 3rd)
sex: Passenger's gender (male or female)
age: Passenger's age in years
sibsp: Number of siblings or spouses aboard
parch: Number of parents or children aboard
fare: Passenger fare
embarked: Port of Embarkation (C = Cherbourg; Q = Queenstown; S = Southampton)
name: Passenger's name
ticket: Ticket number
cabin: Cabin number
passengerid: Unique passenger identifier 

## Folders for Projects

Each project will be completed in its own folder.

- notebooks/project01 folder:
  - ml01.ipynb - COMPLETE THIS
  - ml01.py - working script with just the code
  - README.md - instructions - modify this to present your lab project


##  Daily Workflow

Please ensure that the prior steps have been verified before continuing.
When working on a project, we open just that project in VS Code.

### Git Pull from GitHub

Always start with `git pull` to check for any changes made to the GitHub repo.

```shell
git pull
```

### Run Checks as You Work

This mirrors real work where we typically:

1. Update dependencies (for security and compatibility).
2. Clean unused cached packages to free space.
3. Use `git add .` to stage all changes.
4. Run ruff and fix minor issues.
5. Update pre-commit periodically.
6. Run pre-commit quality checks on all code files (**twice if needed**, the first pass may fix things).
7. Run tests.

In VS Code, open your repository, then open a terminal (Terminal / New Terminal) and run the following commands one at a time to check the code.

```shell
git pull
uv sync --extra dev --extra docs --upgrade
uv cache clean
git add .
uvx ruff check --fix
uvx pre-commit autoupdate
uv run pre-commit run --all-files
git add .
uv run pytest
```

NOTE: The second `git add .` ensures any automatic fixes made by Ruff or pre-commit are included before testing or committing.
Running `uv run pre-commit run --all-files` twice may be helpful if the first time doesn't pass. 

<details>
<summary>Click to see a note on best practices</summary>

`uvx` runs the latest version of a tool in an isolated cache, outside the virtual environment.
This keeps the project light and simple, but behavior can change when the tool updates.
For fully reproducible results, or when you need to use the local `.venv`, use `uv run` instead.

</details>

### Build Project Documentation

Make sure you have current doc dependencies, then build your docs, fix any errors, and serve them locally to test.

```shell
uv run mkdocs build --strict
uv run mkdocs serve
```

- After running the serve command, the local URL of the docs will be provided. To open the site, press **CTRL and click** the provided link (at the same time) to view the documentation. On a Mac, use **CMD and click**.
- Press **CTRL c** (at the same time) to stop the hosting process.

###  Execute

This project includes demo code.
Run the demo Python modules to confirm everything is working.

In VS Code terminal, run:

```shell
uv run python notebooks/project01/ml01.py
```

A new window with charts should appear. Close the window to finish the execution. 
If this works, your project is ready! If not, check:

- Are you in the right folder? (All terminal commands are to be run from the root project folder.)
- Did you run the full `uv sync --extra dev --extra docs --upgrade` command?
- Are there any error messages? (ask for help with the exact error)

## Update this README as you work

Add commands to run additional scripts as you work through the course (update the path and file name as needed).

---

###  Git add-commit-push to GitHub

Anytime we make working changes to code is a good time to git add-commit-push to GitHub.

1. Stage your changes with git add.
2. Commit your changes with a useful message in quotes.
3. Push your work to GitHub.

```shell
git add .
git commit -m "describe your change in quotes"
git push -u origin main
```

This will trigger the GitHub Actions workflow and publish your documentation via GitHub Pages.

### Modify and Debug

With a working version safe in GitHub, start making changes to the code.

Before starting a new session, remember to do a `git pull` and keep your tools updated.

Each time forward progress is made, remember to git add-commit-push.
