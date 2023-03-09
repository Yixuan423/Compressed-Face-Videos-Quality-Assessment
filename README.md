# Compressed-Face-Videos-Quality-Assessment


Database and VQA codes for the following paper:

> Yixuan Li. et al. "Perceptual Quality Assessment of Face Video Compression: A Benchmark and An Effective Method", 2023.

<img src = "https://github.com/Yixuan423/Compressed-Face-Videos-Quality-Assessment/blob/main/figures/dataset-ref2.jpg" width ="1000px">

## HIGHLIGHTS
- The first large-scale subjective video quality assessment for compressed face videos.
  Spatial and temporal distortions, along with traditional and generative distortions for face videos are included and studied.
- The first full-reference face video quality assessment method correlating well with human perceptual quality.
  Free of training or fine-tuning.


## VQA DATASET INFORMATION

In total, 3240 distorted face video sequences derivated from 135 reference face videos are included in our dataset. 
The download link of CFVQA dataset is

Onedrive:  https://portland-my.sharepoint.com/:f:/g/personal/yixli5-c_my_cityu_edu_hk/EqdHThcDoGxBiAFikI0areAB_0bDyfw8_Q0lZpPD9dDJFQ?e=2fJFaN

Please contact YixuanLI (yixuanli423@gmail.com) for download password, questions or comments.

Please cite the paper if you use any part of the videos or data supplied in this project page.


### SOURCE VIDEOS

