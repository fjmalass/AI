# Human Poses

## Competition

- 2022-08-26 [`WodProofApp`](https://wodproofapp.com)

## 2022-07-30

- `NVidia` [`BodyPose3DNet`](https://catalog.ngc.nvidia.com/orgs/nvidia/teams/tao/models/bodypose3dnet)
- `MediaPipe` [Body Pose](https://google.github.io/mediapipe/solutions/pose)
- [`Tutorial GitHub`](https://github.com/cbsudux/Human-Pose-Estimation-101)
- [`Panopic CMU`](http://domedb.perception.cs.cmu.edu/) Occluded Multi Person Pose
data capture

### Pose

1. Loss:

- Mean Squared Error
- Regression model

2. Evaluation Metrics:

- __PCP__: Percentage of Correct Parts (Correctness of limbs)

  - Limb is detected if distance between two predicted joint locations and the
  true limb is at most 1/2 of limb length (PCP@0.5)  - Cons: Penalizes short limbs

- __PCK__: Percentage of Correct Key-Points (Correctness of joints)

  - 2D and 3D metric
  - Detected joint is considered correct if the distance between the predicted
  and the true joint is within a certain threshold (threshold varies)

  - `PCKh@0.5` if the threshold is 0.5 of head bone link
  - `PCK@0.2` if the threshold is 0.2 of torso diameter

- _PDJ_: Percentage of Detected Joints

  - Mostly a 2D metric
  - Detected joint is considered correct if the distance between the predicted
  and the true joint is within a certain threshold of torso diameter
  - `PDJ@0.2` == `PCK@0.2`

- __MPJE__: Mean Per Joint Position Error

  - Per Joint Position Error = Euclidean distance between ground truth and
  predicted joint
  - Average over all (typically 16) joints
  - Calculated after alignment of pelvis

  - __PA MPJE__: Procrustes _MPJE_: Calculated after 3D alignment using the
  _Procrustes_ method.

## 2022-02-13

- Anatomy-aware 3d pose estimation [`Arxiv`](https://arxiv.org/pdf/2002.10322v5.pdf)
- Max Plank Institute Saarbrucken [Saarbrucken](https://www.mpi-inf.mpg.de/departments/visual-computing-and-artificial-intelligence/publications)
- `Tex2Shape` [`Arxiv`](https://arxiv.org/pdf/1904.08645.pdf) [`github`](https://github.com/thmoa/tex2shape)
