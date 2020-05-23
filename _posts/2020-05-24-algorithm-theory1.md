---
layout: post
title:  "[개념정리] 힙(Heap)"
# subtitle: 
categories: algorithm
tags: 자료구조 개념정리
comments: true
# 공개여부:
published : true
---


#### 본 게시글은 '청년 AI Big Data 아카데미 교육' 과정에서 AI 강의를 수강하면서 작성했습니다. (POSTECH - 최승진 교수님)


> Linear Classification

사람과 기린을 분류해야 하는데 Height와 Weight 변수를 가진 데이터가 주어졌을 때를 생각해보자. ex) [Height, Weight] : [183, 64], [154, 45], [420, 780], [164, 51], [380, 660] ...  
복잡한 알고리즘을 적용할 필요도 없이 Height가 250cm 이상이거나 Weight가 300kg 이상 등의 자기 객관적인 기준을 가지고 매우 정교한 모델을 만들어 낼 수 있다. 이와 같이 둘 중 하나로 분류되는 모델을 이진 분류 모델(Binary Classification Model)이라고 한다.

그렇다면 사람과 고릴라를 분류해야 한다고 생각해보자. 서부 고릴라의 경우 수컷은 160 ~ 180cm, 암컷은 150cm 까지 자라며 체중 또한 각각 140 ~ 180kg, 90kg 까지 성장한다. 그렇다. 머리로 간단하게 알고리즘을 짤 수 없다. 아래의 그림을 보자.

![](/assets/img/20200521/1.jpg){: .align-center}  

다음과 같은 경우에 주어진 정보로 분류해본다고 하자. 사람은 세계 성인 평균 몸무게는 62kg고, 평균 신장은 165cm라고 치자. Linear Classfication 개념을 모르고 단순하게 분류한다고 가정했을 때 Height/Weight를 구해서 풀어볼 수 있을 것이다. 인간은 약 2.66이 나오며, 고릴라의 경우 1.06 ~ 1.7 까지 나온다. 인간의 경우 워낙 스펙트럼이 넓기때문에 대략 Height/Weight가 1.8 이상인 경우에 사람으로 판단한다고 하자. 이를 그림으로 나타내면 아래와 같다.

![](/assets/img/20200521/2.jpg){: .align-center}  

가장 잘 분류했다고 할 수 있을까? 해당 모델의 정확도는 전체 30개의 데이터중 3개를 틀렸기 때문에 Accuracy는 90%가 된다. 사실 이와 같은 데이터셋에서 선 하나로 잘 분류할 수 있는 경우는 아래이 30개의 데이터중 1개만을 틀리게 분류했을 경우이다. 이 때 Accuracy는 96.7%가 나온다.

![](/assets/img/20200521/3.jpg){: .align-center}  

이와 같이 가장 Accuracy가 높은(혹은 Error가 낮은) 직선의 방정식을 찾아가는 과정이 Linear Classification이다. 

![](/assets/img/20200521/4.jpg){: .align-center}  
