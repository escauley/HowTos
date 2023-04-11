# GitHub Setup: Preparing the Environment

## GH Paths
The `gh` is installed on Biowulf at `/data/CCBR_Pipeliner/db/PipeDB/bin/gh_1.7.0_linux_amd64/bin/gh`. You can run the following lines to edit your `~/.bashrc` file to add `gh` to your `$PATH`:
```bash
echo "export PATH=$PATH:/data/CCBR_Pipeliner/db/PipeDB/bin/gh_1.7.0_linux_amd64/bin" >> ~/.bashrc
source ~/.bashrc
```

## Creating PAT for GH 
You will need [gh cli](https://cli.github.com/) installed on your laptop or use `/data/CCBR_Pipeliner/db/PipeDB/bin/gh_1.7.0_linux_amd64/bin/gh` on biowulf. 

Personal Access Token (PAT) is required to access GitHub (GH) without having to authenticate by other means (like password) every single time. You can create a PAT by going [here](https://github.com/settings/tokens). Then you can copy the PAT and save it into a file on biowulf (say `~/gh_token`). Next, you can run the following command to set everything up correctly on biowulf (or your laptop)
```
gh auth login --with-token < ~/git_token
```

## Password-less Login

If you are like me and hate to re-enter (username and) password everytime you push/pull to/from github (or mkdocs gh-deploy), then it is totally worthwhile to spend a couple minutes to set up SSH keys for auto-authentication. 

It does not make any sense for me to repeat these, as the instructions are already available [here](https://blog.corsego.com/aws-cloud9-github-ssh).
