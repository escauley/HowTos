### Creating PAT for GH 
You will need [gh cli](https://cli.github.com/) installed on your laptop or use `/data/CCBR_Pipeliner/db/PipeDB/bin/gh_1.7.0_linux_amd64/bin/gh` on biowulf. 

Personal Access Token (PAT) is required to access GitHub (GH) without having to authenticate by other means (like password) every single time. You can create a PAT by going [here](https://github.com/settings/tokens). Then you can copy the PAT and save it into a file on biowulf (say `~/gh_token`). Next, you can run the following command to set everything up correctly on biowulf (or your laptop)
```
gh auth login --with-token < ~/git_token
```
