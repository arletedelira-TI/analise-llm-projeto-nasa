# Análise de Documentos com LLM — Projeto NASA 🚀

Este projeto foi desenvolvido com o objetivo de implementar uma arquitetura de **RAG (Retrieval-Augmented Generation)** utilizando o ecossistema **LangChain** para analisar, extrair e consultar de forma inteligente a documentação estratégica da NASA. 

O foco principal da análise é o documento oficial de desenvolvimento de objetivos e estratégias da jornada da Lua a Marte (*Moon to Mars Strategy and Objectives Development*).

---

## Tecnologias e Ferramentas

A stack técnica utilizada no projeto foi estruturada para garantir eficiência no processamento de linguagem natural e na busca semântica por similaridade:

*   **Linguagem:** Python
*   **Orquestração de LLM:** LangChain & LangChain-Community
*   **Processamento de PDFs:** PyPDF (via `PyPDFLoader`)
*   **Provedor de Inferência:** Groq (via `LangChain-Groq`)
*   **Modelos e Componentes Extras:** LangChain-HuggingFace & LangGraph
*   **Ambiente de Desenvolvimento:** Google Colab

---

## Arquitetura do Sistema (Fluxo RAG)

O pipeline de análise de dados segue a estrutura padrão de enriquecimento de contexto para modelos de linguagem:

1.  **Carregamento Automatizado:** O PDF original hospedado neste repositório é consumido diretamente em formato *raw* através do carregador nativo da LangChain.
2.  **Processamento e Chunking:** O texto longo do documento é segmentado em blocos menores e gerenciáveis para manter o contexto sem estourar a janela de tokens da LLM.
3.  **Vetorização (Embeddings):** Criação de vetores numéricos representativos do conteúdo textual de cada página do documento.
4.  **Busca por Similaridade:** Armazenamento em um *Vector Store* para recuperação eficiente dos trechos de texto mais relevantes com base na pergunta do usuário.
5.  **Geração de Resposta:** O provedor Groq recebe a pergunta enriquecida com o contexto exato extraído do documento da NASA para gerar uma resposta precisa e fundamentada.

---

## Como Executar o Projeto

Você pode rodar e experimentar este ecossistema de análise diretamente no seu navegador com apenas um clique:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/arletedelira-TI/analise-llm-projeto-nasa/blob/main/analise_de_documento_com_langchain.ipynb)

### Pré-requisitos
Caso opte por rodar as células manualmente, certifique-se de ter suas chaves de API (como a `GROQ_API_KEY`) configuradas no ambiente de execução. As dependências do projeto são instaladas de forma automatizada no início do notebook:

```bash
pip install -qU pypdf langchain langchain-community langchain-groq langchain-huggingface langgraph
```

## 📁 Estrutura do Repositório

```text
├── analise_de_documento_com_langchain.ipynb  # Notebook Jupyter com o pipeline RAG completo
└── document-nasa-s-moon-to-mars-strategy...pdf # Documento base da NASA (fonte de dados)
