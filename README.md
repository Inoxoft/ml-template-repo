# ml-template-repo
A template repository for the 2021 Data-Focused Programming Bootcamp


### Install
- [install git lfs via apt or brew](https://packagecloud.io/github/git-lfs/install)
- ```git lfs install```
- type ```git lfs``` for help

### Add New Large Files
- to add new folders ```git lfs track "deploy/url_to_category/models/model_prod/**"```
- see whats tracked ```git lfs track```

### Push like normal
- ```git add -A``` 
- ```git commit -m ```
- ```git push origin xxx```
- if you mess up a commit ```git reset HEAD~```

### Pull
- ```git pull```
- ```git lfs fetch```
- ```git lfs checkout```


# The Repo

## Install

some docker files for various use cases:

- GPU Training
- CPU Training
- Deployment (intended to be as lightweight as possible)

```
source utils/builddocker.sh train-gpu-jupyter.Dockerfile
```

## Data

a home for data downloaders, athena queries etc..

```
source utils/runshell.sh
python -i data/url_to_category/download_tools.py
```

## Train

a model examples for training (and exporting models)

```
source utils/runnotebook.sh
#go to train folder and open the notebook
```

or

```
source utils/runshell.sh
#run automated hyperparameter searcher using hyperas
python train/example_AUTO.py
```

NOTE: it'll be useful to keep track of system resources while training, try `nvidia-smi` for GPU, `nload` for network, and `htop` for CPU.

## Deploy

a home for deployable models and test scripts

## Utils

a home for general purpose scripts (running a shell inside docker quickly etc...)

`source utils/runshell.sh`
or
`source utils/runnotebook.sh`
