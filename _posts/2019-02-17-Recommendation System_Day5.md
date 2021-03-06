---
layout: post
title: "현대 세대의 Recommender System의 장단점에 대한 이해"
subtitle: "6"
categories: data
tags: rs
comments: true





---



# Recommendation System_Day5

- DAY5 _ 현대 세대의 Recommender System의 장단점에 대한 이해
- 각 본문의 **출처**는 제목 링크와 같습니다.

<br/>

------

### [Introduction to Recommender Systems in 2018 ](https://tryolabs.com/blog/introduction-to-recommender-systems/)

- 가벼운 번역.

많은 전자상거래와 소매 회사들은 그들의 웹사이트에 추천자 시스템을 시행함으로써 데이터의 힘을 활용하고 판매를 증대시키고 있다. 간단히 말해서, 이러한 시스템은 **사용자의 이익을 예측하고 그들에게 상당히 흥미로운 항목을 추천하는 것을 목표**로 한다. 추천 시스템에 필요한 데이터는 영화를 보거나 노래를 들은 후, 검색 엔진 쿼리와 구매 이력 또는 사용자/아이템 자체에 대한 다른 지식에서 비롯된다. Spotify, YouTube, Netflix와 같은 사이트들은 각각 재생 목록, 소위 Daily Mix를 제안하거나 비디오 추천을 하기 위해 이 데이터를 사용한다.

이 블로그 포스트에서는 가장 인기 있는 **추천 시스템의 다양한 유형**을 설명하고, 몇 가지 예를 통해 그들이 어떻게 작동하는지에 대한 통찰력을 줄 것이다. 이 주제에 대한 동기부여를 주고 그것이 가치 있는 투자인지 아닌지를 결정하는 데 도움을 주기 위해, 우리는 몇몇 실제 사례 연구들을 통해 추천자 제도를 시행하기 위한 높은 수준의 요구 사항에 대해 말하고, 그것들이 어떻게 공정하게 평가될 수 있는지에 대해 이야기 할 것이다.

<br/>

### Recommender system 시행의 장점

추천 시스템을 사용하는 회사들은 **매우 개인화된 추천과 향상된 고객 경험의 결과를 통한 판매 증가에 초점**을 맞추고 있다. 추천시스템은 일반적으로 검색 속도를 높이고 사용자가 관심 있는 콘텐츠에 쉽게 접근할 수 있도록 하며 검색하지 않았을 제안으로 이들을 놀라게 한다. 더욱이 기업들은 수신자의 관심을 만족시키는 새로운 제안, 혹은 개인에게 맞는 영화와 TV 쇼의 추천과 관련된 이메일을 보내 고객들을 얻고 유지할 수 있다. 사용자는 기업이 자신을 알고 이해한다고 느끼기 시작하고, 추가 제품을 구입하거나 더 많은 콘텐츠를 소비할 가능성이 더 높다. 사용자가 원하는 것을 알면 회사는 경쟁 우위를 확보하고 경쟁업체에 고객을 빼앗길 위험이 줄어든다.

시스템 과 제품에 대한 추천으로 사용자에게 추가적인 가치를 제공하는 것은 매력적이다. 이는 회사가 경쟁사들보다 앞서고 결국 이들의 수익을 증가시킬 수 있게 해준다.

<br/>

### Types of recommender systems

Recommender systems 은 아래 두 가지의 정보를 바탕으로 작동한다.

- **Characteristic information** :  항목 (keywords, categories 등) 및 사용자 (preferences, profiles 등)에 관한 정보
- **User-item interactions** : 등급, 구매건수, 호감 등의 정보 

이를 바탕으로 추천시스템의 첫번째 분류에 도달한다. 1) **Characteristic information을 사용한 Content-based**, 2) **User-item interactions을 기반으로한 Collaborative filtering**. 이 Hybrid 시스템은 한 가지 정보만을 사용했을 때 발생하는 문제를 피하기 위한 목적으로 두가지 정보를 모두 사용한다. 다음으로, 우리는 Content-based와 Collaborative filtering을 좀 더 깊이 파고들 것이다.

<br/>

#### Content-based systems

