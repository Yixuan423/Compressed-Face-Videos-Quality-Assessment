# Compressed-Face-Videos-Quality-Assessment
<img src = "https://user-images.githubusercontent.com/45612850/199892894-0cc7a951-e84c-47bc-880a-1d87a5524ed1.png" width ="1000px">

#### SOURCE VIDEOS

The source face videos were obtained from two copyright-free website Pexel(https://www.pexels.com/videos/) and Mixkit(https://mixkit.co/).
The source videos are permitted to use, modify and redistribute freely without attribution.
The raw videos were downloaded in MP4 format, then cropped and trimmed into demanding layout.
All the source videos are in the resolution of 512 x 512, length 5 s and frame-rate of 25 fps
The *.mp4 videos were converted into uncompressed *.yuv files using the ffmpeg (Command:ffmpeg -i %i -s 512x512 -pix_fmt yuv420p *.yuv ).

#### COMPRESSED VIDEOS

Compressed videos in this database are provided as *.yuv files.

All the video files have planar YUV 4:2:0 format and contain no headers.
The resolution for all videos is 512 x 512. The 8-bit Y component of the first frame, followed the 8-bit U component 
of the first frame, followed by the 8-bit V component of the first frame. 
Frames are concatenated to form sequence files.


#### FILENAMING CONVENTION

The file naming convention of this database has the pattern of "num_codec_qp.yuv" or "num.yuv".

"num" is an interger that denotes the reference video sequence that was used to create the compressed video.
There are totally 135 reference videos in this database, so the patterns of "num" is from 1 to 135.

"codec" means the video compression codec used for generating compressed video sequence. The patterns used for them are as follows:
	"vvc"  - Versatile Video Coding (VVC)
	"dvc"  - DVC: An End-to-end Deep Video Compression Framework,
	"rlvc" - Learning for Video Compression with Recurrent Auto-Encoder and Recurrent Probability Model,
	"fomm" - First Order Motion Model for Image Animation.
	"cfte" - Beyond Keypoint Coding: Temporal Evolution Inference with Compact Feature Representation for Face Video Compression

"qp" is qp value that denotes the quantization parameter.

For instance, for the "100.yuv" sequence:

1. "100.yuv" is a reference video.
2. "100_dvc_22.yuv" is a compressed video obtained by compressing the reference video with the codec dvc at qp22.
3. "100_rlvc_1024.yuv" is a compressed video obtained with the codec rlvc at qp27.

Specially, in the fomm and cfte folder:
"100_fomm_22.yuv" denotes a compressed video obtained with fomm model with 10 key points, and the first frame is compressed by VVC in the QP level of 22.

#### DATASET INFORMATION

In total, 3240 distorted video sequences derivated from 135 reference videos are included in our dataset. 
The download link of CFVQA dataset is: https://portland-my.sharepoint.com/:f:/g/personal/yixli5-c_my_cityu_edu_hk/EqdHThcDoGxBiAFikI0areABIt6R3FXdGRTwUwzfHmDszQ?e=clHoK0


Please cite the paper below if you include any part of this database in your work:
[
]

#### Video Codec Information

