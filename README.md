# 📘 TechReader

TechLibrary 사이트에 등재된 AI 최신 동향 데이터를 다룬 문서 기반 RAG 시스템으로, <br>
기술 보고서(PDF)를 업로드하면 문서 구조(목차·소제목)를 기반으로 섹션별 예상 질문·답변(Q&A)을 자동 생성해줍니다. <br> <br> 
<img width="1192" height="635" alt="image" src="https://github.com/user-attachments/assets/cdeddc85-ddc0-41df-9a34-4e3081c1748d" />


# 🔎 프로젝트 개요
* 프로젝트명 : 테크리더 (TechReader) 
* 수행 기간 : 2025.09.04-2025.09.05 
* 사용 목적 : 방대한 기술 보고서를 빠르게 이해하고, 목차 기반 Q&A를 통해 효율적이고 최신 정보를 빠르게 습득

<img width="1320" height="722" alt="image" src="https://github.com/user-attachments/assets/f5938762-089b-4e42-a178-f02cf2d512b2" />


# 🚨 문제 정의

* 기술 보고서는 수십~수백 페이지로 방대하여, 핵심 내용을 빠르게 정리하기 어렵습니다.
* 기존 RAG 방식은 단순 chunk 검색만 제공해 문서의 구조적 맥락을 반영하지 못합니다.
* 단순 요약은 학습·실무·인터뷰 대비에 충분하지 않으며, 구체적 질문 응답이 필요합니다. 

<img width="1172" height="603" alt="image" src="https://github.com/user-attachments/assets/f491ca8f-c792-42f5-884d-a98492414375" />


# 🙌 필요성 및 기대효과 

📑 효율적 학습 지원: 방대한 문서에서도 핵심 Q&A를 빠르게 확보
🤖 자동 질의응답 제공: 단순 요약을 넘어 실제 활용 가능한 질문·답변 생성
🎯 실전 면접 대비: 예상 질문 세트를 통해 인터뷰 준비 시간 단축
🚀 지식 재사용 강화: 문서 지식을 구조화하여 다양한 활용 가능 

<img width="1173" height="613" alt="image" src="https://github.com/user-attachments/assets/d0231380-b747-4dab-9a00-8bec792d4010" />


# 📂 데이터 및 워크플로우
### 입력 데이터  
- 테크너리라이브러리 산업 기술 보고서 PDF (예: Tech Guide, Tech Trend)  
- 데이터의 문제점 : 목차 정보 부재 
<img width="1330" height="695" alt="image" src="https://github.com/user-attachments/assets/37aa057e-dded-4586-9061-c49c4cafbe72" />


### 처리 과정  
1. **PDF 업로드 & 변환** → LlamaParse로 Markdown 구조화  
2. **문서 구조 인식** → MarkdownHeaderSplitter로 제목·소제목 추출  
3. **Chunking & 임베딩** → OpenAI Embeddings + FAISS Vector Store  
4. **질의응답 생성** → GPT 모델을 활용하여 예상 질문·답변 생성  
5. **출력 제공** → 목차별 Q&A 형식으로 사용자에게 결과 제공

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


📊 전체 구조 요약 


# 🛠 기술 스택

* Parsing: LlamaParse
* Framework: LangChain
* Embedding: OpenAI Embeddings
* Vector DB: FAISS
* LLM: OpenAI GPT API, Gemini 2.5 pro API 
* UI: Gradio
