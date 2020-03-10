# 3d Ground truth Traffic Sign Positions in KITTI
Coming soon!

This respository contains the annotated Ground Truth (GT) traffic sign 3D positions annotated using the LiDAR and images from the [KITTI raw dataset](http://www.cvlibs.net/datasets/kitti/raw_data.php).

## Distribution of Signs
A total of 73 signs are annotated across sequences 00 -> 10 (except 03 which is missing from KITTI raw) 

| Seq |       Date_Drive      | # Signs Annotated |
|:---:|:---------------------:|:-----------------:|
|  00 | 2011_10_03_drive_0027 |         16        |
|  01 | 2011_10_03_drive_0042 |         5         |
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

### Outputs
* Relative Positions of signs in each sequence in format
* Absolute Metric Positions of signs (wrt origin frame)
* Absolute GPS Positions of signs
All annotation txt files are of the format:
| Image ID | x | y | z  | Seq GT ID |
|----------|---|---|----|-----------|
