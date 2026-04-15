# KitchenFlow API Documentation

Documentação da API do **KitchenFlow V2**, sistema de gestão gastronômica com foco em controle operacional, CMV real, comandas, vendas e inteligência de cardápio.

---

## 🌐 Base URL

Produção:
https://kitchenflow-backend-p8cq.onrender.com

Local:
http://localhost:3000

---

## 📦 Formato de Dados

A API utiliza:

- JSON para envio e retorno de dados
- Header obrigatório:

Content-Type: application/json

---

## 📊 Status HTTP

- 200 OK → sucesso
- 201 Created → criado com sucesso
- 400 Bad Request → erro de dados
- 404 Not Found → não encontrado
- 500 Internal Server Error → erro interno

---

# 🚀 Endpoints

## 🏠 Rota principal

GET /

Retorna a interface do sistema.

---

## 💰 Vendas

GET /vendas  
Lista todas as vendas

---

GET /vendas/resumo  
Resumo gerencial (faturamento, ticket médio, etc)

---

GET /vendas/cmvs  
CMV por prato

---

POST /vendas/cmv-real  

Body:
{
  "prato_id": 1
}

---

POST /vendas/simular  

Body:
{
  "prato_id": 1,
  "quantidade": 2,
  "preco_unitario": 59.9
}

---

## 🥬 Insumos

Base:
GET /insumos  
POST /insumos  

Controle de estoque e insumos

---

## 🍝 Fichas Técnicas

Base:
GET /fichas  
POST /fichas  

Controle de composição dos pratos

---

## 🍽️ Pratos

Base:
GET /pratos  
POST /pratos  

Gerenciamento de cardápio

---

## 📦 Movimentações

Base:
GET /movimentacoes  
POST /movimentacoes  

Entrada e saída de estoque

---

## 🧾 Comandas

Base:
GET /comandas  
POST /comandas  

Gestão operacional do salão

---

## 🪑 Mesas

Base:
GET /mesas  
POST /mesas  

Controle de mesas e ocupação

---

# 💻 Exemplos de uso

## Buscar resumo de vendas

fetch("https://kitchenflow-backend-p8cq.onrender.com/vendas/resumo")
  .then(res => res.json())
  .then(data => console.log(data));

---

## Simular venda

fetch("https://kitchenflow-backend-p8cq.onrender.com/vendas/simular", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    prato_id: 1,
    quantidade: 2,
    preco_unitario: 59.9
  })
})
.then(res => res.json())
.then(data => console.log(data));

---

# 🧠 Arquitetura

- server.js → inicialização do servidor  
- routes/ → definição de rotas  
- controllers/ → regras de negócio  
- database.js → banco de dados  

---

# ⚠️ Observações

- Banco SQLite em ambiente temporário (Render)
- Dados não persistem após reinício
- Ideal para demonstração

---

# 🔗 Sistema Online

https://kitchenflow-backend-p8cq.onrender.com

---

# 👨‍🍳 Autor

Fernando Andrade  
Desenvolvedor Backend | Node.js | APIs REST  
Chef Executivo & Consultor Gastronômico
