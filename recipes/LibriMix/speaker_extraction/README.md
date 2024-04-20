# Recipe for target speaker extraction using Sepformer


You may find sepformer sources in `lobes/models/dual_path.py`.  Currently only simplified concatenation fusion of speaker embeddings is implemented.

## Setup
install requirements using
```bash
cd speechbrain
pip install -r requirements.txt
pip install --editable .`
```
and
```bash
cd recipes/LibriMix
pip install -r ../extra_requirements.txt
```

## Prepare data
Download librispeech (100h part is ok) and use [LibriMix scripts](https://github.com/JorisCos/LibriMix) to create mixes. Running these scripts will create Libri2Mix folder with `mix`, `s1` and `s2` subfolders, which contain mixed audio files and sources.

## Train

```bash
cd speechbrain/recipes/LibriMix/speaker_extraction
python train_tss.py hparams/sepformer-libri2mix-tss.yaml --data_folder "PATH_TO_DATA/data/Libri2Mix"
```

## TODO
- [ ] remove all changes from `lobes/models/dual_path.py` and create new module for speaker extraction
- [ ] add param to change speaker embedding fusion approach
