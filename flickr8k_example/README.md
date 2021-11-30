## What's in here?

This directory contains code that replicates the experiments we ran to
compute correlation with human judgments in the Flickr8K corpus. This
setup has been used in prior work, but there are a number of specific
settings one needs to use to replicate the original results from the
SPICE paper, who are the first to run in this setup. More details are
available in appendix A of:

CLIPScore: A Reference-free Evaluation Metric for Image Captioning
by Jack Hessel, Ari Holtzman, Maxwell Forbes, Ronan Le Bras, Yejin Choi
https://arxiv.org/abs/2104.08718

## How do I run the code?

There are three steps:

1. run `download.py` which downloads and preprocesses the Flickr8K corpus.
2. run `compute_metrics.py` which will compute the appropriate evaluation metrics.
3. run `correlate_with_human.py` which will report the correlation between evaluation metrics and human judgments.