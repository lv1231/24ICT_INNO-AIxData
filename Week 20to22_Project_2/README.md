# [ ICT-INNO ]

> [!NOTE]  
> 'ICT 부트캠프' 최종 프로젝트와 관련된 레포지토리이다. "IT 기업 취업 준비생을 위한 면접 보조 서비스"를 기획 및 구현이 최종 목적이다.

|기본 UI|결과 UI|
|---|---|
|![app](https://github.com/user-attachments/assets/b01e3c32-04d0-43ae-9443-a2379da3fa8b)|![app_result](https://github.com/user-attachments/assets/558b2b75-6d23-4fc4-90ff-a3e2d812108f)|


## 프로젝트 개요
목적: IT 기업 취업을 준비하는 구직자들에게 면접 대비를 위한 보조 서비스를 제공합니다. 음성 데이터를 분석하여 면접 답변에 대한 피드백을 제공하고, 전문 분야에 대한 심층적인 질문과 답변을 연습할 수 있는 플랫폼을 구축합니다.

## 주요 기능
1. 음성 인식 및 분석
- 사용자가 면접 질문에 대한 답변을 음성으로 녹음하여 업로드하면, 이를 텍스트로 변환하고 분석한다.
- **자연어 처리(NLP)**를 통해 답변의 내용, 키워드, 문장 구조 등을 분석하여 피드백 제공한다.

2. 피드백 제공
- 답변의 적합성, 전문성, 논리성 등에 대한 평가를 제공한다.
- 개선이 필요한 부분과 모범 답안을 제시한다.

3. 질문 데이터베이스
- IT 분야 면접에서 자주 나오는 질문들을 카테고리별로 제공하고, 사용자 맞춤형 질문을 추천한다.

4. 사용자 프로필 및 학습 이력 관리
- 사용자별로 학습 이력, 강점 및 약점을 관리하여 개인화된 학습 계획을 제공한다.

5. 실시간 모의 면접
- 챗봇이나 AI 면접관을 통해 실시간으로 모의 면접을 진행할 수 있다.


## 시스템 아키텍처
```
project_root/
├── app/                      # Flask 백엔드 애플리케이션 디렉토리
│   ├── __init__.py           # Flask 앱 초기화 및 설정
│   ├── routes.py             # 라우트 및 뷰 함수 정의
│   ├── models.py             # 데이터베이스 모델 정의
│   ├── utils.py              # 유틸리티 함수들
│   ├── speech_processing/    # 음성 처리 모듈
│   │   ├── __init__.py
│   │   ├── speech_to_text.py # 음성을 텍스트로 변환하는 모듈
│   │   └── nlp_analysis.py   # NLP 분석 모듈
│   ├── templates/            # Jinja2 템플릿 파일들
│   │   ├── index.html
│   │   ├── result.html
│   │   └── ...
│   └── static/               # 정적 파일들 (CSS, JS, 이미지 등)
│       ├── css/
│       │   └── styles.css
│       ├── js/
│       │   └── scripts.js
│       └── images/
│           └── logo.png
├── frontend/                 # Flet 기반 프론트엔드 애플리케이션 디렉토리
│   ├── main.py               # Flet 애플리케이션의 진입점
│   ├── components/           # 재사용 가능한 UI 컴포넌트들
│   │   ├── __init__.py
│   │   ├── file_uploader.py
│   │   └── feedback_display.py
│   └── assets/               # 프론트엔드에서 사용하는 정적 자산
│       ├── images/
│       │   └── icon.png
│       └── ...
├── data/                     # 데이터 파일 저장 디렉토리
│   ├── uploads/              # 업로드된 음성 파일들
│   └── processed/            # 처리된 데이터 파일들
├── config.py                 # 설정 파일 (MongoDB URI 등)
├── requirements.txt          # 필요한 패키지 목록
├── run.py                    # 애플리케이션 실행 스크립트
├── README.md                 # 프로젝트 설명 문서
├── .gitignore                # Git에서 제외할 파일 목록
```