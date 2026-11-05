# Chapter 07 — Generative AI & Large Language Models

**Project:** Artificial Intelligence (AI) — Deep Research & Study Notes  
**Owner / Content Creator:** Sandeep Barupal  
**Copyright:** © 2026 Sandeep Barupal. Original explanatory notes; third-party names and trademarks belong to their respective owners.

## 1. Generative AI kya hai?

Generative AI aisi AI technology hai jo prompt ya input ke basis par naya content create kar sakti hai. Output text, image, audio, video, code ya inka combination ho sakta hai.

Predictive AI ka common task existing data ke basis par class ya value predict karna hai; Generative AI ka common task content generate karna hai. Dono ke peeche machine learning techniques ho sakti hain.

## 2. LLM kya hota hai?

LLM ka full form Large Language Model hai. Ye large text datasets se language patterns learn karne wala model hota hai. Iska use question answering, summarization, translation, drafting aur code assistance jaise tasks mein hota hai.

GPT, Gemini, Claude, Llama aur Qwen jaise naam model families/products ko refer karte hain. Ye independent educational notes hain; third-party names aur trademarks unke owners ke hain.

## 3. LLM ka basic workflow

1. User prompt submit karta hai.
2. Text tokenizer ke through tokens mein convert hota hai.
3. Tokens numerical embeddings mein convert hote hain.
4. Model context aur token relationships process karta hai.
5. Model next token ke scores calculate karta hai.
6. Decoding strategy next token select karti hai.
7. Process repeat hota hai jab tak response complete ya stop na ho.

## 4. Tokens and tokenization

Token text ka chhota unit hota hai. Token ek word, word ka part, punctuation ya special token ho sakta hai. Exact split tokenizer aur language par depend karta hai.

Tokenization text ko tokens mein divide karne ki process hai. Modern language models mein subword ya byte-level tokenization approaches common hain.

Tokens context limits, processing aur API billing ko affect kar sakte hain.

## 5. Embeddings

Embedding text, image ya doosre data ko numerical vector ke form mein represent karta hai. Similar meaning wale text ke vectors embedding space mein relatively close ho sakte hain, depending on the model.

Uses:
- Semantic search.
- Document retrieval.
- Similarity matching.
- Recommendations.
- RAG systems.

Illustrative vectors (actual values nahi):
- "Apple fruit" → [0.12, 0.45, 0.88]
- "Orange fruit" → [0.14, 0.43, 0.81]
- "Car engine" → [0.92, 0.18, 0.31]

## 6. Transformer architecture

Modern LLMs mein Transformer architecture widely used hai.

Important parts:
- **Embeddings:** Tokens ko vectors mein map karte hain.
- **Positional information:** Sequence/order ka signal provide karta hai.
- **Self-attention:** Sequence ke tokens ke beech relationships process karta hai.
- **Feed-forward layers:** Representations ko transform karti hain.
- **Output layer:** Next-token scores produce karti hai.

Self-attention sentence ke context mein words ke relationships model karne mein help karta hai. Transformer ka har implementation exactly same nahi hota; encoder-only, decoder-only aur encoder-decoder designs milte hain.

## 7. Pretraining

Pretraining mein model large training corpus se general patterns learn karta hai. Autoregressive language models mein common objective next-token prediction hota hai.

Training ke dauran model predictions aur target tokens ke difference ke basis par parameters update karta hai. Data selection, filtering, licensing, quality aur safety training outcomes ko affect karte hain.

## 8. Fine-tuning

Fine-tuning mein pretrained model ko specific task, behaviour ya domain ke examples par further train kiya jata hai.

Common approaches:
- Supervised Fine-Tuning (SFT).
- Instruction Fine-Tuning.
- Parameter-Efficient Fine-Tuning (PEFT).
- LoRA (Low-Rank Adaptation).

Fine-tuning model parameters ko adapt karti hai. Frequently changing company facts ke liye RAG ya other data retrieval approach zyada suitable ho sakti hai.

## 9. Prompt Engineering

Prompt Engineering ka matlab instructions, task, context aur output format ko clearly define karna hai.

