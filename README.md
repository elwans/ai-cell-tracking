# ai-cell-tracking
### Sayel Elwan, Rudy Harricks, Reira Ikenaga, Kannan Annamalai, Xiu Yit Foo, Viththegan Sresutharsan, Muhamed Tafech
An implementation of GNN and Trackastra cell tracking methods for 2025 Computer Science capstone.

## Usage:
Usage is incredibly simple; firstly create a `/PROJECT/` directory in your google drive and MOVE the `/data/` directory located here into /PROJECT.  The result should be similar to: `drive_root/PROJECT/data/<dataset_name>/`. Then run the scripts in the following order: `gnn`, `trackastra` then `visualisation`. 
 
## 🚀 Project Overview

The goal of this project is to build and compare two advanced approaches for cell tracking in live-cell microscopy time-lapse sequences. Specifically, we implement:

A Graph Neural Network (GNN)-based tracking approach inspired by “Graph Neural Network for Cell Tracking in Microscopy Videos” by Ben-Haim & Riklin Raviv (ECCV 2022) 

The TrackASTRA method: a transformer-based tracking approach described in “TrackASTRA: Transformer-based cell tracking for live-cell microscopy” (Gallusser & Weigert, 2024) 

Our implementation allows benchmarking and visualisation of how each method performs on sample CTC microscopy datasets, to provide insights on strengths and weaknesses of GNN vs transformer strategies in the domain of cell tracking.
## GNN Notebook
[![GNN](https://colab.research.google.com/assets/colab-badge.svg)]([https://colab.research.google.com/github/talbenha/cell-tracker-gnn/blob/main/notebooks/training_example.ipynb](https://drive.google.com/file/d/1X0BeWqo68DpoPh6-pP532FjTMQta_Gtr/view?usp=sharing))
## Trackastra Notebook
[![Trackastra](https://colab.research.google.com/assets/colab-badge.svg)]([[https://colab.research.google.com/github/talbenha/cell-tracker-gnn/blob/main/notebooks/training_example.ipynb](https://drive.google.com/file/d/1X0BeWqo68DpoPh6-pP532FjTMQta_Gtr/view?usp=sharing)](https://colab.research.google.com/drive/115Yz6dYFUGT6xxAVrodz3qov7FOoe-vX?usp=sharing))

## What we implemented:
- Visualisation suite to make 2d and 3d videos showcasing tracking
- Refactored GNN to fix outdated dependency+environment errors in the orignal repo
- Introduced a colab script for trackastra that allows training from scratch + iterative training
- Corrected outdated/unsupported functions in Trackastra script.
- Rigid I/O structure outlined below to avoid confusion and enable uniformity

## I/O TREE:
``` 
PROJECT/
├── (CODE)  jupyter_notebooks
│   ├── napari_visualisation_setup.ipynb
|    └──  .  .  .
├── (INPUT) data/
│   └── <dataset_name>
├── (OUTPUT) gnn_out/
│   ├── features/
│   ├── basic_features
│   ├── advanced_features
│   ├── inference_results/
│   ├── <dataset_name>/
│   │   ├── [01/02]_CSV
│   │   ├── [01/02]_RES_inference
│   │   └── RES_inference
│   ├── trained_models/
│   │   ├── metric_models
│   │   └── pytorch_models
│   └── results/
│       └── <dataset_name>/
│           └── TR_RES
├── (INPUT) trackastra_trained_models/
│   └── trackastraTrained<dataset_name>/
│       └── model.pt
├── (OUTPUT)trackastra_out/
│   ├── trained_models/
│   │   └── trackastraTrained_<dataset_name>.zip
│   └── trackastra_inference/
│       └── tracking_results<dataset_name>/
|       └──  .  .  .
└── (OUTPUT) visualisation/
    └── <dataset_name>/
        ├── 3D_cell_tracking_spinning.mp4
        ├── 3D_cell_tracking.mp4
        ├── 2D_cell_tracking.mov
        └──  2D_cell_tracking_frames/
            └── frame_001.png
            └── frame_002.png
            └──  .  .  .
```
