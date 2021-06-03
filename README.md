# wav2kws
Wav2kws is keyword spotting (KWS) based on Wav2Vec 2.0. This model shows state-of-the-art in Google Speech Commands datasets V1 and V2.

# Preparation

* [PyTorch](http://pytorch.org/) version >= 1.5.0
* Python version >= 3.6
* **To install fairseq** and develop locally:

``` bash
git clone https://github.com/pytorch/fairseq
cd fairseq
pip install --editable ./
```



The pretrained Wav2Vec 2.0 base model not finetuned (https://dl.fbaipublicfiles.com/fairseq/wav2vec/wav2vec_small.pt) must exist in the model directory.

# Training

```
python downstream_kws.py [pretrained model path] [dataset path] [saving model path]
```



And you can benchmark this model number of samples per each class.

```
python downstream_kws_benchmark.py [pretrained model path] [dataset path] [saving model path]
```



# Model Architecture

With Wav2Vec 2.0 as the backbone,  speech representation, output of transformer, is transferred to the structure of the model for speech commands recognition.

![image](https://user-images.githubusercontent.com/33983084/103804052-d8f13380-5094-11eb-92e5-fb11e2df2586.png)

# Performance

Accuracy of baseline models and proposed Wav2Keyword model on Google Speech Command Datasets V1 and V2 considering their 12 shared commands.

| Dataset    | Accuracy (%) |
| ---------- | ------------ |
| Dataset V1 | 97.9         |
| Dataset V2 | 98.5         |

Accuracy of baseline models and proposed Wav2Keyword model on Google Speech Command Dataset V2 with its 22 commands

| Dataset     | Accuracy (%) |
| ----------- | ------------ |
| Dataset V12 | 97.8         |

# Reference

[0] https://github.com/pytorch/fairseq/tree/master/examples/wav2vec

[1] https://arxiv.org/abs/1804.03209

[2] https://paperswithcode.com/sota/keyword-spotting-on-google-speech-commands