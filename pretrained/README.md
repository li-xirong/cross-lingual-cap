# Pretrained Models

| Model | Training set | Image feature | Model Config | 
|:--- |:--- |:--- |:--- 
| [ruc_imcap_v0](http://lixirong.net/data/mm2017/ruc_imcap_v0.tar.gz) | flickr30k-cn train | [resnet-152_imagenet1k](http://data.mxnet.io/models/imagenet/resnet/152-layers/) | 30k_neuraltalk | 

## Requirements

* python 2.7
* mxnet for image feature extraction 
* tensorflow for caption generation.  

We have used virtualenv to setup a deep learning workspace that supports both mxnet and tensorflow.

```bash
virtualenv --system-site-packages ~/deepws
source ~/deepws/bin/activate
pip install --upgrade pip
# Install MXNet with GPU support using CUDA 8.0.
pip install mxnet-cu80==0.11.0
# Install tensorlfow
pip install --upgrade tensorflow
deactivate
```

## Code

As a light version of [fluent-cap](https://github.com/weiyuk/fluent-cap), [ruc_imcap](https://github.com/li-xirong/cross-lingual-cap/blob/master/pretrained/ruc_imcap.tar.gz) generates captions for novel images, without the performance evaluation module. The code has been tested on Ubuntu 14 and Mac OS X Yosemite. The unix-style bash script `do_ruc_imcap.sh` needs to be adapted in order to run on a windows machine. 

```bash
mkdir code && cd code
wget https://github.com/li-xirong/cross-lingual-cap/raw/master/pretrained/ruc_imcap.tar.gz
tar xzf ruc_imcap.tar.gz 
cd ruc_imcap
```

#### Process a toyset

```bash
python util/download_toyset.py  # this will generate a folder called toyset in $HOME/VisualSearch
source ~/deepws/bin/activate
./do_ruc_imcap.sh toyset  #set gpu_id=-1 if your computer has no gpu card
deactivate
```

Generated captions will be saved to `$rootpath/toyset/autocap/toyset/flickr30kzhbbosontrain/sample/30k_neuraltalk/vocab_count_thr_5/pyresnet-152_imagenet1k,flatten0_output,osl2/bs5/top0/top_one_pred_sent.txt`

## Process a new image collection

#### Prepare data

1. Create a new folder called `$test_collection` in `$HOME/VisualSearch`
2. Put all (jpeg) images in `$test_collection/ImageData`. Subfolders in `ImageData` are allowed. We assume image filenames are unique, because they will be used as keys to index both image features and generated sentences.

That's it. Please refer to the provided toyset to get a quick idea of how a test dataset is organized.


#### Perform captioning

```bash
source ~/deepws/bin/activate
./do_ruc_imcap.sh $test_collection
deactivate
```




