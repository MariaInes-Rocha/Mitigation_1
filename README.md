# Estágio

# Estratégias para reduzir o viés de confirmação em Grandes Modelos de Linguagem

Este repositório contém os *scripts* de automação e análise utilizados no projeto.
O presente estudo visa analisar e comparar a eficácia de diversas técnicas de mitigação do viés de confirmação.

## Modelos Avaliados
A pesquisa avaliou modelos comerciais (via API) e de código aberto (via execução local):
* **Comerciais (OpenRouter):** GPT-4o, Claude 3.7, Gemini 1.5 Pro, DeepSeek-V3, Qwen3-235B-A22B, Grok-3.
* **Open-Source (LM Studio):** Meta-Llama-3.1-8B, Mistral-7B-v0.3, Qwen-2.5-7B, Gemma-3-4B.

## 1. Configuração de Modelos via API (DeepSeek)
Ficheiro: Teste_mitigacao_eng_prompt_v0(sem_analise).ipynb

Neste ficheiro, não é necessário alterar o código dentro das funções. As configurações são feitas nas variáveis globais no início do notebook:

  API Key: Localize a variável api_key no topo do ficheiro e insira a sua chave entre aspas:

    api_key = "sk-xxxxxxxxxxxxxxxxxxxxxxxx"

  URL: A variável url já está configurada para o endpoint do DeepSeek. Só precisa de a alterar se quiser usar outro serviço compatível:

    url = "https://api.deepseek.com/chat/completions"

  Execução: O script utiliza automaticamente as colunas one_shot e few_shot do ficheiro CSV para realizar os testes.

## 2. Configuração de Modelos Locais (LM Studio)

Ficheiro: Teste_mitigacao_fine_tuning_v0(sem_analise).ipynb

Este script comunica com o modelo que estiver atualmente "carregado" e "ativo" no seu computador.

No LM Studio: Carregue o modelo e inicie o servidor (Porta 1234).

No Código (Início): A variável url deve apontar para o servidor local:

  url = "http://localhost:1234/v1/chat/completions"

No Código (Fim): Como o script não deteta o nome do modelo local sozinho, deve alterar a última linha do notebook para que o ficheiro de saída tenha o nome correto:

  # Altere "gemma-3-4b" para o nome do modelo que tenha aberto no LM Studio

  testar_mitigacao_local("perguntas_enviesadas.csv", "NOME_DO_MODELO")