Useful prompt components:
1. Role or perspective.
2. Clear task.
3. Relevant context.
4. Desired output format.
5. Constraints and success criteria.

Example:

```text
Task: Explain AI to a beginner.
Language: Easy Hindi (Hinglish).
Include: Definition, 3 examples and limitations.
Format: Headings and numbered steps.
Avoid: Unexplained technical jargon.
```

Common techniques:
- Zero-shot: Example ke bina instruction.
- One-shot: Ek example.
- Few-shot: Multiple examples.
- Role prompting: Desired perspective define karna.
- Structured prompting: Output format specify karna.

Prompting output improve kar sakti hai, lekin factual correctness guarantee nahi karti.

## 10. Context window

Context window model ek request ke dauran kitne tokens process kar sakta hai, uski limit hoti hai. Ismein instructions, conversation, supplied documents aur output ke tokens count ho sakte hain; exact accounting model/platform par depend karti hai.

Context window aur persistent memory same cheez nahi hain:
- Context: Current processing request mein available information.
- Memory: System ki cross-session information retain karne ki capability, product aur settings ke hisaab se.

## 11. Decoding: temperature, top-k and top-p

Model possible next tokens ke scores produce karta hai. Decoding settings token selection ko influence karti hain.

- **Temperature:** Lower values generally more predictable; higher values generally more varied output.
- **Top-k:** Selection ko top k candidate tokens tak restrict karta hai.
- **Top-p:** Cumulative probability threshold ke basis par candidate set choose karta hai.
- **Max output tokens:** Response length limit karta hai.
- **Stop sequence:** Defined token/string par generation stop kar sakta hai.

Exact behaviour model aur provider par depend karta hai.

## 12. Hallucination

Hallucination tab hoti hai jab model incorrect, unsupported ya invented information ko confident language mein present karta hai.

Risk reduce karne ke methods:
- Trusted source material provide karna.
- RAG aur citations use karna.
- Important facts independently verify karna.
- Uncertainty clearly show karna.
- Human review aur evaluations rakhna.

RAG hallucination ko zero nahi karta. Retrieved content incomplete, outdated ya incorrect ho sakta hai.

## 13. RAG — Retrieval-Augmented Generation

RAG mein response generate karne se pehle external knowledge source se relevant information retrieve ki jaati hai.

Typical workflow:
1. Documents collect aur parse karna.
2. Documents ko chunks mein divide karna.
3. Chunk embeddings generate karna.
4. Vectors aur metadata index/store karna.
5. User query receive karna.
6. Query ke relevant chunks retrieve karna.
7. Retrieved context LLM ko dena.
8. Answer aur supporting source references return karna.
9. Retrieval aur answer quality evaluate karna.

Main components:
- Document loader.
- Parser and chunker.
- Embedding model.
- Vector index/database.
- Retriever or reranker.
- LLM.
- Source/citation layer.
- Evaluation and monitoring.

Vector search tools/platform examples: FAISS, Chroma, Pinecone, Weaviate aur Milvus. Selection data scale, hosting, filters, security aur budget par depend karti hai.

## 14. RAG vs Fine-Tuning

| RAG | Fine-Tuning |
|---|---|
| External content retrieve karta hai | Model parameters ko further train karta hai |
| Frequently changing facts/documents ke liye useful | Task behaviour, style ya domain adaptation ke liye useful |
| Retrieved sources cite/show kiye ja sakte hain | Sources automatically provide nahi hote |
| Knowledge base update ki ja sakti hai | Updated knowledge ke liye training/update required ho sakta hai |

Dono approaches ek system mein combine bhi ki ja sakti hain.

## 15. Multimodal AI

Multimodal AI multiple data types process ya generate kar sakta hai.

Examples:
- Text: questions and answers.
- Image: visual analysis.
- Audio: speech recognition or generation.
- Video: clip understanding.
- Documents: text, tables and page images.
- Mixed input: image plus a text question.

Multimodal systems ke outputs ko bhi task ke hisaab se verify karna chahiye.

## 16. AI API and application architecture

API application ko model service se connect karne ka interface hai.

