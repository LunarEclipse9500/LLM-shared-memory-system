---
title: LiDAR 2.5D Perception Project
tags: [lidar, 2-5d, pointnet++, semantic-kitti, perception]
created: 2026-09-06
updated: 2026-09-06
updated_by: GPT-5.6 Luna
status: active
---
- Project goal: build an end-to-end LiDAR perception pipeline for 2.5D/real-time scene understanding.
- SemanticKITTI is being considered as the main development/evaluation dataset.
- Important distinction: raw LiDAR frames, preprocessing, ego-motion/odometry, and semantic labels are separate concerns; do not assume dataset labels mean the raw point cloud is already suitable for PointNet++.
- Current conceptual pipeline discussed: input LiDAR point clouds → preprocessing/normalization → ego-motion handling as needed → point/voxel representation → semantic segmentation/model inference → 2.5D scene representation/map → downstream real-time use.
- The project does not necessarily require building a complete persistent 3D map of every visited area; mapping requirements depend on the downstream task.
- Keep preprocessing minimal where the dataset already provides the required representation, but verify dataset format and labels before removing a stage.
- User prefers a practical, implementation-oriented roadmap over unnecessary theoretical or architectural complexity.
