# TinyWASE
Implementation of our paper [Compressing Speaker Extraction Model with Ultra-low Precision Quantization and Knowledge Distillation]. 

## Getting Started
The training samples are generated by randomly selecting speeches of different speakers from *si_tr_s* of WSJ0, and mixing them at various signal-to-noise ratios (SNR). The evaluating samples are generated by fixed list *./data/wsj/mix_2_spk_voiceP_tt_WSJ_dellnode.txt*. Please modify the dataset path in *./data/preparedata.py* according to your actual path.
```python
data_config['speechWavFolderList'] = ['FOLDER_TO_SPEECH_FILES']
data_config['spk_test_voiceP_path'] = 'PATH_TO_SPK_TEST_VOICEP_FILE'
```

We advise you to utilize the pickle file, which could speed up experiments by saving time for frequency resampling. You could modify the pickle path to anywhere you like.
```python
data_config['train_sample_pickle'] = 'PATH_TO_TRAIN_SAMPLE_PICKLE'
data_config['test_sample_pickle'] = 'PATH_TO_TEST_SAMPLE_PICKLE'
```

### Training
Specify the path for --restore_teacher, --pretrained and --log in train_tinywase.py and run the bash.

```bash
python train_tinywase.py
```

### Evaluation
Specify the path for --restore, --log　in eval_tinywase and run the bash.

```bash
python eval_tinywase.py
```

## Citations
If you find this repo helpful, please consider citing:

```
@article{huang2021compress,
  title={Compressing Speaker Extraction Model with Ultra-lowPrecision Quantization and Knowledge Distillation},
  author={Huang, Yating and Hao, Yunzhe and Xu, Jiaming and Zhang, Peng and Xu, Bo}
}
```

```
@inproceedings{hao2021wase,
  title={Wase: Learning When to Attend for Speaker Extraction in Cocktail Party Environments},
  author={Hao, Yunzhe and Xu, Jiaming and Zhang, Peng and Xu, Bo},
  booktitle={ICASSP 2021-2021 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  pages={6104--6108},
  year={2021},
  organization={IEEE}
}
```

```
@article{hao2020unified,
  title={A Unified Framework for Low-Latency Speaker Extraction in Cocktail Party Environments},
  author={Hao, Yunzhe and Xu, Jiaming and Shi, Jing and Zhang, Peng and Qin, Lei and Xu, Bo},
  journal={Proc. Interspeech 2020},
  pages={1431--1435},
  year={2020}
}
```

## License

Apache License 2.0. 
