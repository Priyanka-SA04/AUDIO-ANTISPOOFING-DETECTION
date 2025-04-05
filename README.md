# AASIST

This repository provides the overall framework for training and evaluating audio anti-spoofing systems proposed in ['AASIST: Audio Anti-Spoofing using Integrated Spectro-Temporal Graph Attention Networks'](https://arxiv.org/abs/2110.01200)

### Getting started
`requirements.txt` must be installed for execution. We state our experiment environment for those who prefer to simulate as similar as possible. 
- Installing dependencies
```
pip install -r requirements.txt
```
- Environment (for GPU training)
  - Based on a docker image: `pytorch:1.6.0-cuda10.1-cudnn7-runtime`
  - GPU: 1 NVIDIA Tesla V100
    - About 16GB is required to train AASIST using a batch size of 24
  - gpu-driver: 418.67

### Data preparation
We train/validate/evaluate AASIST using the ASVspoof 2019 logical access dataset [4].
```
python ./download_dataset.py
```
(Alternative) Manual preparation is available via 
- ASVspoof2019 dataset: https://datashare.ed.ac.uk/handle/10283/3336
  1. Download `LA.zip` and unzip it
  2. Set your dataset directory in the configuration file

### Training 
The `main.py` includes train/validation/evaluation.

To train AASIST [1]:
```
python main.py --config ./config/AASIST.conf
```

### Pre-trained models
Have provided pre-trained AASIST 

To evaluate AASIST [1]:
- It shows `EER: 0.83%`, `min t-DCF: 0.0275`
```
python main.py --eval --config ./config/AASIST.conf
```
### Additional Resources

- Research Document: [https://drive.google.com/file/d/1qJW6VPksBb9T4tdEqn_aVsmx7kkNW8Et/view?usp=drive_link]
- Documentation & Analysis: [https://drive.google.com/file/d/1uWnbLM74NI9ZQZUwdGr_kO6I8yggb08q/view?usp=drive_link]

