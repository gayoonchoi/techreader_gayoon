# 📘 TechReader

기술 보고서(PDF)를 업로드하면 문서 구조(목차·소제목)를 기반으로 섹션별 예상 질문·답변(Q&A)을 자동으로 생성하는 RAG(Retrieval-Augmented Generation) 기반 문서 분석 시스템입니다.
<img width="1364" height="723" alt="image" src="https://github.com/user-attachments/assets/a210fb6b-7250-4abb-9476-b7b2d38d27ad" />


# 🔎 프로젝트 개요

TechReader는 방대한 산업 기술 보고서를 빠르게 이해할 수 있도록 돕는 AI 도구입니다.

단순 요약이 아닌 질의응답 포맷(Q&A)을 제공하여 학습·연구·인터뷰 대비에 활용할 수 있습니다.

문서의 목차와 소제목을 반영한 RAG 파이프라인으로 맥락을 보존한 질문 응답을 제공합니다.

<img width="1320" height="722" alt="image" src="https://github.com/user-attachments/assets/f5938762-089b-4e42-a178-f02cf2d512b2" />


# 🚨 문제 정의

기술 보고서는 수십~수백 페이지로 방대하여, 핵심 내용을 빠르게 정리하기 어렵습니다.

기존 RAG 방식은 단순 chunk 검색만 제공해 문서의 구조적 맥락을 반영하지 못합니다.

단순 요약은 학습·실무·인터뷰 대비에 충분하지 않으며, 구체적 질문 응답이 필요합니다. 

<img width="1174" height="620" alt="image" src="https://github.com/user-attachments/assets/f58483c7-681d-4166-a028-0efe60f88dc5" />


# 🙌 필요성 및 기대효과

📑 효율적 학습 지원: 방대한 문서에서도 핵심 Q&A를 빠르게 확보

🤖 자동 질의응답 제공: 단순 요약을 넘어 실제 활용 가능한 질문·답변 생성

🎯 실전 면접 대비: 예상 질문 세트를 통해 인터뷰 준비 시간 단축

🚀 지식 재사용 강화: 문서 지식을 구조화하여 다양한 활용 가능 

<img width="1164" height="626" alt="image" src="https://github.com/user-attachments/assets/2cab6fd1-cca2-4ea7-a02e-addc14a8dac3" />


# 💡 선택 동기

RAG 파이프라인은 많이 연구되었지만, 사용자 친화적 학습 도구로 확장된 사례는 부족합니다.

개인적으로 기술 보고서를 학습하고 면접에 대비할 수 있는 맞춤형 Q&A 도구의 필요성을 느껴 프로젝트를 기획했습니다.

최신 기술 스택(LlamaParse, OpenAI API, LangChain, FAISS)을 직접 적용해보고, 실제 활용 가능한 파이프라인을 구현하고자 했습니다.

# 📂 데이터 및 워크플로우
입력 데이터

산업 기술 보고서 PDF (예: Tech Guide, Tech Trend)

처리 과정

PDF 업로드 & 변환 → LlamaParse로 Markdown 구조화

문서 구조 인식 → MarkdownHeaderSplitter로 제목·소제목 추출

Chunking & 임베딩 → OpenAI Embeddings + FAISS Vector Store

질의응답 생성 → GPT 모델을 활용하여 예상 질문·답변 생성

출력 제공 → 목차별 Q&A 형식으로 사용자에게 결과 제공

# ⚙️ 시스템 아키텍처

PDF 문서
   │
   ▼
[LlamaParse] → Markdown 변환
   │
   ▼
[Header Splitter] → 소제목 단위 분리
   │
   ▼
[Embedding + Vector DB] → FAISS 저장
   │
   ▼
[RAG + GPT 모델] → Q&A 생성
   │
   ▼
[UI] → 사용자 확인


# 🛠 기술 스택

Parsing: LlamaParse

Framework: LangChain

Embedding: OpenAI Embeddings

Vector DB: FAISS

LLM: OpenAI GPT API

UI: Streamlit / Gradio
