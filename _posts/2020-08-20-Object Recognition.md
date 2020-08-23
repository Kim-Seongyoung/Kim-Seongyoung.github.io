---
title:  "Object Recognition"
excerpt: "프로젝트"
toc: true
author_profile: false
toc_sticky: true
categories:
- project
tags:
- Object Recognition
- Object Detection
---
## 1. Object recognition(객체 인식)이란?

- 이미지 또는 비디오 상의 객체를 식별하는 컴퓨터 비전(computer vision)기술

- 기계가 인간처럼 이미지의 내용을 인식하도록 하는 것이 목표

- 자율 주행, 바이오이미징, 로봇 비젼과 같은 다양한 분야에서 유용



## 2. Object recognition의 종류
![01](https://user-images.githubusercontent.com/52816346/90980498-b0114b80-e596-11ea-9f41-72896391cd4d.JPG)

- Image Classification

  - 이미지를 입력으로 사용하고 해당 이미지의 label을 출력

- Object Localization

  - 이미지에서 객체의 찾아 경계 박스로 표현

- Object Detection

  -  Image Classification+ Object Localization

  -  경계 박스와 label을 합친 박스를 생성

  -  물체의 면적, 둘게 같은 요소를 정확하게 측정 불가

![02](https://user-images.githubusercontent.com/52816346/90980500-b1427880-e596-11ea-9afa-0ee34c531d49.jpg)

- Image Segmentation

  - 이미지의 각 객체에 대해 픽셀 단위 마스크로 표시

  - Object Detection의 추가 확장 기술

  - 경계 박스보다 더 세분화된 마스크 표현
  
  - 종류
  
    - Semantic Segmentation : 카테고리 또는 label에 따라 다른 색상으로 표시
  
    - Instance Segmentation : 각 객체의 경계를 식별하고 다른 색상으로 표시

![03](https://user-images.githubusercontent.com/52816346/90980501-b1db0f00-e596-11ea-8800-519e1b9efbe9.jpg)



### 3. 딥러닝을 활용한 Object Detection
- 단일 단계 방식

  - 정해진 위치와 정해진 크기의 객체만 탐색

  - 보통 원본 이미지를 고정된 사이즈로 나누고 각 영역에 대해 형태와 크기가 미리 결정된 객체의 고정 개수를 예측

  - 이단계 방식보다는 정확도가 떨어지지만 빠른 처리가 가능

  - ex) YOLO, SSD 등


- 이단계 방식

  - 객체를 포함할 가능성이 높은 영역을 제안

  - 제안 방법

    - Selective Search 등의 컴퓨터 비전 기술 사용

    - 딥러닝 기반의 영역 제안 네트워크(RPN - Region Proposal Network) 사용

  - 단일 단계보다 높은 정확도를 제공하지만 처리 속도가 느림

  - ex) Mask R-CNN, Faster R-CNN, R_FCN 등



## 출처
- Object Recognition 관련 내용 [출처](https://www.geeksforgeeks.org/object-detection-vs-object-recognition-vs-image-segmentation/)

- 딥러닝을 활용한 Object Detection [출처]([https://blogs.sas.com/content/saskorea/2018/12/21/%EB%94%A5%EB%9F%AC%EB%8B%9D%EC%9D%84-%ED%99%9C%EC%9A%A9%ED%95%9C-%EA%B0%9D%EC%B2%B4-%ED%83%90%EC%A7%80-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0/](https://blogs.sas.com/content/saskorea/2018/12/21/딥러닝을-활용한-객체-탐지-알고리즘-이해하기/))

- Mask R-CNN API [참조](https://github.com/matterport/Mask_RCNN)

