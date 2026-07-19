### 2026-07-19 — Continue conectado a Ollama
- Instalé la extensión Continue en VS Code
- Configuré dos modelos: llama3.2:3b para chat, qwen2.5-coder:1.5b para autocompletado
- Aprendizaje clave: usar modelos distintos según la tarea (velocidad vs. calidad de razonamiento)
- Añadí nomic-embed-text como modelo de embeddings (rol `embed`)
- Aprendizaje clave: el embedding no genera texto, convierte código en vectores 
  para que Continue pueda buscar por significado con @codebase — es un modelo 
  distinto al de chat o autocompletado