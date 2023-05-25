### object_detection
## Detecting number of people and cars

**YOLO(You Only Look Once) : 머신러닝에서 한 사진 안에 어떤 물체들이 등장하는지에 대한 것을 판별해주는 Task**

1. 비디오 영상 캡쳐(video_capture)
     - 35분짜리 영상 10초 단위로 캡쳐해서 250장 캡쳐 (실질적으로 약 25분 250장 캡쳐)
     - 1차: 150장
     - 2차: 200장
     

2. 레이블링 (labelImg)
      - 보행자(p), 차(car) labeling
      - custom_data 생성(.jpg, .txt, class.txt)


3. yolov4(yolov4.conv.137) 다운받아 yolo모델로 다크넷 사용해서 train_data 학습
     -  학습될 가중치를 저장할 backup 이라는 폴더 미리 생성
     -  yolov4.cfg -> yolov4_custom.cfg 
     - cfg, weight 파일 생성

5. 학습 결과 중간 확인
     - train_data 일부를  이미지 파일(.jpg)형태로 생성한 cfg, weight 로 사람, 보행자 detect 
     - 
5. 학습 결과 중간 확인
     - 학습 결과
          아래의 2개의 파일을 다운로드 받으면 됩니다.
           1. 가중치
                /content/drive/MyDrive/yolo_custom_model_Training3/backup/yolov4_custom_last.weights
           2. cfg 파일
                /content/drive/MyDrive/yolo_custom_model_Training3/darknet/cfg/yolov4_custom.cfg

     - 이미지 파일로 우선 cfg, weight 사용해서 detect 잘되는지 확인
          - train_data 일부를  이미지 파일(.jpg)형태로 생성한 cfg, weight 로 사람, 보행자 detect 
     
  
  
6. 보행자, 자동차 수 측정
     - softmax 함수로 자동차와 사람 수 count  vs. 시그모이드 함수로 사람 수만 count