Content-based system 은 user의 과거 item과 profile features을 사용하여 추천한다. 이는 사용자가 과거에 어떤 항목에 관심이 있었다면, 그들은 미래에 다시 그것에 관심을 가질 것이라고 가정한다. 유사한 품목은 대개 그 특징에 따라 분류된다. User profile은  과거의 상호작용을 이용하거나 자신의 관심사에 대해 명시적으로 나타냄으로써 구성되어 있다. 여기에는 사용자 개인 데이터와 사회 데이터를 활용하여 오직 content-based라고만 여겨지지 않는 다른 시스템이 있다.

한 가지 문제는 **과도하게 집중된 interest 때문에 너무 정확한 추천을 하는 것**이다. (사용자 A는 카테고리 B, C, D에만 관심이 있고, 시스템은 설령 이외의 범주에 대해 흥미로워 할지라도 추천할 수 없다.) 또 다른 일반적인 문제는 신규 사용자가 명시적으로 정보를 나타내지 않는 한 정**의된 profile이 부족**하다는 것이다. 그럼에도 불구하고 새로운 항목을 시스템에 추가하는 것은 비교적 간단하다. 우리는 단지 우리가 그들의 특징에 따라 그들에게 그룹을 할당하면 된다.

<br/>

#### Collaborative filtering systems

이 시스템은 관심 항목을 필터링하기 위해 **user interactions를 이용**한다. 우리는 각 항목(i, j)가 user i와 item j 사이의 상호작용을 나타내는 매트릭스와의 상호작용들을(집합) 시각화할 수 있다. Collaborative filtering을 보는 흥미로운 방법은 이를 classification과 regression을 일반화 한 것이라고 생각하는 것이다. 이러한 경우 우리는 다른 변수 (features, x)에 직접 의존하는 변수(y)를 예측하는 것을 목표로 하지만, Collaborative filtering에서는 feature variables 와 class variables 의 구별을 하지 않는다. 행렬의 문제로 보면, 우리는 고유한 column 값을 예측하는 것이 아니라 주어진 value 값을 예측하는 것을 본다.

