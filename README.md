# 킥스타터 펀딩 성공의 핵심요소 분석



## Goal : 

킥스타터 펀딩을 성공시키지 위해 어떤 요소들을 중점적으로 고려하여야할지 탐색



## 세부내용

- 주제선정동기

1. 신제품 출시의 초기비용부담
2. 효과적 마케팅 수단
3. 출시전, 판매데이터 수집가능 장점



- 가설 6가지

1. 목표금액이 적을수록 성공율은 높아질 것이다.
2. 후원자수가 높을수록 성공율은 높아질 것이다.
3. 펀딩기간이 짧을수록 성공율은 높아질 것이다.
4. 진행국가는 성공율에 영향을 주지 않을 것이다.
5. 화폐종류는 성공율에 영향을 주지 않을 것이다.
6. 주요분야는 성공율에 영향을 줄 것이다.



- 데이터 전처리


1. 프로젝트 진행기간 변수 추가

"deadline"  - "launched" = "period“   
“모금진행기간” 으로 치환


2. 검증에 불필요한 변수 제거

"ID"  :  중복데이터가 적어 삭제
"category" (소분류) 제거  :  "main_category" (대분류) 사용
"usd pledged", "goal", "pledged"  :  통일된 화폐단위 USD로


3. 결측치, 이상치 처리


4. 변수별 특성 확인

인기가 많은 펀딩은 시작과 동시에 마감 => 유의미
이상치 제거 후, 모델분석결과 정확도 0.98로 과적합
=> 계수를 올려, 양극단값 이상치 5% 정도 제거




## 결과물 :

EDA 인사이트

1. 가설에서 제시한 6가지 변수는 모두 상관관계가
    있는 것으로 추정    

2. 성공율을 높이려면 목표금액, 펀딩기간은 적게,
    후원자수는 많이 모으는 것이 유리할 것으로 추정

3. 예상외로 화폐종류와 진행국가가 성공률과 관계가
    있는 것으로 보임

4. 주요분야 분석에서 성공율 상위 펀딩은 모두 무형 컨텐츠
    
    => 무형은 비용이 적고 실물제품은 비용이 커, 
        목표금액 등의 변수 차이가 있을 것으로 추정

5. 결측치 제거 전/후로 결과값들의 변화가 큰 경우가
    다수 발생

    => 영향이 없을 것 같던, 프로젝트명에서도 변화 발견



한계점

1. 외부요인 변수
    ( ex : 브랜드, 광고 노출, 댓글 수)

2. 컨텐츠 품질요소 변수 
    ( ex : 텍스트, 영상, 이미지)

3. 나라별 문화요소 변수
    ( ex: 미국 / 그 외로 이원화)



