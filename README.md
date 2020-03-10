# 3d Ground truth Traffic Sign Positions in KITTI

This respository contains the annotated Ground Truth (GT) traffic sign 3D positions annotated using the LiDAR and images from the [KITTI raw dataset](http://www.cvlibs.net/datasets/kitti/raw_data.php).

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

## Annotation Variance
Since each raw sign position is annotated from multiple coresponding pairs of image and lidar scans, it's annotated position may vary slightly. Then the raw sign position annotations are averaged as explained above. There mean difference in the final positions of each sign and raw annotations is given below:

| Var     | Mean  |
|---------|-------|
| x       | 0.035 |
| y       | 0.021 |
| z       | 0.034 |
| Overall | 0.061 |