![Illustration of classification vs collaborative filtering.](https://tryolabs.com/images/blog/post-images/2018-05-09-introduction-to-recommender-systems/collaborative-filtering-systems.954f82f7.jpg)

간단히 말해서, collaborative filtering 시스템은 **user가 item A를 좋아하고 다른 user가 item B를 좋아하는 경우, 첫 번째 user도 두 번째 item에 관심을 가질 수 있다는 가정을 기반**으로 한다. 즉, 그들은 과거와의 상호작용을 바탕으로 새로운 상호작용을 예측하는 것을 목표로 한다. 이 목표를 달성하기 위한 방법에는 **메모리 기반(memory-based)**과 **모델 기반(model-based)** 두 가지가 있다.

<br/>

#### Memory-based

여기에는 두 가지 접근법이 있다.  첫 번째 접근법은 **사용자 군집을 식별하고 한 특정 사용자의 Interactions을 이용하여 다른 유사한 사용자의 interactions을 예측**한다. 두 번째 접근법은 **사용자 A에 의해 등급이 매겨진 항목들의 군집을 식별하고 이를 활용하여 사용자 A의 interactions와는 다르지만 유사한 item B에 대한 사용자 A의 interaction를 예측**한다. 사용자 A와 유사하지만 유사한 항목 B의 상호작용을 예측한다. user-item interactions 수가 좋은 품질의 클러스터를 생성하기에 너무 낮을 수 있기 때문에 이러한 방법들은 대개 large sparse matrices과 함께 주된 문제가 된다.
<br/>

#### Model-based

이 방법은 Machine learning과 Data mining 기술에 기반한다. 예측을 할 수 있는 모델을 훈련시키는 것이 목표이다. 예를 들어, 우리는 기존 user-item interactions를 사용하여 사용자가 가장 좋아할 수 있는 상위 5개 항목을 예측하는 모델을 훈련시킬 수 있다. 이러한 방법의 한 가지 장점은 **memory-based과 같은 다른 방법과 비교했을 때 더 많은 users에게 수의 사용자에게 더 많은 items를 추천할 수 있다**는 것이다. 우리는 그들이 Popularity Bias problem : 유명한 것으로 추천이 치우치게 된다는 것. 음악을 추천한다고 할 때 collaborative filtering을 사용하여 3명 밖에 듣지않은 음악을 추천하는 것은 매우 어려운 일이다. 같은 similarity점수라 하더라도 더 많은 사람들이 좋아한 것을 추천하게 된다.large sparse matrices를 가지고 작동 때에도 large *coverage*를 가지고 있다고 말한다.

<br/>

#### Issues with collaborative filtering systems

이러한 시스템을 만들 때 생각해야 하는 두 가지 주요 challenges가 있다.

- Cold start : 시스템이 작동하기에 **충분한 정보(user-item interactions)**를 가져야 한다. 만약 우리가 새로운 전자상거래 사이트를 개설한다면, 우리는 사용자들이 상당수의 아이템과 상호작용을 하기 전까지는 추천을 할 수 없다.

- Adding new users/items to the system : 새로운 사용자든 항목이든, 우리는 그들이 기존 상호작용을 하지 않기 때문에 시스템에 대한 사전 정보가 없다.

이러한 문제는 가입 시 다른 유형의 데이터(성, 연령, 관심사 등)를 사용자에게 요청하고, 데이터베이스의 다른 기존 항목과 관련시킬 수 있도록 item의 메타 정보를 사용하여 완화될 수 있다.

<br/>

### Practical examples of collaborative filtering

**협업 필터링은 현재 가장 자주 사용되는 접근방식 중 하나이며 대개 콘텐츠 기반 추천보다  더 나은 결과를 제공**한다. 이것의 몇 가지 예는 Youtube, Netflix, Spotify의 추천 시스템에서 찾을 수 있다. 다음으로, 우리는 협업 필터링 시스템을 구축하기 위한 두 가지 기술을 검토할 것이다.

<br/>

#### Fully-connected neural networks

고전적인 접근법 중 하나는 matrix factorization이다. user-item interactions의 행렬에서 모르는 값을 것을 완성하는 것을 목표로 한다 (행렬 *R*이라 하자). 우리가 두 matrix *U*와 *I*를 가지고 있고, *UxI* 알려진 값에선 *R*과 같다고 상상해보자. *UxI* 를 사용하여 우리는 또한 *R*의 알려지지 않은 값에 대해 알 수 있을 것이고, 이 값은 추천시스템을 만드는데 사용될 수 있다.

![Illustration of matrix factorizations.](https://tryolabs.com/images/blog/post-images/2018-05-09-introduction-to-recommender-systems/fully-connected-neureal-networks.8600985b.jpg)



행렬 *U*와 *I*를 찾는 현명한 방법은 **Neural network**를 사용하는 것이다.

첫째, 각 user와 item을 각각 *M*과 *N* 차원의 벡터로 매핑해야 한다. 이것은 우리가 보통 Embedings 라고 불리는 user와 item의 representations를 알아야 한다는 것을 의미한다.  배울 필요가 있다는 것을 의미한다. 우리는 이 벡터의 값을 아직 모르기 때문에 무작위 초기화부터 시작해야 할 것이다.

그런 다음 각 user-item interactions(u, x)에 대해 사용자 u와 항목 x를 모두 연결하여 단일 벡터를 제공한다. 우리는 이미 이 user-item interactions의 가치를 알고 있기 때문에, 이 벡터에 대한 Neural network output을  강요할 수 있다. 그런 다음, 네트워크는backpropagation을 사용하여 자체 가중치와 embeddings을 모두 조정하므로, 결과는 우리가 기대하는 것과 일치한다. 그러므로 Neural network는 사용자와 항목을 대표하는 최선의 방법을 학습할 것이며, 그 결과 발생하는 embeddings으로 공급함으로써 이전에 보지 못했던 interactions을 예측하는 데 유용할 것이다.



예를 들어, 위의 이미지를 보고 'User Matrix'와 'Item Matrix'가 랜덤하게 초기화된 embeddings라고 가정해보자. interaction(A, X)을 위해, 우리는 벡터 [1.2, 0.8, 1.2, 0.6]로 우리의 Neural network 에 적용하여 그것의 output을 4.5와 같게 할 것이다. 이 예시 에서 우리는 MSE을 loss function으로 사용할 수 있다. 만약 우리가 binary matrix를 가지고 있다면, cross entropy와 같은 classification에 더 일반적인 loss function을 사용하는 것이 적절할 것이다.

이 접근법의 매우 흥미로운 결과는 embeddings가 보통 특정한 의미 정보를 포함하고 있다는 것이다. 따라서, 우**리는 알려지지 않은 상호작용에 대한 예측만 가지고 끝나는 것이 아니라, 우리가 실행 가능한 것으로 만들 수 있는 통찰력**을 얻는다. 예를 들어, 유사한 user는 결국 user 벡터 공간에서 서로 더 가깝게 될 것이다. 예를 들어, 이것은 고객이 어떻게 행동하는지 연구하는데 유용할 수 있다.



#### Item2vec

Item2vec는 Word2vec와 동일한 기법을 사용하여 항목에 대한 embeddings을 찾을 수 있다고 제안한다. 이는 매장에서 이뤄지는 구매를 상황적 정보로 활용하는데, 이것은 **유사한 상황에서 구매한 품목을 비교할 수 있다**는 것을 암시한다.

이 접근법은 사용자가 추천이 이뤄지는 순간에 직접 관여하거나 고려하지 않는다. 그러나 우리의 목표가 사용자가 선택한 특정 item에 대한 사용자 대안을 보여주는 것이라면 매우 유용할 수 있다.

우리가 여기서 가지고 있는 주요 이슈는 좋은 embeddings를 생산하기 위해서는 엄청난 양의 데이터가 필요하다는 것이다. Item2vec 논문에서는 2개의 데이터 셋을 활용했다 ( 1) 900만 개의 interactions, 73만2000개의 users, 4만9000개의 items 2) 37만9000개의 interactions, 1706개의 items, user에 대한 정보는 사용하지 않았다.)

