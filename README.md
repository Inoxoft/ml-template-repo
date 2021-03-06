# ml-template-repo
A template repository for the 2021 Data-Focused Programming Bootcamp

# The Repo

## Install (Mac/Linux)

some docker files for various use cases:

- GPU Training
- CPU Training
- Deployment (intended to be as lightweight as possible)

```
source utils/builddocker.sh minimal.Dockerfile
```
### Windows

```
cd (project base directory)
docker build -t projectname install/ -f install/minimal.Dockerfile
```


## Data

a home for data downloaders, athena queries etc..

```
source utils/runshell.sh
python -i data/url_to_category/download_tools.py
```

### Windows 

```
cd (repo name)
docker run -v ${PWD}:/tf -it --rm -p 8888:8888 projectname
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
