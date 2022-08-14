# BERT multilingual model

Data : Web crawling at Musinsa's review, star_rate

Model : BERT multilingual model using Hugging Face API

---


## 개요

인터넷에서 상품을 구매할 때 소비자의 큰 결정요인 중 하나는 실제로 구매한 고객들의 리뷰입니다.

또한 상품이 나타나는 순서 및 인기요인을 판가름하는 기준은 별점입니다.

그러나 모든 리뷰에서 긍정리뷰+긍정별점 , 부정리뷰+부정별점이 매칭되지는 않습니다.

그래서 저희는 보다 신뢰성 있는 리뷰 및 별점을 얻기 위해 bert모델을 이용해 학습하여

임의의 리뷰를 작성했을때 자동적으로 그에 맞는 **실질별점**을 만들어보고자 프로젝트를 진행했습니다.

---
## 수집 및 전처리

Musinsa 상품 페이지에서 약 35만개의 평점과 별점을 크롤링하였습니다.

하지만 데이터 중 5점의 별점이 압도적으로 많은 **imbalance data**였고 이를 해결하기 위해 추가적으로 1~3점의 별점을 추가적으로 크롤링했습니다.


|평점 5|평점 4|평점 3|평점 2|평점 1|
|---|:---|:---|:---|:---|
|298540|39242|5332|563|463|

그러나 