# Feedback Inteligente

Chatbot com inteligência artificial que combina function calling, integrações externas, armazenamento vetorial e um ciclo de feedback para evolução contínua do prompt do sistema.

## Principais recursos

- Conversação com Google Gemini 2.5 Flash
- Function calling nativo para uso de ferramentas externas
- Contexto semântico com ChromaDB
- Histórico persistente de conversas
- Coleta e processamento de feedback dos usuários
- Versionamento e atualização automática do prompt
- Interface web com Streamlit
- Execução local ou via Docker

## Integrações

O assistente pode consultar serviços externos como:

- ViaCEP
- PokéAPI
- IBGE
- Open-Meteo
- TVMaze
- Open Library
- Lyrics.ovh

## Arquitetura

```text
feedback-inteligente/
├── src/
│   ├── agent/          # Lógica do agente e gerenciamento de prompts
│   ├── feedback/       # Processamento de feedback
│   ├── tools/          # Integrações externas
│   └── vectorstore/    # ChromaDB
├── data/               # Histórico persistente
├── tests/
├── app.py              # Aplicação Streamlit
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
└── .env.example
```

## Tech Stack

- Python
- Google Gemini 2.5 Flash
- ChromaDB
- Streamlit
- Docker / Docker Compose
- pytest

## Execução local

Clone o repositório e instale as dependências:

```bash
git clone https://github.com/anetogm/feedback-inteligente.git
cd feedback-inteligente
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Configure a chave do Gemini:

```bash
cp .env.example .env
```

Depois execute:

```bash
streamlit run app.py
```

A aplicação ficará disponível normalmente em `http://localhost:8501`.

## Docker

```bash
cp .env.example .env
docker compose up -d --build
```

## Testes

```bash
pytest
```

Com cobertura:

```bash
pytest --cov=src tests/
```

## Objetivo técnico

O projeto explora agentes com ferramentas, memória semântica, persistência de contexto e uso de feedback para modificar dinamicamente o comportamento de um sistema baseado em LLM.
