
# Santander Dev Week 2023 – ETL com Python

Este projeto foi desenvolvido como parte do desafio **Santander Dev Week 2023**, com o objetivo de aplicar conceitos de **ETL (Extract, Transform, Load)** para personalizar a comunicação com clientes do banco, utilizando **Inteligência Artificial Generativa (OpenAI GPT)** para criar mensagens de marketing.

---

## 🏆 Desafio

Você é um cientista de dados no Santander. Seu objetivo é envolver os clientes de forma personalizada, usando IA para gerar mensagens de marketing que serão entregues individualmente.

---

## 🔄 Fluxo do Projeto

### 📥 Extract

- Ler uma lista de IDs de usuários de um arquivo CSV (`SDW2023.csv`).
- Para cada ID, buscar os dados do usuário na API pública da Santander Dev Week 2023:  
  **GET** `https://sdw-2023-prd.up.railway.app/users/{id}`

### 🔧 Transform

- Gerar mensagens de marketing personalizadas utilizando a API da OpenAI (ChatGPT / GPT-4).
- Foco em destacar a **importância dos investimentos**.

### 📤 Load

- Atualizar os dados dos usuários na API, adicionando a mensagem gerada à lista de notícias do cliente:  
  **PUT** `https://sdw-2023-prd.up.railway.app/users/{id}`

---

## 🚀 Como Rodar o Projeto

1. Clone o repositório e instale as dependências:

```bash
pip install -r requirements.txt
```

2. Adicione sua chave de API da OpenAI em uma variável de ambiente  
ou diretamente no código (**não recomendado para produção**).

3. Execute o notebook `Cópia_de_SantanderDevWeek2023.ipynb`,  
seguindo o fluxo ETL descrito acima.

---

## 📄 Sobre o Arquivo Principal

O notebook contém exemplos de requisições para:

- 📄 Ler o CSV.
- 🔍 Buscar dados dos usuários via API.
- ✍️ Gerar mensagens personalizadas usando OpenAI.
- 🔄 Atualizar o cadastro dos usuários com a nova mensagem.

---

## ❗ Explicação do Erro Encontrado

Durante a execução, ocorreu o seguinte erro:

```
RateLimitError: You exceeded your current quota, please check your plan and billing details.
```

### 🤔 O que isso significa?

- A OpenAI impõe um limite de uso (gratuito ou pago) para suas APIs.
- Quando esse limite é atingido (por excesso de requisições ou falta de créditos), você recebe este erro.

### ✅ Como Resolver:

1. Verifique seu plano e saldo em:  
   🔗 [https://platform.openai.com/account/usage](https://platform.openai.com/account/usage)

2. Caso tenha ultrapassado o limite gratuito:
   - Adicione créditos.  
   **OU**  
   - Aguarde a renovação mensal do plano.

---

## 🔍 Observações

- O projeto é **didático** e pode ser adaptado para outras finalidades de **ETL** e **IA**.
- Caso não possua uma chave da OpenAI, a geração das mensagens pode ser **simulada ("mockada")** apenas para testes.

---