```text
Web / Mobile Frontend
        |
        v
Secure Backend
        |
        v
Authentication + Validation
        |
        v
AI Model API
        |
        v
Response Validation
        |
        v
Frontend Response
```

API keys frontend/browser code mein expose nahi karni chahiye. Secure backend, secrets management, rate limits, logging controls aur error handling use karein.

## 17. Practical project — Company Knowledge AI Assistant

Goal: Company ke approved documents se employee questions ke answers dene wala RAG assistant.

Suggested pages:
- Dashboard: usage and recent activity.
- AI Chat: question-answer interface.
- Knowledge Base: approved documents list.
- Upload Documents: authorized file upload.
- Sources: retrieved document references.
- Chat History: permitted previous conversations.
- Settings: model and retrieval settings.
- Admin: users, roles and access controls.

Workflow:
1. Admin approved documents upload karta hai.
2. Backend files parse aur chunks create karta hai.
3. Embedding model vectors banata hai.
4. Vector index chunks aur metadata store karta hai.
5. Employee question submit karta hai.
6. Retriever relevant permitted chunks find karta hai.
7. LLM context ke basis par answer draft karta hai.
8. UI answer aur sources show karti hai.

Illustrative pseudocode:

```python
def answer_question(question, relevant_documents):
    prompt = f"""
    Use only the supplied context.
    If the answer is not present, say that it is not available.

    Context:
    {relevant_documents}

    Question:
    {question}
    """
    # Call the selected model through a secure backend.
    # Keep provider credentials outside frontend code.
    return call_your_selected_llm_api(prompt)
```

This is workflow pseudocode, not a complete provider integration. Production needs authentication, document permissions, safe parsing, prompt-injection defenses, citations, rate limits, audit controls and evaluation.

## 18. Risks and safeguards

| Risk | Safeguard |
|---|---|
| Hallucination | Grounding, citations, testing and human review |
| Privacy leakage | Data minimization, access control and retention policies |
| Prompt injection | Treat retrieved content as untrusted; isolate instructions and tools |
| Copyright concerns | Check data/output rights and applicable licences |
| Bias | Representative evaluation and monitoring |
| Excessive cost | Usage limits, caching and model selection |
| Unsafe actions | Least privilege, approval gates and audit logs |

## 19. Tools and official learning resources

- Hugging Face Learn: https://huggingface.co/learn
- Transformers documentation: https://huggingface.co/docs/transformers
- OpenAI API documentation: https://platform.openai.com/docs
- Google AI for Developers: https://ai.google.dev/
- LangChain documentation: https://docs.langchain.com/
- LlamaIndex documentation: https://docs.llamaindex.ai/
- FAISS: https://faiss.ai/
- Chroma: https://docs.trychroma.com/

Tools/framework examples include Hugging Face Transformers, Ollama, LangChain, LlamaIndex and vector search systems. Evaluate them based on requirements rather than choosing only by popularity.

## 20. Knowledge check

1. Generative AI ka main purpose kya hai?
2. Token kya hota hai?
3. Embedding ka use kya hai?
4. RAG mein retrieval ka role kya hai?
5. Fine-tuning pretrained model ko kaise adapt karti hai?
6. Context window aur persistent memory mein kya difference hai?
7. API key frontend mein expose kyun nahi karni chahiye?

Answer hints: New content generation; text ka unit; numerical vector representation; relevant source information search; further parameter training; current context vs cross-session retention; credential theft/misuse risk.

## 21. Chapter summary

- Generative AI new content generate karta hai.
- LLM language patterns learn karke text-related tasks perform karte hain.
- Tokenization text ko tokens mein divide karti hai.
- Embeddings data ko vectors mein represent karte hain.
- Transformers self-attention use karte hain.
- Pretraining general patterns sikhati hai; fine-tuning model ko adapt karti hai.
- Prompt engineering instructions ko clear banati hai.
- RAG external knowledge retrieve karke answer ko ground kar sakta hai.
- Multimodal models multiple data types process karte hain.
- Secure APIs, privacy, evaluation aur human oversight production systems ke liye essential hain.

**Chapter 07 status:** Learning notes prepared and added to the repository.
