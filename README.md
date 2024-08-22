# 팀앤드(&)
> Encore Dataengineering 28기 부트캠프 mini project

# Team
|지민철|오유빈|정모은|최재웅|김수연|김수아|
|-----|-----|-----|-----|-----|-----|
|데이터 엔지니어(팀장)|데이터 엔지니어|데이터 분석|데이터 분석|모델|백엔드|

# Use Tech

#### Environment
<img src="https://img.shields.io/badge/vscode-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white">

#### Development
<img src="https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white"> <img src="https://img.shields.io/badge/django-092E20?style=for-the-badge&logo=django&logoColor=white"> <img src="https://img.shields.io/badge/bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white"> <img src="https://img.shields.io/badge/apachehadoop-66CCFF?style=for-the-badge&logo=apachehadoop&logoColor=black"> <img src="https://img.shields.io/badge/amazonec2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white"> <img src="https://img.shields.io/badge/apachespark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white"> <img src="https://img.shields.io/badge/sqlite-003B57?style=for-the-badge&logo=sqlite&logoColor=white">

### Communication
<!-- <div align=center> -->
<img src="https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white"> <img src="https://img.shields.io/badge/slack-4A154B?style=for-the-badge&logo=slack&logoColor=white">
<!-- </div> -->

# 전체 프로젝트 일정
* 프로젝트 일정 : 2024.01.23 ~ 2024.01.26

# 목차
* [프로젝트 개요](#프로젝트-개요)
* [기능명세서](#기능-명세서)
* [요구사항정의서](#요구사항-정의서)
* [WBS](#wbs)
* [Hadoop 환경구축](#hadoop-환경구축)
* [Spark 환경구축](#spark-환경구축)
* [Model 서빙](#model-서빙)
* [전체적인 아키텍처](#전체적인-아키텍처)
* [회고](#회고)
* [출처사이트](#출처-사이트)

# 프로젝트 개요
![Alt text](image.png)
* 목표
    * 장고를 사용하여 웹 게시판을 구현하고, 비속어 필터링 및 감정 분석 모델을 통해 사용자 경험을 향상시키는 것.

* 배경: 
    * 온라인 커뮤니티에서의 건전한 소통을 촉진하고, 사용자 간의 긍정적인 상호작용을 장려하기 위해 비속어 필터링과 감정 분석 기능이 필요함.

* 기대 효과:
    * 사용자들이 보다 책임감 있는 방식으로 소통할 수 있도록 유도
    * 긍정적이고 건전한 커뮤니티 문화 조성
    * 관리자가 커뮤니티 관리에 드는 시간과 노력 절감

## 기능 명세서
* 회원가입 및 로그인
    * 이메일 인증을 통한 사용자 가입
    * 비밀번호 암호화 저장
* 게시판 기능
    * 게시글 작성, 조회, 수정, 삭제
    * 댓글 작성, 조회, 수정, 삭제
    * 카테고리별 게시글 분류
* 비속어 필터링
    * 게시글 및 댓글 작성 시 비속어 사전을 통한 필터링
    * 검출된 비속어는 자동으로 가려짐 또는 경고 메시지와 함께 게시 거부
* 감정 분석
    * 게시글 및 댓글의 텍스트를 분석하여 긍정, 부정, 중립 등의 - 감정 상태 표시
    * 사용자에게 피드백 제공 및 관리자에게 감정 분석 리포트 제공
* 관리자 기능
    * 비속어 사전 관리
    * 사용자 관리 및 게시물 관리
    * 감정 분석 리포트 조회

## 요구사항 정의서
* 비속어 필터링 요구사항
    * 비속어 사전은 관리자가 업데이트 가능해야 함
    * 실시간으로 텍스트 검사가 이루어져야 함
    * 비속어가 포함된 게시글 및 댓글은 게시 전에 사용자에게 경고 메시지 표시
* 감정 분석 요구사항
    * 텍스트 감정 분석을 위해 NLP 기술 사용
    * 분석 결과는 긍정, 부정, 중립으로 분류
    * 분석 결과를 사용자와 관리자에게 시각적으로 표시
## WBS
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
## Hadoop 환경구축
## Spark 환경구축
## Model 서빙
## 전체적인 아키텍처
## 회고
## 출처 사이트
- [Musinsa](https://www.musinsa.com/app/?utm_source=google_shopping&utm_medium=sh&source=GOSHSAP001&utm_source=google_shopping&utm_medium=sh&source=GOSHSAP001&gclid=CjwKCAiAzJOtBhALEiwAtwj8tqGiZ3KsEj28ahRoGruhkvSVOKQpIPV9G3QI3XlZUmggjbQA3HeBvRoCmUEQAvD_BwE)
- [일베 사이트 비속어 데이터](https://github.com/2runo/Curse-detection-data/blob/master/dataset.txt)
- [뉴스기사 댓글 비속어 데이터](https://github.com/kocohub/korean-hate-speech)
- [한국어 혐오표현 분류(탐지) 데이터셋](https://open.selectstar.ai/ko/?page_id=5948)
- [디시인사이트](https://gall.dcinside.com/board/lists/?id=leagueoflegends5)
- [네이버 식당리뷰](https://m.place.naver.com/restaurant/1085956231/review/visitor?entry=ple&reviewSort=recent)
- [fmkorea](https://www.fmkorea.com/fm24free)


