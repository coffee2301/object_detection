### object_detection
# YOLO(You Only Look Once) : 머신러닝에서 한 사진 안에 어떤 물체들이 등장하는지에 대한 것을 판별해주는 Task

# Detecting number of people and cars

1. 비디오 영상 캡쳐
  - 35분짜리 영상 10초 단위로 캡쳐해서 210장 캡쳐




2. 
  - yolov4 or yolov 3 활용해 훈련
  - cfg, weights 
  - softmax 함수로 자동차와 사람 수 count  vs. 시그모이드 함수로 사람 수만 count
  
  
  
3. 사람, 자동차 수 측정
