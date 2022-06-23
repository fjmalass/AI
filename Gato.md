# GATO  A generalist Agent
2022-05-14
## Encoding
* Text: 32000 Subwords with SentencePiece
* Images: non overlapping 16x16 patches in raster order, ViT  normalized to [-1, 1] with sqrt(16)
* Atari button pressed [ row-major sequence of integers within the range of [0, 1024)]
* Proprioceptive inputs , sequences of floating points in row-major order. (mu-law included to -1, 1)
* Uses timesteps as observation tokens then action tokens

# Embeddings
* Text tokens: embedding via lookup table into a leanred vector embedding space. 
* Image patches: Single Resnet block to abtain a vector per patch. add a leanable within-image 2d offset of patch. 

use transformer: Vaswani 2017
