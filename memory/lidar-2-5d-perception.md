---
title: LiDAR 2.5D Perception Project
tags: [lidar, 2-5d, pointnet++, spvcnn, semantic-kitti, perception, mapping]
created: 2026-09-06
updated: 2026-09-06
updated_by: GPT-5.6 Luna
status: active
---
- Project goal: build an end-to-end LiDAR perception pipeline for 2.5D/real-time scene understanding.
- SemanticKITTI is the main candidate dataset for development/evaluation; verify its exact raw/pose/label format before simplifying preprocessing.
- Semantic labels are annotations, not an indication that the input point cloud is already preprocessed for a specific network.
- Current development flow: LiDAR frames → required preprocessing/normalization → ego-motion/pose handling if temporal alignment is needed → point/voxel representation → semantic segmentation → 2.5D scene representation/map → downstream real-time use.
- Preprocessing and ego-motion are not automatically required at the very beginning for every experiment; they are task/data dependent. A single-frame semantic-segmentation baseline can start directly from correctly decoded point clouds.
- PointNet++ is a point-based model; SPVCNN is a sparse point-voxel convolutional architecture. Model input requirements should determine the representation rather than forcing the dataset through unnecessary stages.
- PyTorch should be the core ML/tensor computation stack. NumPy can handle lightweight data manipulation. Open3D is optional and is best treated as a geometry/visualization utility rather than a required ML dependency.
- PyTorch can replace custom Open3D-dependent processing for many tensor operations, filtering, transforms, voxelization, and model preparation, but Open3D remains useful for point-cloud visualization and ready-made geometry/registration utilities.
- The system does not necessarily need a persistent 3D map of every visited area. Mapping scope should follow the downstream requirement; 2.5D/BEV-style representations may be sufficient.
- Real-time processing should be designed around frame-wise inference, efficient spatial representation, and only the temporal state actually needed by the application.
- [2026-09-06] Current priority is to minimize unnecessary pipeline complexity while keeping the architecture extensible from a baseline semantic-segmentation prototype toward real-time 2.5D mapping.
