# Deep Image Retrieval
Image Retrieval using Deep Feature

## My Experiements 

##### notify
* My individual review  is that methods such as multiscale input images, multiple backbone networks, QE, etc. are not practical and are just tricks to increase performance. In this experiments, I avoid the above mentioned methods as much as possible, and I will try to achieve SOTA in a way that is as true to the basics as possible.
* These results show only the best results for each evaluation set(Oxford5k, Paris6k, Holidays) among the results of applying the model generated during training. 
That is, it is not a result of a single model. Of course, one model may yield the best results for all evaluation sets.
* In case of npair loss, normalization is not performed in the last layer. The reason was not learned.
* using tensorflow(tf) and pytorch(pt)
* P of the gem was fixed at 3. In the future, I plan to continue tuning around 3. > [hint](https://github.com/lyakaap/Landmark2019-1st-and-3rd-Place-Solution/issues/7)

##### update : 2020-01-08

| NO | net| feat | Holidays  | Paris6k  | Oxf5k |  dim | loss | trainset | pre-trained| lib |
| :---: | :---: | :---: | :---: |:---: |:---: |:---: |:---: |:---: |:---: |:---: |
| [1] | alexnet | fc6 |    0.789   |   |  0.557 |  128 | cls  |  neuralcode | imgnet |
|  | res152 | gem        | 0.9026 | 0.8927 |	0.7808  | 1024 | npairs  |  nc | imgnet | tf |
|  | res152 | gem:single | 0.9001 |  0.8927 |	0.7507 | 1024 | npairs  |  nc | imgnet | tf |
|  | res152 | mac        | 0.8823 | 0.833 |  0.7357  | 1024 | npairs  |  nc | imgnet | tf |
|  | res152 | mac:single |  0.8805  | 0.833 |  0.7357   | 1024 | npairs  |  nc | imgnet | tf |
|  | res152 | spoc        | 0.8626 | 0.7366 |  0.5833   | 1024 | npairs  |  nc | imgnet | tf |
|  | res152 | spoc:single | 0.8626 | 0.7366 |  0.5833   | 1024 | npairs  |  nc | imgnet | tf |
|  | res101 | r-mac  | 0.83 |  0.852 |  0.74   | 1024 | triplet  |  nc | imgnet | pyt |


* refer[1] : Neural Codes for Image Retrieval : [[paper]](https://arxiv.org/abs/1404.1777)[[review]](https://github.com/chullhwan-song/Reading-Paper/issues/14)
* nc: neuralcode clean dataset
* triplet : triplet loss
* imgnet : imagenet
* tf : tensorflow
* pyt : pytorch

## Instance benchmark dataset

| NO | Title | 카테고리 | link| category| query | all | 비고  |
| --- | --- | --- | --- |--- |--- |--- |--- |
| 1 | Oxford5k | landmark |[링크](http://www.robots.ox.ac.uk/~vgg/data/oxbuildings/) |  16  |  55 |  5,062 | 
| 2 | Paris6k| landmark |[링크](http://www.robots.ox.ac.uk/~vgg/data/parisbuildings/) |  11 | 55 |  6,412|
| 3 | Holidays | landmark |[링크](http://lear.inrialpes.fr/~jegou/data.php) |  500| 500|  1,491|
| 4 | Google-Landmarks_V1 |landmark |[링크](https://www.kaggle.com/c/landmark-recognition-challenge/data) | 12,894| 100,000 |  1,060,709 | textbysearch |
| 4 | Google-Landmarks_V2 | landmark | [링크](https://github.com/cvdfoundation/google-landmark) | 203,094 | 117,577 | 5,012,248 | textbysearch |
| 5 | UKBench | landmark  | [링크](https://archive.org/details/ukbench) |  2,550 | 10,200|  10,200|
| 6 | FlickrLogos-32| logo | [링크](http://www.multimedia-computing.de/flickrlogos/) |  32 | 500|  8,240|
|  7 | FlickrLogos-47| logo | [링크](http://www.multimedia-computing.de/flickrlogos/) |  47  | ? |  ? |
|  8 | INSTRE|  Instance  | [링크](http://isia.ict.ac.cn/dataset/instre.html) |  200  | N/A |  28,543 |
|  9 | ZuBuD|  landmark | [링크](http://www.vision.ee.ethz.ch/showroom/zubud/) |  200 |115 |  1,005|
|  10 | SMVS|  표지류 | [링크](http://web.cs.wpi.edu/~claypool/mmsys-dataset/2011/stanford/mvs_images/) |  1,200 |3,300|  1,200|
| 11 | DupImage| Instance   | [링크](https://pan.baidu.com/s/1jGETFUm) | 33 | 108 |  1,104 |
| 12 | Neural Codes | landmark |  [링크](http://sites.skoltech.ru/compvision/projects/neuralcodes/) | 672 | |  213,678 | textbysearch |

## [평가 방법](https://github.com/chullhwan-song/Image-Retrieval/issues/1)

## Learnable (fine-tuning using targeted datasets)
* QE performance remove
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



 