<br/>

### When to implement a recommender system?

이제 우리는 recommender system에 대해 어느 정도 이해했으므로, recommender system을 언제 실행하면 좋을지 생각해 볼 때가 되었다.

만약 당신이 성공적인 사업을 운영하고 있다면, 당신은 아마도 recommender system 없이도 살아남을 수 있을 것이다. 단, 데이터의 힘을 활용하여 더 나은 사용자 경험을 창출하고 수익을 증대시키려면, 데이터의 구현을 진지하게 고려해야 한다.

좋은 recommendation system에 투자할 가치가 있는가? 이 질문에 답하는 좋은 방법은 그**러한 제도를 시행한 회사들이 어떻게 경쟁해 왔는지**를 보는 것이다.



- 맥킨지에 따르면 아마존 구매의 35%가 그들의 recommender system의 결과라고 한다.

- 알리바바는 2016년 11월 11일 중국 글로벌 쇼핑 페스티벌 기간 중personalized landing pages를 이용해 전환율의 최대 20%의 성장을 이뤘다고 전했다.

- 사람들이 유튜브에서 비디오를 보는 데 쓰는 시간의 70%는 추천에서 나온다고 한다.

- 맥킨지에 따르면, 사람들이 넷플릭스에서 보고 있는 것의 75%는 추천에서 나온다고 한다.

- 한 임원이 작성한 본 논문에 따르면, Netflix는recommender system을 채택하면 매년 약 10억 달러를 절약할 수 있다.

> 월정액 감소는 모두 기존 가입자의 평생 가치를 높이고, 취소된 가입자를 대체하기 위해 필요한 신규 가입자의 수를 감소시킨다. 우리는 개인화와 추천의 결합으로 연간 1억 달러 이상을 절약할 수 있다고 생각한다.

- 맥킨지에 따르면 교차판매와 카테고리 침투 기술은 매출을 20% 늘리고 이익을 30% 정도 늘린다.

<br/>

### What are the prerequisites for building a recommender system?

데이터는 가장 중요한 단일 자산이다. 기본적으로, 당신은 user와 item에 대한 세부사항을 알아야 한다. 이용 가능한 메타데이터가 전부라면, 컨텐츠 기반의 접근부터 시작할 수 있다. 만약 당신이 많은 user interactions을 가지고 있다면, 당신은 더 강력한 협업 필터링으로 실험할 수 있다.

