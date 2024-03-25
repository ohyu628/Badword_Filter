# Profanity_classification_model

#### Project Team :  "&"
#### Project Period : 2024.01.23 ~ 2024.01.26
![Alt text](image.png)

## Team
#### 지민철
* AWS로 서버환경 구축
* 크롤링 데이터, 데이터셋 하둡에 저장
#### 오유빈
* 데이터크롤링, 데이터셋 준비
* spark로 데이터 분석 및 전처리
#### 정모은 
* 데이터크롤링, 데이터셋 준비
* spark로 데이터 분석 및 전처리
#### 최재웅
* 데이터크롤링, 데이터셋 준비
* spark로 데이터 분석 및 전처리
#### 김수연
* 리뷰데이터셋으로 감정분석 모델 학습 및 구현
* 비속어 데이터셋으로 필터링 모델 학습 및 구현
#### 김수아
* Django로 게시판사이트 구현
## Stack

# 프로젝트 개요
- 목표: 
장고를 사용하여 웹 게시판을 구현하고, 비속어 필터링 및 감정 분석 모델을 통해 사용자 경험을 향상시키는 것.

- 배경: 
온라인 커뮤니티에서의 건전한 소통을 촉진하고, 사용자 간의 긍정적인 상호작용을 장려하기 위해 비속어 필터링과 감정 분석 기능이 필요함.

* 기대 효과:
    * 사용자들이 보다 책임감 있는 방식으로 소통할 수 있도록 유도
    * 긍정적이고 건전한 커뮤니티 문화 조성
    * 관리자가 커뮤니티 관리에 드는 시간과 노력 절감
# 요구사항 정의
## 기능 명세서
1. 회원가입 및 로그인

- 이메일 인증을 통한 사용자 가입
- 비밀번호 암호화 저장
2. 게시판 기능

- 게시글 작성, 조회, 수정, 삭제
- 댓글 작성, 조회, 수정, 삭제
- 카테고리별 게시글 분류
3. 비속어 필터링

- 게시글 및 댓글 작성 시 비속어 사전을 통한 필터링
- 검출된 비속어는 자동으로 가려짐 또는 경고 메시지와 함께 게시 거부
4. 감정 분석

- 게시글 및 댓글의 텍스트를 분석하여 긍정, 부정, 중립 등의 - 감정 상태 표시
- 사용자에게 피드백 제공 및 관리자에게 감정 분석 리포트 제공
5. 관리자 기능

- 비속어 사전 관리
- 사용자 관리 및 게시물 관리
- 감정 분석 리포트 조회

## 요구사항 정의서
1. 비속어 필터링 요구사항

- 비속어 사전은 관리자가 업데이트 가능해야 함
- 실시간으로 텍스트 검사가 이루어져야 함
- 비속어가 포함된 게시글 및 댓글은 게시 전에 사용자에게 경고 메시지 표시
2. 감정 분석 요구사항

- 텍스트 감정 분석을 위해 NLP 기술 사용
- 분석 결과는 긍정, 부정, 중립으로 분류
- 분석 결과를 사용자와 관리자에게 시각적으로 표시


#### Environment
- vscode

#### Development
* Python 3.11.5
* Django
* Bootstrap
* Hadoop (client, namenode(datanode1), secondnode(datanode2))
* AWS(ubuntu) EC2 (t2.small -> t2.xlarge) * 3
* Spark
* Jupyter Lab
* sqlite
#### Communication
- Slack
- Github

#### Daily
* 1일차
    * 비속어 데이터 크롤링
    * 일반 댓글 카테고리화 하여 크롤링
    * AWS환경 구축
    * Django로 백엔드 작업 시작
    * 비속어 모델 설계 시작
    * 감정분석 모델 설계 시작

* 2일차
    * hadoop에 데이터 적재
    * 학습을 위한 데이터 전처리(pandas, pyspark)
    * 모델 학습 시작

* 3일차 
    * 비속어 모델 성능 미달로 다른 방법으로 대체
    * 감정 분석 학습 데이터 늘려서 재학습
    * 비속어를 리스트화 해서 웹에 적용시도

