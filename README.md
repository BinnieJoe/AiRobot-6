# 시각장애인을 위한 AI 기반 가이드 독

#### 프로젝트 기간: 2024.06.10 ~ 2024.07

2달동안 6명의 팀원들과 프로젝트를 진행했습니다.

## 개요
> ### 추진배경
> 1. 정확성과 신뢰성
>>   로봇견은 첨단 센서와 인공지능 기술을 통해 위험 장애물을 더 정확하게 식별하고, 최적의 경로를 계산하여 목적지에 빠르고 정확하게 도착할 수 있습니다.

> 2. 시각장애인의 증가
>>   고령화와 다양한 질병으로 인해 시각장애인의 수가 증가하고 있으며, 이들을 지원할 기술 및 서비스의 필요성이 커지고 있습니다.

> ### 필요성
> 1. 로봇견은 피로나 건강 문제 없이 24시간 내내 시각장애인을 지원할 수 있습니다.
> 2. 개인 맞춤형 서비스 제공이 가능하여 각 시각장애인의 필요에 맞는 최적의 지원을 제공합니다.
> 3. 안내견보다 낮은 유지비용과 높은 접근성으로 경제적 부담을 줄일 수 있습니다.
> 4. 시각장애인의 독립성과 자율성을 증대시켜 더 포용적인 사회를 만드는 데 기여합니다.

> ### 기대효과
> 1. 향상된 이동 안정성
> 2. 사회적 상호작용 증가
> 3. 사용자 친화적 조작
> 4. 기록 및 학습 기능

----------------------------------------------------------------------------------------------------

## 개발환경

+ 파이썬

        face-recognition==1.3.0
        face_recognition_models==0.3.0
        gTTS==2.5.1
        matplotlib==3.9.0
        numpy==1.26.4
        openai==0.28.0
        opencv-python==4.9.0.80
        pandas==2.2.2
        PyAudio==0.2.14
        pyserial==3.5
        pyttsx3==2.90
        scikit-learn==1.5.1
        SpeechRecognition==3.10.4
        tensorflow==2.16.2
        torch==2.0.1+cu117
        torchvision==0.15.2+cu117
        tqdm==4.66.4
        ultralytics==8.2.58

+ 웹 & 앱 

        Flask==3.0.3
  
----------------------------------------------------------------------------------------------------

## 랜더링 도면 및 설계도
![image](https://github.com/user-attachments/assets/be92ea05-6bc1-43c8-aa12-77a2cc6b5169)

![image](https://github.com/user-attachments/assets/db97f52a-e6fb-4d92-b001-2492361cdab5)

----------------------------------------------------------------------------------------------------

## 전체 프로세스 알고리즘
![1](https://github.com/user-attachments/assets/8cef98f5-37e3-4b49-b72d-f098cc3910b4)

----------------------------------------------------------------------------------------------------

## 기능 설명
1. 대화기능
> + Chat GPT API(3.5 turbo) + GTTS
>
시작 멘트 감지하여 대화시작. 사용자가 전달한 문장을 API로 응답. 응답한 텍스트를 음성으로 출력. 종료 멘트 감지시 대화 종료.
>
2. 객체인식
> + YOLOv8 - Custom Data
>   
시각 장애인 보행에 장애가 되는 객체 13클래스를 인식하는 모델. 로보플로우에서 이미지 라벨링 진행 후 Custom Dataset 제작. Custom Dataset으로 학습시킨 YOLOv8 모델을 이용하여 객체인식 수행.
객체인식의 결과를 gtts로 음성출력.
![train_batch0](https://github.com/user-attachments/assets/5fa5ebbe-85dd-4ff1-8dbe-235205d0b6a3)

>
3. 얼굴인식
> + OpenCV Face Detection 모델 + face embadding
> 
DNN모델을 이용해서 얼굴인식. 특정 멘트 입력 후 촬영하여 데이터파일에 이미지를 저장. 저장된 얼굴데이터의 임베딩 생성 시작 후 같은 얼굴 일치 여부 확인.

----------------------------------------------------------------------------------------------------

## 웹 & 앱
 + 카메라를 호출하여 실시간 스트리밍과 녹화를 진행합니다. 스트리밍 영상은 2분 간격으로 녹화.
 + 녹화된 영상은 "Saved Videos"에 저장됩니다. 저장된 영상은 "Video Play Back" 기능을 통해 재생할 수 있습니다.
----------------------------------------------------------------------------------------------------

## 향후 발전가능성 
 + GPS모듈을 추가하여 사용자의 위치를 보호자에게 전달
 + URL 링크 대신 서버를 구축하고 앱을 배포하여 링크 기능을 대체
 + 화면을 추가하여 App, Web을 제외한 PC 확인 기능
 + 지인과의 대화를 텍스트로 변환하여 정보 파일에 저장

----------------------------------------------------------------------------------------------------
