# Diffusion Models 

## Reference

- Survey: [Arxiv](https://arxiv.org/pdf/2209.00796.pdf) [GitHub](https://github.com/YangLing0818/Diffusion-Models-Papers-Survey-Taxonomy)
- Variational Diffusion Models: [NeurIPS](https://proceedings.neurips.cc/paper/2021/file/b578f2a52a0229873fefc2a4b06377fa-Paper.pdf) 

## Applications

- Computer Vision
- Natural Language Processing
- Waveform Signal Processing
- Molecular Graph Modeling
- Time Series Modeling
- Adversarial Purification
- Multi-Modal Modeling, e.g., Text -> Image or Text -> Audio

## Approach

Two (**2**) Processes:
  1. **Forward Process** (Disturbs data distribution by adding noise at multiple scales)
  2. **Reverse Process** (Restores the data structure)


### Understanding
  1. Very deep hierarchical **Variable Auto Encoders** (**VAE**)
  2. Or Discretized **Stochastic Differential Equations** (**SDE**)


## Models

### Autoregressive

-[ARDM](https://openreview.net/pdf?id=Lm8T39vLDTE)


## Applications

### Computer Vision

#### Image Generation

##### Image Super Resolution and Inpainting

- Super Resolution Diffusion (SRDiff): Based on likelihood of data
- Super Resolution via Repeated Refinement (SR3): Iterative denoising
- Latent Diffusion Models (LDM): Used pretrained auto-encoders
- RePaint: Update sampling 

##### Semantic Segmentation

##### Anomaly Detection

##### Point Cloud Completion and Detection

- PVD
- Point Diffusion Refinement (PDR): Particles in thermodynamic system to heat bath.

#### Video Generation

- Flexible Diffusion Model (FDM)
- Residual Video Diffusion (RVD): autoregressive
- Video Diffusion Model (VDM): Conditional sampling [Best]

### Natural Language Processing

### Waveform Signal Processing 

#### Speech generation:

- WaveGrad: Gaussian white noise as input, iteratively refines the signal with gradient based sampler. Autoregressive
- [DiffWave](https:://arxiv.org/pdf/2009.09761.pdf): Diffusion probablistic model for conditiona and/or unconditional waveform generation. 

