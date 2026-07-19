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
  citaba el documento, pero no respondía exactamente la pregunta, hacía un resumen muy general

  ### 2026-07-19 — Sesión completa: embedding, alucinación y límite de contexto
- Configuré manualmente el embedder del workspace (nomic-embed-text), ya que 
  no se aplicaba por defecto
- Embebí el PDF público de mensajería HL7 de Sacyl
- Al preguntar por el "punto 5, ARQUITECTURA DE LA HCE" (página 8), el modelo 
  respondió con una arquitectura en capas y HL7 CDA — contenido inventado, 
  no presente en el documento real
- Diagnóstico: Ollama limita el contexto a 2048-4096 tokens por defecto 
  (~1,5-3 páginas) y corta el resto en silencio, sin avisar — el contenido 
  de la página 8 nunca llegó a estar disponible para el modelo
- Aprendizaje clave: un LLM local puede alucinar citas y contenido técnico 
  con total seguridad cuando el documento no cabe en su ventana de contexto — 
  la verificación humana es imprescindible, no opcional
- Pendiente para la próxima sesión: el workspace ha dejado de mostrar el 
  contenido embebido — a revisar sin más pruebas por hoy