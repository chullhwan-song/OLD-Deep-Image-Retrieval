# Image-Retrieval
Image Retrieval using Deep Feature

## Instance benchmark dataset

| NO | Title | 카테고리 | link| category| query | all | |
| --- | --- | --- | --- |--- |--- |--- |--- |
| 1 | Oxford5k | landmark |[링크](http://www.robots.ox.ac.uk/~vgg/data/oxbuildings/) |  16  |  55 |  5,062 | 
| 2 | Paris6k| landmark |[링크](http://www.robots.ox.ac.uk/~vgg/data/parisbuildings/) |  11 | 55 |  6,412|
| 3 | Holidays | landmark |[링크](http://lear.inrialpes.fr/~jegou/data.php) |  500| 500|  1,491|
| 4 | Google-Landmarks | landmark | [링크](https://www.kaggle.com/c/landmark-recognition-challenge/data) |  12,894| 100,000 |  1,060,709 |
| 5 | UKBench | landmark  | [링크](https://archive.org/details/ukbench) |  2,550 | 10,200|  10,200|
| 6 | FlickrLogos-32| logo | [링크](http://www.multimedia-computing.de/flickrlogos/) |  32 | 500|  8,240|
|  7 | FlickrLogos-47| logo | [링크](http://www.multimedia-computing.de/flickrlogos/) |  47  | ? |  ? |
|  8 | INSTRE|  Instance  | [링크](http://isia.ict.ac.cn/dataset/instre.html) |  200  | N/A |  28,543 |
|  9 | ZuBuD|  landmark | [링크](http://www.vision.ee.ethz.ch/showroom/zubud/) |  200 |115 |  1,005|
|  10 | SMVS|  표지류 | [링크](http://web.cs.wpi.edu/~claypool/mmsys-dataset/2011/stanford/mvs_images/) |  1,200 |3,300|  1,200|
| 11 | DupImage| Instance   | [링크](https://pan.baidu.com/s/1jGETFUm) | 33 | 108 |  1,104 |
| 12 | Neural Codes | landmark |  [링크](http://sites.skoltech.ru/compvision/projects/neuralcodes/) | 672 | |  213,678 | 정제무- only text|

## [평가 방법](https://github.com/chullhwan-song/Image-Retrieval/issues/1)

## Learnable (fine-tuning using targeted datasets)
* QE performance remvoe
* GD : Global Descriptor
* LD :  Local Descriptor

| Paper | Oxf5k |  Par6k |  Oxf105k |  Par106k |  Holidays |descriptor | 비고 |  
| --- | --- | --- |--- |--- |--- |--- |--- |
| SOTA|  86.1 | 94.5  |  82.8  |  90.6  |  90.3/94.8 | |  |  |
| [1] |  86.1 | 94.5  |  82.8  |  90.6  |  90.3/94.8 |  GD | DIR, triplet, R-MAC |
| [2] |  83.8 | 85.0  | 82.6  | 81.7| | LD | delf, softmax |
| [3] | 79.7  | 83.8  | 73.9  |  76.4 | 82.5 | GD | siamense, R-MAC |

* [1] End-to-end Learning of Deep Visual Representations for Image Retrieval : [[paper]](https://arxiv.org/abs/1610.07940)[[review]](https://github.com/chullhwan-song/Reading-Paper/issues/17)
* [2] Large-Scale Image Retrieval with Attentive Deep Local Features : [[paper]](https://arxiv.org/abs/1612.06321)[[review]](https://github.com/chullhwan-song/Reading-Paper/issues/4)
   * delf는 QE+DIR과의조합을 통해 SOTA를 기록한 Case임.   
* [3] CNN Image Retrieval Learns from BoW: Unsupervised Fine-Tuning with Hard Examples

## Not Learnable (only trained on ImageNet)
| Paper | Oxf5k |  Par6k |  Oxf105k |  Par106k |  Holidays | Sculp6k | UKB | descriptor | 비고 |  
| --- | --- | --- |--- |--- |--- |--- |--- |--- |--- |
| SOTA|  0.712 |  0.805 |  0.672 | 0.733 | |  |  |
| [1] | 0.712 |  0.805 |  0.672 | 0.733 |  |  | |  GD | CAM |
| [2] | 53.3  |  67.0 | 48.9 |   | 71.6 | 37.7  | 84.2   | GD | MAC (first paper), Max pooling + l1 dist | 
 
* [1] Class-Weighted Convolutional Features for Visual Instance Search
* [2] Visual Instance Retrieval with Deep Convolutional Networks



 
