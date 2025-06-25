# vibeCoding 2-2

FastAPI + Streamlit + LangGraph Agent를 활용한 챗봇 프로젝트

## 🚀 프로젝트 개요

이 프로젝트는 **Clean Architecture** 패턴을 적용하여 구축된 AI 챗봇 시스템입니다. 사용자가 상품 검색을 요청하면 LangGraph Agent가 웹 검색을 수행하고 결과를 제공합니다.

## 🏗️ 아키텍처

### 기술 스택
- **Backend**: FastAPI (Python 3.11)
- **Frontend**: Streamlit  
- **AI Agent**: LangGraph with Gemini-2.5-flash-preview-05-20
- **Search Tool**: DuckDuckGo Search
- **Architecture**: Clean Architecture + SOLID 원칙

### 폴더 구조
```
vibe_coding_w2-1/
├── backend/                    # FastAPI 백엔드
│   ├── app/
│   │   ├── api/               # API Layer (Presentation)
│   │   ├── services/          # Service Layer
│   │   └── agents/            # Agent Layer (AI Processing)
│   ├── tests/                 # 테스트 코드
│   └── requirements.txt
├── frontend/                   # Streamlit 프론트엔드
├── docs/                      # 문서
├── .github/                   # GitHub Actions & Templates
└── .cursor/rules/             # Cursor Rules
```

## 🔧 설치 및 실행

### 환경 설정
```bash
# 가상환경 생성 및 활성화
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 백엔드 의존성 설치
cd backend
pip install -r requirements.txt

# 프론트엔드 의존성 설치  
cd ../frontend
pip install -r requirements.txt
```

### 환경 변수 설정
```bash
# .env 파일 생성
GEMINI_API_KEY=your_gemini_api_key
LANGSMITH_API_KEY=your_langsmith_api_key  # (선택사항)
```

### 실행
```bash
# 백엔드 서버 실행
cd backend
uvicorn app.main:app --reload

# 프론트엔드 실행 (새 터미널)
cd frontend
streamlit run app.py
```

## 🧪 테스트

### TDD 개발 프로세스
1. 테스트 코드 작성
2. 구현 코딩
3. 테스트 실행 및 수정 반복

### 테스트 실행
```bash
cd backend
pytest tests/ -v --cov=app
```

## 📋 개발 태스크

| Task ID | 제목 | 상태 | 우선순위 |
|---------|------|------|----------|
| TASK-001 | 프로젝트 구조 및 환경 설정 | ✅ | High |
| TASK-002 | FastAPI 백엔드 기본 구조 구현 | 🚧 | High |
| TASK-003 | LangGraph Agent 구현 | ⏳ | High |
| TASK-004 | Streamlit 프론트엔드 구현 | ⏳ | High |

## 🤖 AI Agent 동작 방식

1. **사용자 입력**: 상품 검색 요청
2. **Agent 처리**: LangGraph React Agent가 요청 분석
3. **웹 검색**: DuckDuckGo Tool을 사용하여 검색 수행
4. **결과 생성**: Gemini LLM이 검색 결과를 분석하고 응답 생성
5. **응답 반환**: 구조화된 상품 정보 제공

## 🔄 GitHub 자동화

### GitHub Actions
- ✅ 자동 테스트 실행 (Push/PR)
- ✅ PR 자동 댓글, 할당, 라벨링
- ✅ Issue 자동 관리
- ✅ 자동 코드 리뷰

### 브랜치 전략
- `main`: 메인 브랜치
- `feature/TASK-XXX-description`: 새 기능
- `bugfix/TASK-XXX-description`: 버그 수정
- `hotfix/TASK-XXX-description`: 긴급 수정

## 📝 개발 원칙

### Clean Architecture
- **Domain Layer**: 비즈니스 로직 및 엔티티
- **Application Layer**: Use Cases
- **Infrastructure Layer**: 외부 시스템 연동
- **Presentation Layer**: API 엔드포인트

### SOLID 원칙
- **S**ingle Responsibility Principle
- **O**pen/Closed Principle  
- **L**iskov Substitution Principle
- **I**nterface Segregation Principle
- **D**ependency Inversion Principle

## 📚 문서

- [UX 와이어프레임](docs/ux-wireframes.md)
- [API 명세서](docs/api-specification.md)
- [시스템 아키텍처](docs/system-architecture.md)

## 🤝 기여하기

1. 이슈 생성 또는 기존 이슈 할당받기
2. 브랜치 생성: `feature/TASK-XXX-description`
3. TDD 방식으로 개발
4. PR 생성 (템플릿 사용)
5. 코드 리뷰 및 머지

## 📄 라이선스

이 프로젝트는 MIT 라이선스를 따릅니다.

---

**개발 문의**: [Issues](https://github.com/jibongPark/vibeCoding-2-2/issues)를 통해 문의해주세요! 