* 4일차
    * 감정분석 모델 pth로 저장하여서 웹에 적용
    * 비속어 필터 웹에 적용
#### Data
- [Musinsa](https://www.musinsa.com/app/?utm_source=google_shopping&utm_medium=sh&source=GOSHSAP001&utm_source=google_shopping&utm_medium=sh&source=GOSHSAP001&gclid=CjwKCAiAzJOtBhALEiwAtwj8tqGiZ3KsEj28ahRoGruhkvSVOKQpIPV9G3QI3XlZUmggjbQA3HeBvRoCmUEQAvD_BwE)
- [일베 사이트 비속어 데이터](https://github.com/2runo/Curse-detection-data/blob/master/dataset.txt)
- [뉴스기사 댓글 비속어 데이터](https://github.com/kocohub/korean-hate-speech)
- [한국어 혐오표현 분류(탐지) 데이터셋](https://open.selectstar.ai/ko/?page_id=5948)
- [디시인사이트](https://gall.dcinside.com/board/lists/?id=leagueoflegends5)
- [네이버 식당리뷰](https://m.place.naver.com/restaurant/1085956231/review/visitor?entry=ple&reviewSort=recent)
- [fmkorea](https://www.fmkorea.com/fm24free)

## Model
### 비속어 필터링 모델 (KcELECTRA 모델)
#### 온라인 뉴스와 댓글과 대댓글을 수집해, 토크나이저와 ELECTRA 모델을 처음부터 학습한 Pre-trained ELECTRA 모델

:speech_balloon:구어체의 댓글과 같이 잘 정제되어있지 않고 신조어와 오탈자가 많은 데이터 셋을 학습하는데 적합하다고 선택했다. RTD는 GAN에서 사용된 Generator, Discriminator 두 가지 모델을 활용해 학습하는 방식이다.
:speech_balloon:AutoModelForSequenceClassification 을 통해 쉽게 사전학습모델을 불러왔다. 
![Alt text](image(4).png)
![Alt text](image(5).png)
### 감정 분석 모델(Hugging Face BERT)
#### 구글이 개발한 사전훈련한(pre-training) 모델
![Alt text](image(3).png)

:speech_balloon:data에서 label이 0이면 부정, 1이면 긍정으로 분류

:bulb:BERT의 입력은 그림과 같은데, 문자열의 앞 뒤에 CLS, SEP이 있다.

:sparkles:[CLS] :arrow_right: Classification을 뜻함, 그래서 제일 앞에 삽입

:star2:파인튜닝시 출력에서 이 위치의 값을 사용하여 분류

:sparkles:[SEP] :arrow_right: Seperation, 두 문장을 구분하는 역할

![Alt text](image(1).png)
:speech_balloon:BERT는 형태소분석으로 토큰을 분리하지 않는다.WordPiece라는 통계적인 방식을 사용한다. 한 단어 내에서 자주 나오는 글자들을 붙여서 하나의 토큰으로 만든다. 이렇게 하면 언어에 상관없이 토큰을 생성할 수 있다는 장점이 있다. 또한 신조어 같이 사전에 없는 단어를 처리하기도 좋다.

:heavy_plus_sign:보통 딥러닝 모델에는 토큰 자체를 입력으로 넣을 수 없다. 그래서 임베딩 레이어에 토큰을 숫자로 된 인덱스로 변환하여 사용했다.
BERT의 토크나이저는 {단어토큰:인덱스}로 구성된 단어사전을 가지고 있기에 토큰을 인덱스로 바꿔줬다.

![Alt text](image(2).png)
:arrow_right:사전훈련된 BERT는 다양한 문제로 전이학습이 가능하다.

:bulb:그림과 같이 한 문장을 분류하는 방법을 사용했다. 문장이 입력으로 들어가면, 긍정/부정으로 구분한다. 모델의 출력에서 [CLS] 위치인 첫 번째 토큰에 새로운 레이어를 붙여서 파인튜닝을 했다. Huggning Face는 BertForSequenceClassification() 함수를 제공하기 때문에 쉽게 구현이 가능했다.

## Source
