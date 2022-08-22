# 📚 GAN을 활용한 책표지 디자인 딥러닝 구축 프로젝트

<br>

>💭 **작업환경** `google colab`
>
>📅 **진행기간** 1차 21.12.08 ~ 21.11.12 수정 22.08.18 ~ 22.08.23

<br>

### 프로젝트 개요
📕 



- 가설: '**한국어 문학 출판물**에 공통적으로 적용되는 디자인 요소가 존재할 것'
- 프로젝트의 목표: **한국어 문학 출판물 표지 디자인에 반복적으로 나타나는 요인**을 파악함으로써 출판서적 표지 디자인이 가능한 인공지능 구축의 가능성을 모색해보고자 함 

<br>

### 파일 설명
- **code.ipynb** 분석을 위해 작성한 전체 코드(`google colab`에서 작업)
- **presentation.pdf** 프레젠테이션을 위해 제작한 ppt의 pdf 버전

<br>

### 결과 요약
- 모델링 실패: 책표지로 특정할 수 있는 이미지를 생성할 수 없었음

- ![image](https://user-images.githubusercontent.com/90163856/185928020-de71dce4-6913-466d-bbe8-0204350bb0d9.png)
↑ generator 생성 이미지 

---


### 데이터 세트의 특징
- 출처: 인터넷 서점 예스24(yes24.com)에서 국내 문학부문 최신간 표지 1천여건을 직접 크롤링하여 수집(selenium 활용)
    ※데이터 세트 전처리 과정: (400, 280)px로 이미지 크기 축소 통일<br>

![image](https://user-images.githubusercontent.com/90163856/185926415-f61da4ee-1b99-46af-913f-c405297f6986.png)


<br>

### 문제해결 과정
- 주 사용 라이브러리: tensorflow, numpy
- 사용 모델: DCGAN

1) 수집한 이미지를 numpy array로 변환 

2) image normalization 

3) generator / discriminator 구축



### 한계점과 보완 방안
#### 한계
- 데이터상의 한계: 일러스트/디자인 표지가 수집 과정에서 분리되지 않음, 표본이 지나치게 적음
- 모델 구축상의 한계: 가상머신의 GPU 한계를 고려하여 깊이를 얕게 설정 → generator가 이미지의 특징을 충분히 탐색하지 못함 
(batch 32, buffer size 1000, epoch 10)

#### 보완방안
- 데이터 측면: 일러스트/디자인 표지 분리, 데이터 추가 수집 
- 모델 측면: Google colab 이상의 고성능 컴퓨팅 자원을 활용하여 dense layer 추가, hyperparameter와 epoch 재설정 


### Update
- (2022.07.28 ~ 2022.08.23) 프로젝트 소개문 재작성


