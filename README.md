# DevOps Git Workflow Project

A demonstration of Git best practices applied to a DevOps project. This repo covers proper branching strategy, pull requests, tagging, .gitignore usage, and markdown documentation — all as part of a DevOps internship task series.

---

## Tech Stack

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

---

## Project Structure

```
devops-git-workflow/
├── docs/
│   └── tasks.md       # Markdown documentation of all internship tasks
├── .gitignore         # Files and folders excluded from version control
└── README.md          # Project documentation
```

---

## Branching Strategy

This project follows a standard Git feature branch workflow:

```
main
 └── dev
      └── feature/add-docs
```

| Branch | Purpose |
|---|---|
| `main` | Stable, production-ready code |
| `dev` | Integration branch for completed features |
| `feature/add-docs` | Feature branch for adding task documentation |

### Workflow Used
1. Created `dev` branch off `main`
2. Created `feature/add-docs` branch off `dev`
3. Made changes on the feature branch
4. Opened a Pull Request from `feature/add-docs` → `dev`
5. Merged after review
6. Opened a Pull Request from `dev` → `main`
7. Merged to bring changes into production branch

---

## Pull Requests

Two pull requests were created and merged as part of this workflow:

**PR 1** — `feature/add-docs` → `dev`
Added task documentation in the `docs/` folder covering all four DevOps internship tasks.

**PR 2** — `dev` → `main`
Promoted all completed and reviewed changes from the integration branch into main.

---

## Git Tag

A tag was created to mark the completion of all four DevOps tasks:

```bash
git tag -a v1.0.0 -m "completed all four devops tasks"
git push origin v1.0.0
```

Tags are used in Git to mark specific points in history as important — typically used for releases or milestones.

---

## .gitignore

The `.gitignore` file excludes files that should not be tracked in version control:

```
node_modules/
.env
*.log
.terraform/
terraform.tfstate
terraform.tfstate.backup
.DS_Store
dist/
coverage/
```

This prevents sensitive files like `.env`, generated files like `node_modules/`, and Terraform state files from being accidentally committed to the repo.

---

## Task Documentation

All four DevOps internship tasks are documented in [`docs/tasks.md`](docs/tasks.md):

| Task | Description |
|---|---|
| Task 1 | CI/CD pipeline with GitHub Actions and Docker |
| Task 2 | CI/CD pipeline with Jenkins on Windows |
| Task 3 | Infrastructure as Code with Terraform and Docker |
| Task 4 | Version control workflow with Git best practices |

---

## Key Git Commands Used

```bash
# Create and switch to a new branch
git checkout -b feature/add-docs

# Stage and commit changes
git add .
git commit -m "feature: add task documentation"

# Push branch to remote
git push origin feature/add-docs

# Create an annotated tag
git tag -a v1.0.0 -m "completed all four devops tasks"
git push origin v1.0.0

# View all tags
git tag

# View commit history
git log --oneline
```

---

## Key Concepts Demonstrated

**Branching**
Isolating work in separate branches keeps the main branch stable and allows multiple features to be developed in parallel without interfering with each other.

**Pull Requests**
PRs provide a review mechanism before merging code. They create a clear history of what was changed, why, and when.

**Git Tags**
Tags mark specific commits as significant milestones, commonly used for versioning releases like `v1.0.0`.

**.gitignore**
Prevents unnecessary or sensitive files from being tracked, keeping the repository clean and secure.

**Markdown Documentation**
Documenting projects in markdown makes them readable directly on GitHub without any additional tools.