당신이 가지고 있는 데이터가 클수록 당신의 시스템은 더 잘 작동할 것이다. 더 나아가서, 당신이 이용할 기술들에 의해 수집될 수 있도록 데이터를 이해하고 정확하게 조작할 수 있는 팀과 함께 일해야 한다.

**User-item interactions에 관하여 명심해야 할 사항:**

- 예를 들어, 전자 상거래 사이트에서 작업하는 경우, 항목 클릭, 검색, 방문, 즐겨찾기 항목, 구매, 명시적 등급, 쇼핑 카트의 요소 또는 심지어 폐기된 제품도 interactions이 포함되도록 **시스템에 관한 interactions을 정의**해야 한다.

- interactions 은 *명시적* 이거나 *암묵적* 으로 정의될 수 있다. 명시적인 것은 사용자가 항목의 순위를 매기거나 리뷰를 남기는 것과 같이 항목에 대해 긍정적인 또는 부정적인 관심을 보일 때 같은 상황을 특징으로 한다. 암묵적인 것은 아이템을 찾거나 구매하는 것과 같은 사용자의 관심사가 그들의 행동에서 파생되는 것이다.

- 사용자 및 항목당 상호작용 수가 클수록 최종 결과는 더 좋을 것이다.

- 전형적으로, 사용자들이 많은 것과 그렇지 않은 것들과 interactions하는 매우 인기 있는 품목들이 있는데, 이것은 *Long Tail* 라고 알려진 것을 구성한다. 추천 시스템은 대개 인기 있는 item에서 잘 작동하지만, 비록 그들이 이미 인기 있는 item을  알고 있을 가능성이 높기 때문에 이용자들에게는 그다지 흥미롭지 않을 것이다.*Long Tail* 의 item은 사용자가 추천받지 않는 경우 전혀 고려하지 않을 수 있기 때문에 가장 흥미로운 품목이다.

