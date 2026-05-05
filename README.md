# Face-Driven Zero-Shot Voice Conversion on Low Resource Languages

## Training
2. Extract wav from dataset videos
```python
python Tools/preprocess/extract_wav_from_video.py 
```
3. Extract mel and lf0 from wav
```python
python Tools/preprocess/extract_wav_feature.py
```
4. Extract face feature 
```python
python Tools/Preprocess/extract_face_feature.py
```
5. Extract speech feature
```
python Tools/Preprocess/extract_spk_emb.py
```

- Step2. Model training
1. ParallelWaveGAN is used as the vocoder, so firstly please install [ParallelWaveGAN](https://github.com/kan-bayashi/ParallelWaveGAN)

2. Download the pretrained [VQMIVC](https://drive.google.com/drive/folders/1u8xAJdJEQ3MKfTDSks1xFkTcR2CXdfAd?usp=sharing) and place it in folder pretrained

3. Training model
```
./run_shell/train.sh
```
- Step3. Inference 
1. Preprocess the samples for inference following Step 1. The IDs of the preprocessed samples can be found in the files "test_src_speakers.txt" and "test_tar_speakers.txt."
3. Pretrained FVMVC can be found in [here](https://drive.google.com/file/d/1jgTCIa-78SRm6J3uxaah6DdQe4frtUeX/view?usp=drive_link)

2. Runing inference
```
./run_shell/inference.sh
```



## Citation
The base paper we used and improved upon:
```
@inproceedings{10.1145/3581783.3613825,
author = {Sheng, Zheng-Yan and Ai, Yang and Chen, Yan-Nian and Ling, Zhen-Hua},
title = {Face-Driven Zero-Shot Voice Conversion with Memory-Based Face-Voice Alignment},
year = {2023},
isbn = {9798400701085},
url = {https://doi.org/10.1145/3581783.3613825},
doi = {10.1145/3581783.3613825},
booktitle = {Proceedings of the 31st ACM International Conference on Multimedia},
pages = {8443–8452},
location = {Ottawa ON, Canada},
}
```

## Acknowledgements:
* The voice conversion backbone is borrowed from [VQMIVC](https://github.com/Wendison/VQMIVC)
* The vocoder is borrowed from [ParallelWaveGAN](https://github.com/kan-bayashi/ParallelWaveGAN)
