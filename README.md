# Database Application COM4011

> 2021.03.02

## Team : TopGap

## Senario
> 국민건강관리공단에서는 다양한 일반건강검진 항목들을 복합적으로 분석하여 향후 당뇨병 발생 여부를 미리 예측할 수 있는 새로운 데이터 모델을 개발하기 위하여 빅데이터 분석 전문회사인 A사에 그 일을 위탁하였다.


## Problems
> 우리나라 40세 이상 100만명의 일반건강검진 데이터를 활용하여 연령별, 지역별, 성별 건강검진 내역의 건강상 특이점 분석, 중요 데이터 속성 추출 및 패턴 분석
---
## Plans
- [Week 3-4](#20210316) - [x]
    - 파이썬 라이브러리 공부 및 당뇨병 지식에 대한 공부
    - 데이터 전처리

- [Week 5-6](#20210330) - [x]
    - 데이터 분석 작업(중요 데이터 속성 추출)
  
- [Week 7-8](#20210413) - []
    - 발표 자료 준비    
  
- [Week 9-10]() - [ ]
    - 모델 설계 공부 및 모델 설계
  
- [Week 11-12]() - [ ]
    - 모델 정확도 검증
  
- [Week 13-14]() - [ ]
    - 데이터 시각화 및 프레젠테이션 작업
---
### Member

<p>
<a href="https://github.com/promisemee">
    <img src="https://github.com/promisemee.png"
    width="100">
<a href="https://github.com/kms2698">
    <img src="https://github.com/kms2698.png"
    width="100">
<a href="https://github.com/dury008">
    <img src="https://github.com/dury008.png"
    width="100"> 
<a href="https://github.com/sejin1031">
    <img src="https://github.com/sejin1031.png"
    width="100">    
<a href="https://github.com/ji-hun-choi">
    <img src="https://github.com/ji-hun-choi.png"
    width="100">       
</p>

김다인 김민상 박진혁 엄세진 최지훈

---

### 2021.03.16
### Week 3

  - 과제 수행 계획서 작성

  - 2021.03.23 PBL 시간까지 각자 당뇨병에 대한 자료 조사 후 LMS 그룹 페이지에 업로드


### 2021.03.23
### Week 4


  1. 과제수행 계획서의 사실 -> 문제 상황 + 팀원의 역량

  2. 35개의 속성 중에 직접 관련있는 feature를 알아내기 위해서는 의학적 지식이 필요

  3. To-be는 굵직한 아이디어. 팀의 status에 따른 이루어져야할 것

  4. 다른팀 아이디어 활용 가능. 서로서로 오픈소스로 활용

  5. [Neural Network Project with python](http://www.kyobobook.co.kr/product/detailViewEng.laf?mallGb=ENG&ejkGb=ENG&barcode=9781789138900) -> 멀티레이어 퍼셉트론 이용한 당뇨병 예측하는 프로젝트가 책에 있음

  6. 정제를 하였더라도 나중에 모델링을 하면서 다시 정제를 해야 할 수도 있음

  7. 예측 모델역시 단순 한가지 뿐만 아니라 여러가지 사용하여 설계를 해보아야함. 신경망을 이용할 수도 있음

  8. 중간 발표까지 중요한 속성을 뽑아내야하는데 그러한 방법들에 대해 공부해야함

  -> 상관관계분석이나 의학적인 지식으로 중요한 속성 뽑아내기

  데이터 분석할 때

  - 결측치, 이상수치 필터링처리

  - 데이터 날려버릴 때 잘 처리하기

### 팀 회의록

  1. 데이터 필터링 처리 주피터노트북으로 해서 업로드하기(파일 업로드로 해도 되고 편한대로)

  2. 필요한 공통 속성 정하기. 

 - 성별은 여성이 더 걸리기 쉽다

 - 나이 많을수록

 - 신장 + 체중으로 비만도 계산(BMI)

 - HDL 콜레스테롤

 - 혈압 -> 고혈압 여부

 - 혈색소 당화혈색소 차이점? 

 -  치아와 상관관계 파악하기 -> 안해도될거같음
---
### 2021.03.30
### Week 5

- 콜레스테롤 column은 누락이 많아서 제거 (18년도 데이터)

- [github repository](https://github.com/kms2698/diabetes-analysys_topgap) 생성

- Questions

1. 데이터셋 년도 어떻게?

    원하는 대로 -> (17, 18년도 데이터셋 사용)

2. 데이터 범주의 기준

- 데이터가 많을수록 모델의 정확도는 올라간다. 결측치나 이상치를 보전해서 쓸 수 있으면 합리적으로 사용하는게 좋다. 하지만 임의대로 평균값이나 이상한 값으로 하면 모델 예측의 정확도를 떨어트릴 수 있음
- 쓰레기 데이터를 쓰면 쓰레기 데이터밖에 안나오므로 과감하게 버려야함
- 30개 가량의 속성 중 당뇨병에 영향을 미치는 속성을 잘 골라야하는데 기껏해야 5개 정도로 예상함    
- 별로 중요하지 않으면 그냥 두거나 버리면 됨(신경망일 경우 버려야함)

    --> 가능한 한 보정해서 쓰고, 적절히 보정할 방법이 없다면 버려야한다.

 1. 필요없는 속성

 2. 데이터 지울 때 특정 줄 다 지울지 특정 속성만 지울지

     모델에 따라서 달라질텐데, 그 칼럼이 예측모델에 사용되지 않으면 신경 쓸 필요가 없다.

     사용된다면 결측치 있으면 해당 row를 날려서 사용해야하는게 맞음.

### 다음주까지 할 것?

- 엔트로피 분석하여 중요 속성 알아보기
---
### 2021.04.06
### Week 6

1. 각자 분석해본 결과 공유

   - 김다인 -> 흡연, 청력은 정보이득이 적은편
   - 김민상 -> 데이터 100만개 중 60만개정도로 정리, 음주가 낮게 나옴
   - 박진혁 -> 음주 정보이득 낮게 나옴
   - 엄세진 -> 지니지수 분석 추가
   - 최지훈 -> 음주 정보이득은 과도하게 낮게나옴


    --> 공통적으로 나이에 따라서 정보이득 높게 나옴

2. 사용할 속성 : 연령대코드, 고혈압(수축기, 이완기), 복부비만(허리둘레, 성별), BMI(체중, 신장), 혈당
3. 그냥 보여줄 속성: 성별코드로 분류한 결과

4. 분류 기준

   1. 고혈압 : 120~139/80~89 전단계/  140~159/90~99 1기 / 160/100 2기

   2. 복부비만 : 남자 90 이상, 여자 85 이상

   3. BMI : 공식대로 체중 / (키m)**2

   4. 비만여부(bmi): 

       - 저체중 + 정상 < 24.9
       - 25.0 <= 과체중 <= 29.9
       - 비만 >= 30

        (저체중은 18.5 미만이나 전체 데이터셋의 4.6% 이므로 정상과 통합)

   5. 혈당: 공복 126 이상, 식후 200 이상 -> 당뇨 / 공복  100~125 당뇨 전 단계


6. 이상치 필터링 기준
   - 허리둘레 :  40cm 이하, 140cm 이상은 필터링 처리

다음주까지 할 것?
   1. 정해진 기준으로 데이터 정제후 깃허브 업로드
   2. 전부 업로드 되면 병합
   3. 데이터 어떻게 시각화 해서 보여줄지 생각

### 2021.04.13
### Week 7
1. 중요 속성 추출
    - 의학지식
    - 카이 제곱 통계 테스트
    - 트리 기반 모델
    - 렌덤 포레스트 특성 중요도
    - 정보 증가량
    - 상관계수  
2. 여러 지표들을 통해 최종속성 도출   

3. 발표 PPT 완료
4. 발표담당 : 최지훈
5. 각자 Q&A 및 사용한 모델 및 테스트 공부
---
### 2021.04.20
### Week 8
1. 발표
    