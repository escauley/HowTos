## Everything about managing repos!

### Creating new repository

To create a new repository under the [**CCBR** org account](https://github.com/CCBR) on Github using [gh cli](https://cli.github.com/), you can run the following command on [Biowulf](https://hpc.nih.gov)

```bash
% gh repo create CCBR/<reponame> \
--description "<repo description>" \
--public \
--confirm
```
> **NOTE**: If you drop the `CCBR/` from the `gh` command above, then the new repo is created under your GitHub handle. 

If you wish to create a new repository based on the CCBR Snakemake Pipeline Cookie Cutter template [repository](https://github.com/CCBR/CCBR_SnakemakePipelineCookiecutter) then run:

```bash
% gh repo create CCBR/<reponame> \
--description "<repo description>" \
--public \
--template CCBR/CCBR_SnakemakePipelineCookiecutter \
--confirm
```

This will:
 * create a new repository under [**CCBR** org account](https://github.com/CCBR), and
 * copy over the template code from [CCBR_SnakemakePipelineCookiecutter](https://github.com/CCBR/CCBR_SnakemakePipelineCookiecutter)


> **NOTE** `gh` is installed on Biowulf at `/data/CCBR_Pipeliner/db/PipeDB/bin/gh_1.7.0_linux_amd64/bin/gh`. You can run the following lines to edit your `~/.bashrc` file to add `gh` to your `$PATH`:
> ```bash
> % echo "export PATH=$PATH:/data/CCBR_Pipeliner/db/PipeDB/bin/gh_1.7.0_linux_amd64/bin" >> ~/.bashrc
> % source ~/.bashrc
> ```

Once the repo is created, then you can clone a local copy of the new repository:

```bash
gh repo clone CCBR/<reponame>.git
```

> **NOTE**: You can change `--public` to `--private` in the above `gh` command to make the newly created repository private.


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
git create -b <newbranch>
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