The source face videos were obtained from two copyright-free website Pexel(https://www.pexels.com/videos/) and Mixkit(https://mixkit.co/), where the videos are permitted to use, modify and redistribute freely without attribution.

### COMPRESSED VIDEOS

Compressed videos in this database are provided as *.yuv files.

All the video files have planar YUV 4:2:0 format and contain no headers.
The resolution for all videos is 512 x 512. The 8-bit Y component of the first frame, followed by the 8-bit U and 8-bit V component of the first frame. Frames are concatenated to form sequence files.

Here are some examplar compressed video clips contained in the CFVQA dataset.
#### Videos compressed by different compression methods

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223769902-07c00ec8-601e-419f-bffc-786b05e06f44.mp4)](https://user-images.githubusercontent.com/45612850/223769902-07c00ec8-601e-419f-bffc-786b05e06f44.mp4)

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223770877-27417c42-de47-4a31-9399-62bc63bf16df.mp4)](https://user-images.githubusercontent.com/45612850/223770877-27417c42-de47-4a31-9399-62bc63bf16df.mp4)

#### Videos compressed by the same compression methods in different compression levels

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223766342-11903afe-df21-4417-b9da-ad0f075205f2.mp4)](https://user-images.githubusercontent.com/45612850/223766342-11903afe-df21-4417-b9da-ad0f075205f2.mp4)

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223772262-6a19a075-f621-4ae5-944d-af0828e76641.mp4)](https://user-images.githubusercontent.com/45612850/223772262-6a19a075-f621-4ae5-944d-af0828e76641.mp4)

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223772339-a1752517-c563-4d66-bf51-ca600d7a9b0f.mp4)](https://user-images.githubusercontent.com/45612850/223772339-a1752517-c563-4d66-bf51-ca600d7a9b0f.mp4)

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223772474-9ef71c66-22ad-4a35-9474-ecde5f7b18bc.mp4)](https://user-images.githubusercontent.com/45612850/223772474-9ef71c66-22ad-4a35-9474-ecde5f7b18bc.mp4)

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223772526-ff2ee632-8849-4fb7-a909-b0a3d00620e5.mp4)](https://user-images.githubusercontent.com/45612850/223772526-ff2ee632-8849-4fb7-a909-b0a3d00620e5.mp4)

[![IMAGE ALT TEXT](https://user-images.githubusercontent.com/45612850/223772585-9a3aaeef-5401-4d6e-a7da-0f09094ce01b.mp4)](https://user-images.githubusercontent.com/45612850/223772585-9a3aaeef-5401-4d6e-a7da-0f09094ce01b.mp4)


### FILENAMING CONVENTION

The file naming convention of this database has the pattern of "num_codec_qp.yuv" or "num.yuv".

1. "num" is an interger that denotes the reference video sequence that was used to create the compressed video.
   There are totally 135 reference videos in this database, so the patterns of "num" is from 1 to 135.

- ​		"100.yuv" - The 100th reference face video clip in this dataset. 

2. "codec" means the video compression codec used for generating compressed video sequence. The patterns used for them are as follows:

- ​	"vvc"  - Versatile Video Coding (VVC)	
- ​	"rl"  - reduced resolusion coding
- ​	"dvc"  - DVC: An End-to-end Deep Video Compression Framework
- ​	"rlvc" - Learning for Video Compression with Recurrent Auto-Encoder and Recurrent Probability Model
- ​	"fomm" - First Order Motion Model for Image Animation
- ​	"cfte" - Beyond Keypoint Coding: Temporal Evolution Inference with Compact Feature Representation for Face Video Compression

3. "qp" is qp value that denotes the quantization parameter.

​	For instance, for the "100.yuv" sequence:

- "100.yuv" is a reference video.
- "100_dvc_22.yuv" is a compressed video obtained by compressing the reference video with the codec dvc at qp22.
- "100_rlvc_27.yuv" is a compressed video obtained with the codec rlvc with lambda=1024.

Specially, in the fomm and cfte folder:
"100_fomm_22.yuv" denotes a compressed video obtained with fomm model with 10 key points, and the first frame is compressed by VVC in the QP level of 22. The same convention is for CFTE-compressed videos.

### VIDEO COMPRESSION CODEC IMPLEMENTATIONS

The implementation details of the employed video compression codecs can be found in the supplementary file. The adopted implementations are listed as followed.

VVC : https://vcgit.hhi.fraunhofer.de/jvet/VVCSoftware_VTM/-/tree/VTM-11.0

DVC: https://github.com/RenYang-home/OpenDVC

RLVC: https://github.com/RenYang-home/RLVC

FOMM: https://github.com/AliaksandrSiarohin/first-order-model

CFTE: https://github.com/alibaba-edu/temporal-evolution-inference-with-compact-feature-representation-for-talking-face-video-compression



## FaceVQA FRAMEWORK

<img src = "https://github.com/Yixuan423/Compressed-Face-Videos-Quality-Assessment/blob/main/figures/framework.jpg" width ="850px">

### Dependencies

- Python==3.7
- Pytorch==1.8.0
- numpy
- matplotlib
- scipy
- Pillow

### Network and pretrained models

- Resnet for face recognition: frmodels.py from https://github.com/Tencent/TFace/tree/quality

  The pretrained parameters: /weights/IR_50_MS1M.pth

- Multi-level spatial feature fusion parameters: /weights/DISTS.pt

  Please download via https://portland-my.sharepoint.com/:u:/g/personal/yixli5-c_my_cityu_edu_hk/Ed6ZYYUpL49LurU8ac7mQjEBxB_2skaRmF5beCM1gAwAYg?e=Orbmy7 and put it in the weights folder.

### Usage

- Unzip the Reference and VVC folders.
```
python faceva.py --ref_path videos/Reference/1.yuv --comp_path videos/VVC/1_vvc_32.yuv
```

"facevqa.py" pending update.

## COPYRIGHT NOTICE

Copyright (c) 2023 The City University of Hong Kong

All rights reserved.Permission is hereby granted, without written agreement and without license or royalty fees, to use, copy, and  distribute this database (the images, the results, and the source files) and its documentation for non-commercial research and educational  purposes only, provided that the copyright notice in its entirety appear in all copies of this database, and the original source of this  database, all authors at The City University of Hong Kong, is acknowledged in any publication that reports research using this database.

IN NO EVENT SHALL THE CITY UNIVERSITY OF HONG KONG BE LIABLE  TO ANY PARTY FOR DIRECT, INDIRECT, SPECIAL, INCIDENTAL, OR CONSEQUENTIAL LOSS OR DAMAGES ARISING OUT OF OR IN CONNECTION WITH THE USE OF OR THE  INABILITY TO USE THIS DATABASE, ITS DOCUMENTATION AND INFORMATION, EVEN  IF THE CITY UNIVERSITY OF HONG KONG HAS BEEN ADVISED OF THE  POSSIBILITY OF SUCH LOSS OR DAMAGE.

THE CITY UNIVERSITY OF HONG KONG SPECIFICALLY DISCLAIMS ANY  EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE  IMPLIED WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, ACCURACY OR COMPLETENESS AND NON INFRINGEMENT OF INTELLECTUAL PROPERTY  RIGHTS OF ANY PARTY. THE DATABASE PROVIDED HEREUNDER IS ON AN "AS IS"  BASIS, AND THE CITY UNIVERSITY OF HONG KONG HAS NO OBLIGATION TO  PROVIDE MAINTENANCE, SUPPORT, UPDATES, ENHANCEMENTS, OR MODIFICATIONS.
