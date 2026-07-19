# RAG con AnythingLLM

### 2026-07-19 — Primer workspace RAG funcionando
- Instalé AnythingLLM Desktop y lo conecté a Ollama (llama3.2:3b para chat, 
  nomic-embed-text para embeddings)
- Creé un workspace y subí un documento de prueba
- Aprendizaje clave: el embedder se fija a nivel global, no por workspace — 
  cambiarlo después obliga a re-indexar todo
- Probé el modo "Query" (responde solo con el documento) vs. "Chat" (puede 
  completar con conocimiento general) — Query es más fiable para casos donde 
  la exactitud importa más que la fluidez