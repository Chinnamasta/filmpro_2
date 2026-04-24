# filmpro_2
Assistente de recomendação de filmes com IA, integrando um agente com Agno, uma API com FastAPI e uma interface web em uma aplicação completa.

# FilmPro - Agente de Recomendação de Filmes

Agente inteligente baseado em IA que fornece recomendações personalizadas de filmes usando **Agno**, **OpenAI GPT-4o**, **OMDB API** e **DuckDuckGo**.

## Setup Rápido

```bash
# Criar e ativar venv
python3 -m venv .venv
source .venv/bin/activate

# Instalar dependências
pip install -r requirements.txt
```

```bash
# Configurar variáveis de ambiente
cp .env.example .env
# Edite o .env com suas chaves

# Executar
python main.py
```

## Variáveis de Ambiente

```env
OPENAI_API_KEY=sua_chave_openai
OMDB_API_KEY=sua_chave_omdb
```

> A chave da OMDB API pode ser obtida gratuitamente em [omdbapi.com](https://www.omdbapi.com/apikey.aspx).

## Estrutura

```
├── main.py              # Ponto de entrada e inicialização do agente
├── requirements.txt     # Dependências
├── models/
│   └── movies.py        # Modelos Pydantic (Movie, Cast, MovieRecommendation)
├── prompts/
│   └── movie_search.py  # Descrição e instruções do agente
└── tools/
    └── omdb.py          # Integração assíncrona com a OMDB API (aiohttp)
```

## Funcionalidades

- Recomendações personalizadas de filmes baseadas nas preferências do usuário
- Busca na web via DuckDuckGo para dados atualizados
- Consulta à OMDB API para metadados detalhados dos filmes
- Saída estruturada em JSON (Pydantic) com 5 a 20 recomendações por consulta
- Informações completas: elenco, diretor, plataformas de streaming, classificação etária e mais
- Respostas em português

## Stack

- **[Agno](https://github.com/agno-agi/agno)** — orquestração do agente
- **OpenAI GPT-4o** — modelo de linguagem
- **aiohttp** — cliente HTTP assíncrono para a OMDB API
- **Pydantic v2** — validação e serialização dos dados
- **DuckDuckGo Search (ddgs)** — busca na web
