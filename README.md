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

```

You can treat/report CLIPScore and RefCLIPScore similarly to the other
evaluation metrics. See the paper for more details about CLIPScore and
RefCLIPScore.

## Command Line

If you're running on a dataset that's not MSCOCO, you aren't using the
standard MSCOCO evaluation format, or just want a simple command line
utility, you can use the code in this repo as follows:

```
python clipscore.py 
```