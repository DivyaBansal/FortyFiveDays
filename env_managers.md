PIP
```
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt

deactivate


pip cache remove *
pip cache purge
```

CONDA 
```
conda create --name py35 python=3.5
source activate py35
conda env list
conda create --clone py35 --name py35-2
conda env remove --name py35
conda env create --file bio-env.txt 
source deactivate
```

Useful commands:
export HF_DATASETS_CACHE="/path/to/another/directory"