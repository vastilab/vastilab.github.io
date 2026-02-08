---
title: Congratulation to Peike, Yunqiu on their winning in three tracks in LIP, CVPR 2019.
categories: blog
---

Among the 75 participating teams in the world, our team is proud to announce that we have won the [Look Into Person (LIP) Challenge](https://vuhcs.github.io/) for three tasks, including the single-person human parsing, the multi-person human parsing and multi-person video parsing tracks.
LIP challenge has attracted many world-famous AI companies and universities including the ByteDance AI Lab, JD AI Lab, Samsung AI Lab UCLA, Cambridge and so on.


LIP Challenge is co-organized with workshop on augmented human: human-centric understanding. The workshop is co-located with [CVPR 2019](http://cvpr2019.thecvf.com/), the most important annual computer vision conference, to be held in Long Beach, California 16-23 June.
The goal of this workshop is to allow researchers from the fields of human-centric understanding and 2D/3D synthesis to present their progress, communication and co-develop novel ideas that potentially shape the future of this area and further advance the performance and applicability of correspondingly built systems in real-world conditions.

The results can be found in [https://vuhcs.github.io/](https://vuhcs.github.io/).

![alt text](/images/post/human_parsing1.png "Logo Title Text 1")

![alt text](/images/post/human_parsing2.png "Logo Title Text 1")


The third large-scale Look Into Person (LIP) challenges which include five competition tasks: the single-person human parsing, the single-person pose estimation, the multi-person human parsing, multi-person video parsing, multi-person pose estimation benchmark, and clothes virtual try-on benchmark. This third LIP challenge mainly extends the second LIP challenge in CVPR 2017 and CVPR 2018 by additionally covering a video human parsing challenge and the 2D/3D clothes virtual try-on benchmark. For the single-person human parsing and pose estimation, 50,000 images with elaborated pixel-wise annotations with comprehensive 19 semantic human part labels and 2D human poses with 16 dense key points are provided. For the multi-person human parsing competition task, another 50000 images of crowded scenes with 19 semantic human part labels are provided. For video-based human parsing, 3000 video shots with 1-2 minutes will be densely annotated with 19 semantic human part labels. For multi-person pose estimation, the dataset contains 25,828 images with 2D human poses with 16 dense key points and head & instance bounding boxes. The new image-based clothes try-on benchmark targets at fitting new in-shop clothes into a person image and generate one try-on video to show different clothes viewpoints on the person. The images collected from the real-world scenarios contain humans appearing with challenging poses and views, heavily occlusions, various appearances and low-resolutions. This challenge was released before January, 2019 and the challenge is conjunction with CVPR 2019, Long Beach, CA.


[Single Person Human Parsing Task](http://sysu-hcp.net/lip/parsingchallenge.php)

![alt text](/images/post/human_parsing3.png "Logo Title Text 1")

[Multi-Person Human Parsing Task](http://sysu-hcp.net/lip/mparsing_challenge.php)

![alt text](/images/post/human_parsing4.png "Logo Title Text 1")

[Video Multi-Person Human Parsing Task](http://sysu-hcp.net/lip/video_parsing.php)

![alt text](/images/post/human_parsing5.png "Logo Title Text 1")


Human Parsing is the sub-task of semantic segmentation which need to assign a semantic label (like leg or arm) to each pixel in a human image. We proposed a novel SPHP(Single Person Human Parsing) network, which consists of three key modules to learn for parsing in an end-to-end manner including high resolution embedding module, global context embedding module and edge perceiving module.

### Framework of our winning solution

![alt text](/images/post/human_parsing6.png "Logo Title Text 1")


#### Some Qualitative Results of Our Single Person Human Parsing Solution

![alt text](/images/post/human_parsing7.png "Logo Title Text 1")


#### Some Qualitative Results of Our Multi-Person Human Parsing Solution

![alt text](/images/post/human_parsing8.png "Logo Title Text 1")

#### Some Qualitative Results of Our Video Multi-Person Human Parsing Solution

![alt text](/images/post/human_parsing9.png "Logo Title Text 1")

The detailed report and code will be released later.
