# GitHub Setup: Repository!

## Repository Location

- All CCBR developed pipelines should be created under [CCBR's GitHub Org Account](https://github.com/CCBR/).

## Use of CookieCutter Templates

- All CCBR developed pipelines should be created from the appropriate cookiecutter template:
    - TechDev Projects: https://github.com/CCBR/CCBR_CCBRTechDevCookieCutter
    - Snakemake Pipelines: https://github.com/CCBR/CCBR_SnakemakePipelineCookiecutter

## Creating a new repository
- To create a new repository on Github using [gh cli](https://cli.github.com/), you can run the following command on [Biowulf](https://hpc.nih.gov) update the new repository name (<ADD NEW REPO NAME>) and the repository description (<ADD REPO DESCRIPTION>) commands below. **NOTE** Do not remove the `CCBR/` leading the repository name, as this will correctly place the repository under the CCBR organizaiton account.

```bash
gh repo create CCBR/<ADD NEW REPO NAME> \
--template CCBR/CCBR_SnakemakePipelineCookiecutter \
--description "<ADD REPO DESCRIPTION>" \
--public \
--confirm
```

- Once the repo is created, then you can clone a local copy of the new repository:

```bash
gh repo clone CCBR/<reponame>.git
```

## GitHub Functions
- The following outlines basic GitHub function to `push` and `pull` from your repository. It also includes information on creating a new branch and deleting a branch. These commands should be used in line with guidance on [GitHub Repo Management](https://ccbr.github.io/HowTos/GitHub/sop_repo/).

### Pushing local changes to remote

Check which files have been changed.

```bash
git status
```

Stage files that need to be pushed
```bash
git add <thisfile>
git add <thatfile>
```

Push
```bash
git push
```

### Pulling remote changes to local

Simply,
```bash
git pull
```

This will not work if you have local changes. Then you have 2 choices:

- ignore local changes and pull remote
```bash
git reset --hard
git pull
```
- temporarily stash changes away, pull and reapply changes
```bash
git stash
git pull
git stash pop
```

### Creating a new branch

This is a two step process.

  * Create the branch locally
```bash
git checkout -b <newbranch>
```

 * Push the branch to remote
```bash
git push -u origin <newbranch>
```
OR
```bash
git push -u origin HEAD
```
This is a shortcut to push the current branch to a branch of the same name on `origin` and track it so that you don't need to specify `origin HEAD` in the future.


### Deleting branches

#### Locally

```bash
git branch -d <BranchName>
```

#### on GitHub

```bash
git push origin --delete <BranchName>
```