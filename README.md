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

This repository serves as a central index for LaTeX projects synced between GitHub, Overleaf, and local computers.

> [!IMPORTANT]
> Overleaf GitHub Sync connects one complete Overleaf project to one GitHub repository. It cannot connect an Overleaf project directly to a subfolder of this repository.
>
> Each Overleaf project must keep its own GitHub repository. This central repository references those projects as Git submodules.

## Adding a synced Overleaf project

For example, the Overleaf project **Cellular-Automata-and-Groups-Notes** is linked directly to:

`boofula/Cellular-Automata-and-Groups-Notes`

Add it to this central repository as a submodule:

```bash
   git clone git@github.com:boofula/Will_Bales_LaTex_Projects.git
   cd Will_Bales_LaTex_Projects
   
   mkdir -p synced/personal-research
   git submodule add https://github.com/boofula/Cellular-Automata-and-Groups-Notes.git \
  synced/personal-research/Cellular-Automata-and-Groups-Notes

   git add .gitmodules synced/personal-research/Cellular-Automata-and-Groups-Notes
   git commit -m "Add Cellular Automata notes as synced project"
   git push origin main
```
## Cloning this repository


Clone the central repository and all referenced LaTeX projects:


Bash




```
git clone --recurse-submodules git@github.com:boofula/Will_Bales_LaTex_Projects.git

```





If the repository was already cloned without its submodules:


Bash




```
git submodule update --init --recursive

```





## Editing a synced project locally


Each submodule is an independent Git repository. To edit and sync a project, work from inside its directory:


Bash




```
cd synced/personal-research/Cellular-Automata-and-Groups-Notes

git pull --ff-only origin main
# Edit LaTeX files.
git add -A
git commit -m "Update notes"
git push origin main

```





Then, in Overleaf, select **Pull from GitHub** to retrieve the local changes.


## Editing in Overleaf



1. Before editing, select **Pull from GitHub** in Overleaf.

2. Make and compile changes.

3. Select **Push to GitHub** when finished.

4. Locally, enter the project submodule directory and pull the updates:


Bash




```
cd synced/personal-research/Cellular-Automata-and-Groups-Notes
git pull --ff-only origin main

```



## Updating the central repository


After pushing a new commit from a submodule, update the central repository's recorded project revision:


Bash




```
cd ../../..
git add synced/personal-research/Cellular-Automata-and-Groups-Notes
git commit -m "Update Cellular Automata notes reference"
git push origin main

```





This parent-repository commit does not duplicate project files. It records the exact commit of the project repository referenced by the central repository.


## Avoiding conflicts


Do not edit the same project simultaneously in Overleaf and locally.


Always follow this order:



1. Pull the newest changes.

2. Make edits in one location.

3. Commit and push the changes.

4. Pull the updates in the other location before editing there.



If Git reports a conflict, resolve it locally, commit the resolution, push it to GitHub, and then select **Pull from GitHub** in Overleaf.

