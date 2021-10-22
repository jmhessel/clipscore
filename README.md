# What's in here?

This repo contains the code for our EMNLP 2021 paper: [CLIPScore: A
Reference-free Evaluation Metric for Image
Captioning](https://arxiv.org/abs/2104.08718). CLIPScore is a metric
that you can use to evaluate the quality of an automatic image
captioning system.  In our paper, we show that CLIPScore achieves high
correlation with human judgment on literal image captioning
tasks. However, unlike BLEU or CIDEr, CLIPScore doesn't require
reference captions.

If you find the paper or this code useful, please consider citing:

```
@inproceedings{hessel2021clipscore,
  title={{CLIPScore:} A Reference-free Evaluation Metric for Image Captioning},
  author={Hessel, Jack and Holtzman, Ari and Forbes, Maxwell and Bras, Ronan Le and Choi, Yejin},
  booktitle={EMNLP},
  year={2021}
}
```

# How do I run the code?

There are two ways to run CLIPScore.


## Command Line

Example usage:
```
python clipscore.py 
```


You can use the code in this repo as follows:

```
python clipscore.py [candidates json] [image directory] [optional: reference json]
```

The candidates json should be a dictionary that maps from
`{"string_image_identifier": "candidate"}, e.g.,

```
{'image1': 'an orange cat and a grey cat are lying together.',
 'image2': 'a black dog looks at the camera.'
 ...}
```

The image directory should be a directory containing the images that
act as the keys in the candidates json, e.g.,

```
images/
├── image1.jpg
└── image2.jpg
```

And finally, 


## MSCOCO dataset in pycocoevalcap

If you're running on the MSCOCO dataset and using the standard
evaluation toolkit, you can use our version of
[pycocoevalcap](https://github.com/jmhessel/pycocoevalcap). To do
that, you can simply:

```
pip install git+https://github.com/jmhessel/pycocoevalcap.git
```

there is an example evaluation in that repo under
`examples/eval.py`. After pip installing, if you clone the repo and run

```
python eval.py
```

after a bit of time, the output should be:
```
Bleu_1: 0.579
Bleu_2: 0.404
Bleu_3: 0.279
Bleu_4: 0.191
METEOR: 0.195
ROUGE_L: 0.396
CIDEr: 0.600
SPICE: 0.133
CLIPScore: 0.528
RefCLIPScore: 0.605
```

You can treat/report CLIPScore and RefCLIPScore similarly to the other
evaluation metrics. See the paper for more details about CLIPScore and
RefCLIPScore.