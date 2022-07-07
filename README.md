# LAMO : LAndscape or Me Only with Mask2former and LaMa
### 당신의 더욱 완벽한 추억을 위해
by Taehyeong Kim & Minji Kang
Mask2Former(MMDetection) : https://github.com/open-mmlab/mmdetection.git  
Lama : https://github.com/saic-mdal/lama
<center><img src="/image/demo.gif" width="600" height="600"></center>  

#### 이미지 내 불필요한 인물 객체를 제거하여 당신이 원하는 더욱 완벽한 사진을 생성할 수 있습니다.

1. [MMDetection](https://github.com/open-mmlab/mmdetection) 기반의 [Mask2Former](https://github.com/open-mmlab/mmdetection/tree/master/configs/mask2former)를 기반으로 인물을 탐지하여 mask를 생성하고  
2. [LaMa](https://github.com/saic-mdal/lama) 를 기반으로 mask 영역의 이미지를 새롭게 생성하였습니다.
