# Estágio

# Estratégias para reduzir o viés de confirmação em Grandes Modelos de Linguagem

Este repositório contém os *scripts* de automação e análise utilizados no projeto.
O presente estudo visa analisar e comparar a eficácia de diversas técnicas de mitigação do viés de confirmação.

## Modelos Avaliados
A pesquisa avaliou modelos comerciais (via API) e de código aberto (via execução local):
* **Comerciais (OpenRouter):** GPT-4o, Claude 3.7, Gemini 1.5 Pro, DeepSeek-V3, Qwen3-235B-A22B, Grok-3.
* **Open-Source (LM Studio):** Meta-Llama-3.1-8B, Mistral-7B-v0.3, Qwen-2.5-7B, Gemma-3-4B.

## Guia de Utilização

1. Configuração do Ambiente:
   
Instale as dependências necessárias: pandas requests tqdm matplotlib seaborn

2. Configuração dos Modelos (Local vs API):
   
Os scripts de teste são versáteis e podem ser configurados conforme a necessidade:

Para Modelos Locais (LM Studio):

  1. Inicie o servidor no LM Studio (aba Local Server).

  2. Certifique-se de que o servidor está ativo em http://localhost:1234.

  3. No código, verifique se a variável de URL aponta para o endereço local.

Para Modelos via API (Ex: DeepSeek, OpenAI):

  1. Insira a sua chave de API na variável correspondente (ex: API_KEY).

  2. Configure o endpoint oficial do fornecedor no campo de URL do script.