![Illustration of the long tail.](https://tryolabs.com/images/blog/post-images/2018-05-09-introduction-to-recommender-systems/long-tail.f55e22ee.png)



신제품 출시를 하는 상황에서 추천 시스템을 처음부터 시행하는 것은 쉽지 않을 것이다. content-based approach는 사용자가 상호작용을 시작한 후에 유용하게 쓰일 수 있으며, 또는 당신은 처음에 당신을 돕기 위해 그들의 관심사에 대해 그들에게 명시적으로 물어볼 수 있다. 일단 사용자와의 interactions 의 양이 증가하면, 시스템의 잠재력을 증대시키기 위해 collaborative-filtering approach협력적 필터링 접근방식을 고려해야 할 때다.

마지막으로, 시스템을 평가하고 그 성능을 향상시키는 다른 방법을 생각하는 것이 가장 어려운 과제가 될 것 같다. 하지만 낙담하지 마라, 여러분은 확실히 재미를 느낄 것이고 또한 여러분의 수입의 증가를 느낄 수 있을 것이다, 그렇지 않은가?

>당신의 조직에서 Recommender system를 시행할 생각이십니까? [여기](https://tryolabs.com/blog/2019/02/13/11-questions-to-ask-before-starting-a-successful-machine-learning-project/) MLnitiative를 시작하기 전에 꼭 물어봐야 할 11개의 질문이 있다.

<br/>

### How to evaluate a recommender system?

이 시스템들은 각기 다른 평가 방법을 가지고 있고 그 답은 당신의 목표에 달려있다. 만일 당신이 상위 5개 항목(즉, 사용자가 intraction 할 가능성이 가장 높은 항목)을 추천하는데만 관심이 있다면, 평가를 실시할 때 나머지 항목에 대한 예측을 고려할 필요가 없다.

그러나, 당신은 그 5가지 추천방식의 우선순위에 매우 관심이 있을 수 있으므로, 당신은 이것을 고려해야 할 것이다. 선택한 평가 방식은 당신이 시스템을 설계하는 방식에 중요한 영향을 미친다. Recommender system 평가에는 *online* and *offline* 접근 두 가지 유형이 자주 논의된다.

<br/>

#### Online methods

온라인 방법(**A/B test**라고도 함)으로, 추천사항을 고려하여 사용자 반응을 측정한다. 예를 들어 사용자가 변환 속도뿐만 아니라 권장 항목을 클릭할 때 측정하여 시스템의 직접적인 영향을 평가할 수 있다. 비록 실험을 실행하는 유일한 방법은 이미 만들고 있는 시스템과 interaction을 하는 것이기 때문에 보통 구현하기 어렵긴 하지만, 평가에 대한 이 방식은 이상적이다. 실패한 실험은 수익과 사용자 경험에 직접적인 영향을 미칠 것이다. 게다가, 실제 고객들을 실험에 이용하는 것은 당신이 사전에 데이터를 가지고 있었을 때보다 더 느릴 것이다.

<br/>

#### Offline methods

오프라인 방법은 사용자가 직접 관여하지 않으며 온라인 방법과 달리 시스템을 배치할 필요가 없기 때문에 실험 단계에선 이상적이다. 데이터는 training data sets와 validation data sets로 나뉘는데, 이는 데이터의 일부가 시스템을 구성하는 데 사용되고 다른 부분은 시스템을 평가하는 데 사용될 것임을 의미한다. 이러한 방법을 사용할 때는 결과에 영향을 미치는 요인이 있을 수 있고 적절히 표현할 수 없기 때문에 주의할 필요가 있다. 예를 들어 결과가 특정 시점의 고객 분위기일 수 있으므로 추천시스템을 적용하는데 (계절, 날씨 등)에서 시간 요인이 매우 중요할 수 있다.

<br/>

### Final remarks

우리가 이 게시물에서 보았듯이, 시스템에서의 recommendation system을 포함하는 것은 매력적인 베팅이다. user의 관점에서 보면, 경험과 참여를 만들어낸다.사업을 위해, 이는 더 많은 수익을 창출한다.

소규모의 사용자를 위한 기본 추천 시스템을 갖추는 것이 좋으며, 일단 사용자 기반이 커지면 더욱 강력한 기술에 투자하는 것이 좋다.

가장 빼놓을 수 없는 자원은 **data**다. 관리하거나 제대로 보관하지 않으면 필요한 절차를 밟아야 할 때다. 일단 당신이 실행 단계에 도달하면, 그 주제를 더 깊이 파헤칠 필요가 있을 것이다.

비즈니스 목표는 처음에 당신이 집중해야 할 추천 시스템의 유형을 결정할 것이다: 이미 활동 중인 사용자들에게 더 많은 참여를 이끌어내는지, 아니면 활동이 드문 고객들을 더 활동적이게 만들 것인지.

비즈니스 목표를 정의하는 것 외에, 당신이 당신의 사이트에서 생성된 정보를 분석하고 이해할 수 있는 것이 핵심이다. 그 점을 고려하면, 추천 시스템의 성공을 막을 수 있는 것은 아무것도 없다.

<br/>

---

### [TED 일라이 파리저(Eli Pariser): 온라인 "필터 버블"을 주의하세요 (9:04)](https://www.ted.com/talks/eli_pariser_beware_online_filter_bubbles?language=ko)

표준화된 페이스북과 구글은 더이상 존재하지 않는다.

똑같이 '이집트'를 검색했을 때 다니엘은 구글 검색 결과의 첫 페이지에서 이집트에서의 시위에 대해 아무런 결과도 얻지 못했습니다. 스콧의 결과는 시위에 대해 가득했습니다. 



웹 개인화는 구글과 페이스북만 그런 것이 아닙니다. 이것은 웹에 광범위하게 나타나는 것입니다. 인터넷 최대 뉴스 사이트인 야후 뉴스는 이제 개인화 되어, 서로 다른 사람들이 서로 다른 결과를 얻습니다. 허핑톤 포스트, 워싱턴 포스트, 뉴욕 타임즈 등 모두가 개인화를 다양한 방식으로 시도하고 있습니다. 이것이 인터넷이 우리가 보기 원한다고 생각하지만 우리가 반드시 볼 필요는 없는 것을 보여주는 세상으로 빠르게 움직이게 하고 있습니다.



저는 이것이 정말 문제라고 생각합니다. 여러분이 이런 필터들과 알고리즘들을 함께 사용한다면, 제가 필터 버블이라 부르는 것을 겪을 것이라고 생각합니다. **여러분의 필터 버블은 온라인에서 살아가는 여러분만의 개인적인 유일무이한 정보 우주입니다. 여러분의 필터 버블 안에 있는 것은 여러분이 누구인가, 여러분이 무엇을 하는가에 달려있습니다. 하지만 무엇이 포함될지 여러분이 결정하지 않습니다.** **그리고 보다 중요한 것은, 실제로 무엇이 편집되어 사라지는지 확인하지 않습니다.** 필터 버블의 문제점 중 하나는 넷플릭스의 연구자들에 의해 발견되었습니다. 그들은 넷플릭스의 큐(queue)를 들여다 봤고, 아마도 우리 중 많은 수가 인지해 왔을 재미난 뭔가를 알아냈습니다. 압축 된 후, 즉시 우리의 가정으로 압축이 해제됬던 영화 파일들이 있었던 겁니다.영화들은 큐에 들어가고, 바로 압축이 해제됩니다. "아이언맨"은 바로 압축이 풀어지고, "슈퍼맨을 기다리며"는 오랜 시간 대기열을 탑니다.



이런 종류의 알고리즘 필터, 개인화 필터의 문제점은 **여러분이 가장 처음에 무엇을 클릭하는지 주로 탐색을 하기 때문에 균형을 깰 수가 있다는 것**입니다. 균형잡힌 정보 식단 대신에, 정보 정크 푸드로 둘러싸일 수 있습니다. 이것은 실제로 인터넷에 대해 우리가 원하는 것이 아닌 기사를 볼 수도 있다는 것을 시사합니다. 또 다른 문제는 그 알고리즘은 아직까지 편집자들과 같이 일종의 내**면적 윤리를 가지고 있지 못하다는 것**입니다. 그래서 알고리즘이 우리를 위해 세상을 조율할 것이라면, 또 **알고리즘이 우리가 무엇을 보고 보지 않을지 결정할 것이라면, 그것이 그저 관련성에 맞춰진 것이 아님을 확실히 할 필요가 있습니다.** 또한 거북하거나, 도전적이거나, 또는 중요한 다른 관점들을 우리에게 보여주기도 한다는 것을 확실히 할 필요가 있습니다. 이것이 TED가 하는 일입니다.



이러한 개인화는 1915년 신문들이 그들의 시민적 책임에 대해 많이 노력했던 것과는 다릅니다. 그 당시 사람들은 신문이 아주 중요한 일을 하고 있음을 인지했습니다. 사실, 시민들에게 괜찮은 정보가 유입되지 못한다면, 민주주의가 제 기능을 할 수가 없습니다. 신문이 필터로서 작용했기 때문에 매우 중요했고, 그리고 나서 기자의 윤리가 발전했습니다. 완벽하지는 않지만, 우리가 지난 세기를 지나오게 했습니다. 현재, 우리는 웹상에서 1915년으로 돌아와 있는 것과 같습니다. 그런 책임을 그들이 만들고 있는 코드로 표현할 새로운 정보 관리자가 필요합니다. 또한 거기 있는 **알고리즘들이 공공의 삶의 의미와 시민적 책임의 의미로 만들어진 것인지 확실히 할 필요**가 있습니다. 우리 **필터들을 통해서 결정하는 규칙들이 어떤 것인지 볼 수 있을만큼 충분히 투명한지 확실히 할 필요**가 있습니다. 여러분이 저희에게 약간의 제어권을 주면 무엇이 전달되고 무엇이 그렇지 않을지 결정할 수 있습니다. 저는 우리 모두가 꿈꾸는 것이 되는 인터넷이 정말 필요하다고 생각하기 때문입니다. 우리 모두를 연결하기 위해 그것이 필요합니다. 우리에게 새로운 아이디어와 새로운 사람들, 다른 시각들을 소개하기 위해 그것이 필요합니다. 웹에서 우리 모두가 개개인으로 따로 있다면 그렇게 되지 않을 것입니다.



