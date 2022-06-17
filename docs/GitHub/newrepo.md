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