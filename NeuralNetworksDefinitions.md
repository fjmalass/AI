# Some Definition

## 1. Transposed Convolution Layer `nn.ConvTranspose2d` (`PyTorch`)

* Reference: [D2l](https://d2l.ai/chapter_computer-vision/transposed-conv.html)

* Usage: Upsampling and filtering that is learned

* Drawback: Creates blocking artifacts

## 2. Squeeze-And-Excitation Module [[Paper](https://arxiv.org/pdf/1709.01507v4.pdf)] [[Code](https://gihub.com/hujie-frank/SENet)]

* `Pool` -> `conv` -> `activation` (e.g. `h-swish`) -> `conv` -> `sigmoid`

* Used in MobileNet (Pose estimation)
* Purpose: Used for recalibration within the network (multiply channels instead of batch normalization)
  - Early layers: excites informative features in a class-agnostic manner
  - Later layers: very class specific


## 3. Hourglass [[Paper](https://arxiv.org/pdf/1603.06937.pdf)]
