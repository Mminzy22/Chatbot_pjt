<details>
<summary><strong>MVP 구현</strong></summary>

# AI 기반 대화형 챗봇 프로젝트 💬

## 1. 프로젝트 개요
AI 기반 **대화형 챗봇**을 개발하는 프로젝트입니다.  
LangChain과 Pinecone을 활용한 **RAG(Retrieval-Augmented Generation)** 모델을 기반으로,  
주어진 문서를 참고하여 **면접 질문을 생성하고 답변을 평가**하는 기능을 제공합니다.

## 사용 기술
- **백엔드:** Python, Streamlit  
- **LLM:** OpenAI GPT-4o Mini  
- **벡터 데이터베이스:** Pinecone  
- **DB:** PostgreSQL (Neon)  
- **인프라:** Streamlit Cloud (배포), GitHub Actions (CI)  
- **테스트:** Pytest  

---

## 2. 배포
👉 **[배포 URL](https://chatbotpjt-udbkrmgy8v64nxax3baeae.streamlit.app/)**

---

## 3. 팀원 구성

- 팀장 : 신제창  
- 팀원 : 이현지, 박종관, 박민지

### - 역할 분담  
- Chatbot 모델 - 신제창  
- 웹-Streamlit - 이현지  
- RDB, 벡터DB - 박민지, 박종관  

---

## 4. 주요 기능

### - 면접 질문 생성  
- Pinecone에 저장된 문서를 바탕으로 GPT-4o Mini가 적절한 면접 질문을 생성  

### - 답변 평가  
- 사용자가 입력한 답변을 LangChain RAG 기반으로 평가  
- 참고 문서와 비교하여 **피드백 및 모범 답안 제공**

### - 채팅 내역 저장  
- 사용자별 채팅 세션을 생성하고 데이터베이스에 저장  
- PostgreSQL을 활용하여 채팅 내역 조회 가능  

---

## 5. 프로젝트 구조

```bash
📦 Chatbot_pjt/
│
│── main.py
│
│── 📂 pages/
│   │── home.py
│   │── chat.py
│   └── history.py
│
│── 📂 data/
│   └── referance.docx
│
│── 📂 backend/
│   │── db.py
│   │── accounts.py
│   │── config.py
│   │── langchain_chatbot.py
│   │── pinecone_db.py
│   └── utils.py
│
│── 📂 tests/
│   │── init.py
│   │── test_accounts.py
│   │── test_db.py
│   │── langchain_chatbot.py
│   └── test_pinecone_db.py
│
│── 📂 .streamlit/
│   └── secrets.toml
│
│── requirements.txt
│── venv
│── .env
│── .gitignore
└── README.md
```

---

## 6. 환경 변수 설정

### - 스트림릿 클라우드 배포 환경 변수

`.streamlit/secrets.toml` 파일을 사용합니다.

```toml
[openai]
OPENAI_API_KEY = "your-openai-api-key"
...
```

**⚠️ 중요:**  
Streamlit에서는 `st.secrets`로 값을 불러옵니다.

---

### - 로컬 테스트 환경 변수

`.env` 파일을 사용합니다.

```env
OPENAI_API_KEY=your-openai-api-key
...
```

`.env` 파일은 `python-dotenv`를 사용하여 로드해야 합니다.

---

## ▶️ 로컬 실행 방법

```bash
python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate      # Windows

pip install -r requirements.txt
streamlit run main.py
```

---

## ▶️ 테스트 실행 방법

```bash
pytest tests/
```

---

## 7. GitHub Actions CI 설정

GitHub Actions를 통해 CI를 자동화하며,  
`.github/workflows/ci.yml` 파일에 워크플로우가 정의되어 있습니다.

---

## 8. 참고 사항

- Streamlit Cloud는 `main` 브랜치가 업데이트될 때 자동으로 반영됩니다.

</details>

# 개발 역량 강화를 위한 맞춤형 AI 챗봇 💬
