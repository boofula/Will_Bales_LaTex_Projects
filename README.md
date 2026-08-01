# Will_Bales_LaTex_Projects

This repository contains LaTeX projects created by Will Bales. The goal of this repository is to have a mediating point between my local LaTeX compiler and Overleaf. This allows for the option of using either Overleaf or my local compiler to write in LaTeX while maintaining consistent projects between both points. Since Overleaf only works online, it may be beneficial a local compiler so that work may still continue. On the other hand, Overleaf provides collaborative services that a local compiler could never provide intuitively.

## Organization choice

This repository is split into two top-level folders:

- `synced/` for projects that should stay aligned with Overleaf
- `local/` for projects that are better kept outside of Overleaf sync

This keeps the repository flexible: coursework, shared writing, and polished documents can live in `synced/`, while drafts, experiments, archives, or private work can live in `local/`.

## Category folders

Both top-level folders use the same category layout so projects can be moved between them without reorganizing everything:

- `classnotes/`
- `homework/`
- `templates/`
- `personal-research/`
- `academic-research/`
- `professional-documents/`
- `presentations/`
- `projects/`
- `teaching/`
- `writing/`
- `archives/`

## Suggested usage

- Create one folder per LaTeX project inside the matching category.
- Keep Overleaf-connected projects in `synced/`.
- Keep drafts, older work, and anything that does not need Overleaf in `local/`.

# LaTeX Project Sync Workflow

This repository is synced with a single Overleaf project and can also be used from a local computer.

> [!IMPORTANT]
> Overleaf GitHub Sync connects one complete Overleaf project to one GitHub repository. It cannot sync separate projects into subfolders of the same repository.
>
> For additional Overleaf projects, create a separate GitHub repository for each one.

## Initial setup

1. In Overleaf, open the project to sync.
2. Select **Menu → Sync → GitHub**.
3. Link this repository: `boofula/Will_Bales_LaTex_Projects`.
4. On the local computer, clone the repository:

   ```bash
   git clone git@github.com:boofula/Will_Bales_LaTex_Projects.git
   cd Will_Bales_LaTex_Projects

## Local editing workflow

Before making changes, retrieve updates made through Overleaf:

Bash

```
git pull --ff-only origin main

```

After making local changes:

Bash

```
git add -A
git commit -m "Describe the change"
git push origin main

```

## Overleaf workflow

1. Before editing in Overleaf, select **Pull from GitHub**.

2. Make and compile changes in Overleaf.

3. Select **Push to GitHub** when finished.

## Avoiding conflicts

Do not edit the same files in Overleaf and locally at the same time.

Always follow this order:

1. Pull the newest changes.

2. Make edits in one place.

3. Commit and push the changes.

4. Pull the updates in the other place before editing there.

If Git reports a conflict, resolve it locally, commit the resolution, push it to GitHub, and then pull from GitHub in Overleaf.
