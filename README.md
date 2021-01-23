# 3d Ground truth Traffic Sign Positions in KITTI

This respository contains the annotated Ground Truth (GT) traffic sign 3D positions annotated using the LiDAR and images from the [KITTI raw dataset](http://www.cvlibs.net/datasets/kitti/raw_data.php).

## Usage
If you use this dataset, please cite as:
> H. Chawla, M. Jukola, T. Brouns, E. Arani, and B. Zonooz, "Crowdsourced 3D Mapping: A Combined Multi-View Geometry and Self-Supervised Learning Approach," 2020 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS),Las Vegas, USA, IEEE (in press), 2020.

## Distribution of Signs
A total of 73 signs are annotated across sequences 00 -> 10 (except 03 which is missing from KITTI raw) 

| Seq |       Date_Drive      | # Signs Annotated |
|:---:|:---------------------:|:-----------------:|
|  00 | 2011_10_03_drive_0027 |         15        |
|  01 | 2011_10_03_drive_0042 |         16        |
|  02 | 2011_10_03_drive_0034 |         12        |
|  04 | 2011_09_30_drive_0016 |         1         |
|  05 | 2011_09_30_drive_0018 |         4         |
|  06 | 2011_09_30_drive_0020 |         5         |
|  07 | 2011_09_30_drive_0027 |         2         |
|  08 | 2011_09_30_drive_0028 |         8         |
|  09 | 2011_09_30_drive_0033 |         7         |
|  10 | 2011_09_30_drive_0034 |         3         |

## Annotation Process

### Inputs 
* LiDAR scans
* Rectified and Synced Images
* GT path (metric)
* OXTS GPS
* Calibration (Camera, Camera-to-GPS/IMU, Camera-to-Velodyne)

### Method
Details Coming soon!

### Outputs
* Relative Positions of signs in each sequence in format
* Absolute Metric Positions of signs (wrt origin frame)
* Absolute GPS Positions of signs

All annotation txt files (per Sequence) are of the format:

| Image ID | x   | y   | z   | GT ID |
|----------|-----|-----|-----|-----------|
| ...      | ... | ... | ... | ...       |

### Annotation Variance
Since each raw sign position is annotated from multiple coresponding pairs of image and lidar scans, it's annotated position may vary slightly. Then the raw sign position annotations are averaged as explained above. There mean difference in the final positions of each sign and raw annotations is given below:

| Var  | x     | y     | z     | Overall |
|------|-------|-------|-------|---------|
| Mean | 0.035 | 0.021 | 0.034 | 0.061   |

## Usage
* Each folder contains txt files describing the raw (available), relative (available) and absolute (coming soon!) annotated traffic sign positions for the corresponding KITTI sequence. 
* The annotations can be loaded in `python` using `pandas`. 
  ```
  import pandas as pd
  pd.read_csv(ground_truth_position_file,sep=';')
  ```
## Additional
### Detection Annotations
GT annotations for the bounding box detections have also been provided.  
Per-image annotation files contain the (x,y) coordinates of the 4 corners of the bounding boxes (8 values), with each row representing a different traffic sign. 
