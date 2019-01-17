# Image-Retrieval
Image Retrieval using Deep Feature

* QE performance remvoe
* GD : Global Descriptor
* LD :  Local Descriptor

## Learnable (fine-tuning using targeted datasets)
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
| [2] | 53.3  |  67.0 | 48.9 |   | 71.6 | 37.7  | 84.2   | GD | MAC (first paper) | 

   

 Oxford5k Paris6k Sculp6k Holidays UKB Ox105k
 
* [1] Class-Weighted Convolutional Features for Visual Instance Search
* [2] Visual Instance Retrieval with Deep Convolutional Networks

