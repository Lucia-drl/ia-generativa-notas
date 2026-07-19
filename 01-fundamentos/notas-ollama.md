# Fundamentos: Ollama, Continue y modelos locales

### 2026-07-19 — Primeros pasos con Ollama
- Instalé Ollama y descargué llama3.2:3b
- Probé el chat en terminal

### 2026-07-19 — Continue conectado a Ollama
- Instalé la extensión Continue en VS Code
- Configuré dos modelos: llama3.2:3b para chat, qwen2.5-coder:1.5b para autocompletado
- Aprendizaje clave: usar modelos distintos según la tarea (velocidad vs. calidad de razonamiento)

### 2026-07-19 — Embeddings para @codebase
- Añadí nomic-embed-text como modelo de embeddings (rol `embed`)
- Aprendizaje clave: el embedding no genera texto, convierte código en vectores 
  para que Continue pueda buscar por significado con @codebase — es un modelo 
  distinto al de chat o autocompletado
