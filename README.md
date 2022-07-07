# LAMO : LAndscape or Me Only with Mask2former and LaMa
## 소개
### 당신의 더욱 완벽한 추억을 위해
by Taehyeong Kim & Minji Kang [@minjikang-cod](https://github.com/minjikang-cod)   
    
<div align="center">
<p align"center"><img src="/image/demo.gif" width="600" height="600"></p>

#### 이미지 내 불필요한 인물 객체를 제거하여 당신이 원하는 더욱 완벽한 사진을 생성할 수 있습니다.
</div>





<div align="center">

[[More Details]](https://wry-phalange-187.notion.site/LAMO-218edf4f99fd4574b176a2c4371b345f)  
더욱 자세한 프로젝트 과정을 노션 페이지에서 확인해보세요!   
  
[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/13LhTvB7RF2e5_JNEcdVgZRLmQLt7eBQJ?usp=sharing)   
누구든 코랩을 통해 데모를 체험해보실 수 있습니다 !
</div>

Mask2Former(MMDetection) : https://github.com/open-mmlab/mmdetection.git  
Lama : https://github.com/saic-mdal/lama  

## 방법
1. Segmentation  
    [MMDetection](https://github.com/open-mmlab/mmdetection)을 통해 [Mask2Former](https://github.com/open-mmlab/mmdetection/tree/master/configs/mask2former)로 인물을 Detection & Segmentation하여 mask를 생성합니다. 
2. Inpainting  
    [LaMa](https://github.com/saic-mdal/lama) 로 masking을 통해 지워진 영역의 이미지를 새롭게 복원하였습니다.
## 의의
1. 기존 어플리케이션([Samsung AI Eraser](https://www.samsung.com/africa_en/support/mobile-devices/how-to-remove-unwanted-objects-from-photos-on-your-galaxy-phone/), [Hama](https://www.hama.app/ko))과 다르게, instance segmentation 및 object detection을 통해 사용자의 별다른 영역 지정 없이도 매우 정확한 mask 지정이 가능합니다.
2. segmentation mask에 대해 팽창 연산을 수행하여 주변 배경까지 포함시키는 mask를 생성해 더욱 자연스러운 inpainting이 가능합니다.
3. 사용자가 지우고 싶은 객체를 선택하도록 입력을 받아 활용성을 증가시켰습니다.  

## 한계
1. 지울 인물을 선택할 때, 후보군이 segmentation의 output에 의존하기 때문에 segmentation 단계에서 탐지하지 못하거나 threshold에 의해 filtering 된 객체는 지울 수 없습니다.
2. 환경 구축 단계에서 불필요한 파일까지 모두 다운로드하기 때문에, 다소 긴 시간(10~15분)이 소요됩니다.  

## 추후 발전 방향
1. 사람 이외의 객체도 선택하여 지울 수 있도록 모델을 확장합니다.
2. 객체의 상태(사람만 있는지 혹은 다른 사물을 포함하는지)에 따라 Segmentation Mask를 적용할 지 Bounding Box Mask를 적용할 지 결정하는 알고리즘을 작성하여 모델에 추가합니다.
3. 탐지된 객체들의 평균 신뢰도 값을 threshold 설정에 이용하여 더욱 정확하고 많은 객체들이 segment 될 수 있도록 알고리즘을 수정합니다. 
