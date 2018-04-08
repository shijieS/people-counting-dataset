# People Counting Dataset (PCDS)
The purpose of people counting dataset  is to count the number of people passing through a specified scene. In this dataset, we published a set of videos recorded in the entrance of bus scene by Kinect V1 camera. Each depth video has its corresponding RGB video. And each pair of video has a label to indicate the number of pedestrians passing through the scene.

- This dataset contains 5,464 videos depth video and its corresponding color video. As a result, there total up to 10,928 videos in the PCDS
- These videos is recorded in the entrance of buses.
- The camera is mounted at the top of the entrance of buses.
- Total up to about 10,908 videos passing through the scene

## Purpose
The purpose of this dataset is to provide the real-scene videos for people counting (mainly by depth video).

## ROI counting & LOI counting
People counting can be splited into two class: LOI (Line of Interest) counting and ROI (Region of Interest) counting.
> LOI counting is to count people passing through a area

> ROI counting is to count people in a area

This dataset mainly focuses on the LOI counting

# Dataset
The dataset is available at [BaiYun](http://pan.baidu.com/s/1eR3fmdO).

## Classfication
These videos are categoried by 4 sub-categories: N+C+, N+C-, N-C+, N-C-. See the following table.

|          |  N+C+  |  N+C-  | N-C+ | N-C- |
|:--------:|:------:|:------:|:----:|:----:|
| sunlight | strong | strong | weak | weak |
| crowed   |   yes  |   no   |  yes |  no  |

There are total up to 5,464 videos in this dataset, the detail number of each category is shown as follows.

|          | N+C+ | N+C- |  N-C+ | N-C- |
|:--------:|:----:|:----:|:-----:|:----:|
| entering |  937 |  616 |  5427 | 2704 |
| exiting  | 1149 |  668 |  6647 | 2760 |
| total    | 2086 | 1284 | 12074 | 5464 |

## Dataset Structure
The structure of these videos are shown in the following figure
![](./image/structure_of_videos.png)

Each scene is named by the the following format:
BUS_DATETIME_\[front, back\]

where, BUS is the bus number, DATETIME is the reocred date, \[front, back\] indicates wheter the video is recorded in front entrance of the bus or not. For example the scene name 25_20160411_front means we record the video on the front of the door of 25 bus at 04, Nov. 2016.

The following figure shows part of the structure of PCDS,

![](./image/demo_of_structure.png)

## Label Format
There is a label file in each scene directory. The label file is named as "label.txt", which contains camera extrinsic parameter and the number of pedestrian passing through the entrance of the bus for each video.
The following figure is the demo of label file.
![](./image/demo_of_label_file.png)

The first 4 lines is the camera extrinsic parameter, which is 4x3 matrix. The followed lines are the number of pedestrian passing through the scene which is formated by VideoName,  EnteringNumber, ExistingNumber, VideoType.  There 4 video types represented by the index: 0: N-C-, 1: N-C+, 2: N+C-, 3: N+C+.

---
- The camera mount overhead and has a angle of pitch.
- This dataset contains 5,464 videos
- Total up to about 20,908 people passing through the scene
- These videos are categoried by normal and nosiy. Besides, each category are divided into 2 classes: crowd and uncrowd

---


# Recording Condition
These videos is recorded by Kinect V1, the configuration of camera is illustrated in the following.
![](./image/application_scene.jpg)
The camera in mounted in the top of the entrance and have a pitch angle. Pedestrian passing through the entrance (entering or exiting). The task is to count these pedestrian (entering or existing)

# Notice
We only focus on the deth video and the color video is an accessary. We cannot guarantee the synchronization of A and B.

## License
The datasets provided on this page are published under the [Creative Commons Attribution-NonCommercial-ShareAlike 3.0 License](http://creativecommons.org/licenses/by-nc-sa/3.0/) . This means that you must attribute the work in the manner specified by the authors, you may not use this work for commercial purposes and if you alter, transform, or build upon this work, you may distribute the resulting work only under the same license. If you are interested in commercial usage you can contact us for further options.
