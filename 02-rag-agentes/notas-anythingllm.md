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

  ### 2026-07-19 — Primer documento embebido: guía de mensajería HL7 (Sacyl)
- Subí el PDF público de mensajería HL7 de Sacyl al workspace
- Confirmé "Save and Embed" — AnythingLLM trocea el documento y genera 
  vectores con nomic-embed-text, guardados en LanceDB
- Pregunté sobre el plan de la histórica clínica electrónica y comprobé que la respuesta 
  citaba el documento