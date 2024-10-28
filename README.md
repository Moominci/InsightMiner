# InsightMiner

**InsightMiner**는 네이버 카페 게시글을 크롤링하여 특정 키워드에 대한 데이터를 수집하고, 데이터를 정리하여 Excel 파일로 저장하는 크롤링 툴입니다. Slack 연동 기능을 통해 실시간 업데이트된 크롤링 결과를 손쉽게 공유할 수 있습니다. 

## 🧭 기능 개요

InsightMiner는 여러 키워드를 탐색하고, 각 키워드에 해당하는 네이버 카페 게시글을 수집하여 정리합니다. 이를 통해 특정 주제나 키워드에 대한 인사이트를 얻을 수 있도록 돕습니다. 이 크롤러는 Selenium 웹 드라이버와 Slack API 연동을 통해 데이터를 처리합니다.

## ⚙️ 주요 기능

- **다중 키워드 크롤링**: 키워드별로 구분된 네이버 카페 게시글 데이터를 수집
- **데이터 전처리**: 불필요한 텍스트를 제거, Excel 파일에 정리된 형태로 저장
- **Slack 자동 업로드**: 크롤링 결과를 실시간으로 Excel 파일로 생성하여 Slack에 업로드
- **자동 로그인 및 안정적인 네트워크 처리**: Selenium의 자동화를 통해 로그인 및 페이지 전환을 수행하며, 페이지 로드 시간을 최적화하여 안정성을 보장

## 📁 설치 및 실행

### 요구 사항

- Python 3.7 이상
- 필요 라이브러리 설치: Selenium, Pandas, Webdriver Manager

```bash
pip install selenium pandas webdriver-manager
```
#### 프로젝트 클론
```bash
git clone https://github.com/yourusername/InsightMiner.git
cd InsightMiner
```

#### 🖥️ 코드 구조
- **InsightMiner.py**: 메인 크롤링 스크립트
- **slack_file_upload.py**: Slack에 파일을 업로드하는 유틸리티 모듈
- **file_date.py**: 날짜 형식을 관리하는 모듈로, 원하는 날짜 형식에 맞춘 정보를 제공

#### 주요 함수 설명
- **login()**: 네이버 계정으로 자동 로그인 (계정 정보 입력 필요)
- **clean_article(list_len)**: 게시글의 불필요한 텍스트를 제거
- **keyword_search(keyword)**: 각 키워드별로 검색 조건을 구성하고, 데이터를 수집
- **collect_articles(articles_link)**: 게시글을 수집하고, 제목과 본문을 추출하여 정리
- **main()**: 크롤링을 실행하고 데이터를 최종 저장 및 Slack 업로드

#### 📊 데이터 포맷
InsightMiner는 수집된 데이터를 다음과 같은 포맷으로 정리하여 Excel 파일로 저장합니다:

게시글 번호	게시글 제목	작성자	작성시간/조회수	게시글 내용
1	카페 추천 게시글	user1234	2023-01-01	이 카페 추천합니다.

#### 🚀 향후 개선 사항
- 추가 사이트 연동: 네이버 이외의 추가적인 플랫폼 크롤링
- 데이터베이스 연동: 수집 데이터를 DB에 저장하여 지속적인 데이터 관리 및 분석
- 자동화 스케줄링: 주기적인 데이터 수집을 위한 스케줄러(예: cron)

#### 🛠️ 문제 해결
크롤링 중 에러 발생 시, Selenium Webdriver 옵션을 조정하거나, Slack 업로드 관련 설정을 확인

