# 시각장애인을 위한 AI 기반 가이드 독

#### 프로젝트 기간: 2024.06.10 ~ 2024.07

2달동안 6명의 팀원들과 아래 프로젝트를 진행했습니다.

## 개요
> ### 추진배경
> 1. 정확성과 신뢰성.
↳   로봇견은 첨단 센서와 인공지능 기술을 통해 위험 장애물을 더 정확하게 식별하고, 최적의 경로를 계산하여 목적지에 빠르고 정확하게 도착할 수 있습니다.

> 2. 시각장애인의 증가.
>>   고령화와 다양한 질병으로 인해 시각장애인의 수가 증가하고 있으며, 이들을 지원할 기술 및 서비스의 필요성이 커지고 있습니다.

> ### 필요성
> 1. 한 자리에 머물지 않기 때문에 사각지대가 존재하는 CCTV나 장소가 국한된 출입구 검사기의 단점을 보완할 수 있다.
> 2. 실시간 위치정보와 촬영 데이터를 시각화하여 관리자가 쉽게 확인할 수 있다.
> 3. 인력을 로봇으로 대체함으로써 코로나 확산 가능성을 최소화하고 인력 낭비를 방지할 수 있다.
> 4. 360도 카메라와 인공지능을 활용하여 마스크를 착용하지 않은 사람을 효율적으로 찾아내고 음성경고 및 기록을 할 수 있다.

> ### 기대효과
> 1. 향상된 이동 안정성
> 2. 사회적 상호작용 증가
> 3. 사용자 친화적 조작
> 4. 기록 및 학습 기능

----------------------------------------------------------------------------------------------------

## 개발환경

+ 파이썬 
    Just the head. Here I freeze all backbone layers and train only randomly initialized layers (i.e. layers that do not use pre-trained weights from MS COCO). 
    To train only the head layer, we passed layer='heads' to the train() function.

+ 서버 환경 & 네트워크 & DB
        Flask
  
----------------------------------------------------------------------------------------------------

## 랜더링 도면 및 설계도
![image](https://github.com/user-attachments/assets/be92ea05-6bc1-43c8-aa12-77a2cc6b5169)

![image](https://github.com/user-attachments/assets/db97f52a-e6fb-4d92-b001-2492361cdab5)

----------------------------------------------------------------------------------------------------

## 전체 프로세스 알고리즘
![1](https://github.com/user-attachments/assets/8cef98f5-37e3-4b49-b72d-f098cc3910b4)

----------------------------------------------------------------------------------------------------
## 기능 별 설명
1. 대화기능
2. 객체인식
> + YOLOv8 - Custom Data
    시각 장애인 보행에 장애가 되는 객체 13클래스를 인식하는 모델. Custom Dataset으로 학습시킨 YOLOv8 모델을 이용하여 객체인식 수행 
3. 얼굴인식
