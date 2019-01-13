# Cross-Lingual Image Captioning

Image captioning has so far been explored mostly in English, as most available datasets are in this language. However, the application of image captioning should not be restricted by language. The study of cross-lingual image captioning is essential for a large population on the planet who cannot speak English. We are developing novel algorithms that enable learning an image captioning model for a target language other than English, with minimal labeling effort.

<img src="conceptual.jpg" alt="cross-lingual image captioning" width="500">


## Code

* [Fluent-cap: Fluency-guided image captioning](https://github.com/weiyuk/fluent-cap)

## Datasets

* [Flickr8k-cn (59MB)](http://lixirong.net/data/mm2017/flickr8k-cn.tar.gz)
* [Flickr30k-cn (236MB)](http://lixirong.net/data/mm2017/flickr30k-cn.tar.gz)

|  | Flickr8k-cn |||  Flickr30k-cn |||
|:--- | -----:| -----:| -----:| -----:| -----:| -----:|
|        | train| val | test | train | val | test |
| Images | 6,000 | 1,000 | 1,000| 29,783 | 1,000 | 1,000|
| Human-annotated <br/> Chinese sentences      | 30,000 | 5,000 | 5,000 |  -- | -- |  --  |
| Machine-translated <br/> Chinese sentences | 30,000 | 5,000 | -- | 148,915 | 5,000 | -- |
| Human-translated <br/> Chinese sentences   | --     | --    | 5,000 |  -- | -- | 5,000|

#### Performance table

Automated evaluation of five approaches to cross-lingual image captioning. Rejection sampling and weighted loss are comparable to *Without fluency* which learns from the full set of machine-translated sentences.

|  | Flickr8k-cn |||  Flickr30k-cn |||
|:--- | -----:| -----:| -----:| -----:| -----:| -----:|
|        | BLEU-4| ROUGE | CIDEr | BLEU-4| ROUGE | CIDEr
| Late translation  | 17.3 | 39.3 | 33.7 | 15.3 | 38.5 | 27.1 |
| Without fluency   | 24.1 | 45.9 | 47.6 | 17.8 | 40.8 | 32.5 |
| Fluency-only      | 20.7 | 41.1 | 35.2 | 14.5 | 35.9 | 25.1 |
| Rejection sampling| 23.9 | 45.3 | 46.6 | 18.2 | 40.5 | 32.9 |
| Weighted loss     | 24.0 | 45.0 | 46.3 | 18.3 | 40.2 | 33.0 |


## Pre-trained Models

[ruc_imcap](pretrained): generate Chinese captions for novel images using one script

## Publications

1. Xirong Li, Chaoxi Xu, Xiaoxu Wang, Weiyu Lan, Zhengxiong Jia, Gang Yang, Jieping Xu, COCO-CN for Cross-Lingual Image Tagging, Captioning and Retrieval, IEEE Transactions on Multimedia, 2019 (in press)
2. Weiyu Lan, Xirong Li, Jianfeng Dong, [Fluency-Guided Cross-Lingual Image Captioning](https://arxiv.org/abs/1708.04390), ACM MM 2017
3. Qijie Wei, Xiaoxu Wang, Xirong Li, [Harvesting Deep Models for Cross-Lingual Image Annotation](https://doi.org/10.1145/3095713.3095751), CBMI 2017
4. Xirong Li, Weiyu Lan, Jianfeng Dong, Hailong Liu, [Adding Chinese Captions to Images](https://doi.org/10.1145/2911996.2912049), ACM ICMR 2016

## Acknowledgements

This project was supported by the National Natural Science Foundation of China (No. 61672523).
