# GAL-fWSD
Generative Adversarial Learning Towards Fast Weakly Supervised Detection

### Citing GAL-fWSD

If you find GAL-fWSD useful in your research, please consider citing:

```
@InProceedings{GAL-fWSD_2018_CVPR,
author = {Shen, Yunhang and Ji, Rongrong and Zhang, Shengchuan and Zuo, Wangmeng and Wang, Yan},
title = {Generative Adversarial Learning Towards Fast Weakly Supervised Detection},
booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
year = {2018}
}
```

### Installation

Clone and install the [CSC repository](https://github.com/shenyunhang/CSC.git).

### Usage

Note that GAL-fWSD in CSC repository does not contians the discriminator as described in the paper.

Although bringing unstable, it still approximates the performance in paper and speedups the training stage significantly.


To train and test a GAL-fWSD detector, use `experiments/scripts/gan_300.sh` or `experiments/scripts/gan_512.sh`.
Output is written underneath `$CSC_ROOT/output`.

```Shell
cd $CSC_ROOT
./experiments/scripts/gan_300.sh [GPU_ID] [NET] [DATASET] [--set ...]
# GPU_ID is the GPU you want to train on
# NET in {VGG_CNN_F, VGG_CNN_M_1024, VGG16} is the network arch to use
# DATASET in {pascal_voc, pascal_voc10, pascal_voc12, pascal_voc07+12, coco}
# --set ... allows you to specify configure options, e.g.
#   --set EXP_DIR seed_rng1701 RNG_SEED 1701
```

Example:

```Shell
./experiments/scripts/gan_300.sh 0 VGG16 pascal_voc --set EXP_DIR gan_300
```

This will reproduction approximate VGG16 result in paper.

Trained GAL-fWSD networks are saved under:

```
output/<experiment directory>/<dataset name>/
```

Test outputs are saved under:

```
output/<experiment directory>/<dataset name>/<network snapshot name>/
```
