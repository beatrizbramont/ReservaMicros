# 📚 API de Reserva de Salas

Este repositório contém a **API de Reserva de Salas**, desenvolvida com **Flask** e **SQLAlchemy**, como parte de uma arquitetura baseada em **microsserviços**.

## 🧩 Arquitetura

A API de Reserva de Salas é um **microsserviço** que faz parte de um sistema maior de [School System](https://github.com/beatrizbramont/ProjetoAPI.git)
, sendo responsável exclusivamente pelo gerenciamento das reservas de salas por turma.

⚠️ **Esta API depende de outra API de Gerenciamento Escolar (School System)**, que deve estar em execução e exposta localmente. A comunicação entre os serviços ocorre via **requisições HTTP REST**, para validar:

- Se a **Turma** existe (`GET /turma/<id>`)

---

## 🚀 Tecnologias Utilizadas

- Python 3.x;
- Flask;
- SQLAlchemy;
- SQLite (como banco de dados local);
- Requests (para consumo da API externa).

---

## ▶️ Como Executar a API

### 1. Clone o repositório

```bash
git clone https://github.com/beatrizbramont/ReservaMicros.git
cd ReservaMicros
```

### 2. Crie um ambiente virtual (opcional, mas recomendado)

```bash
python3 -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Execute a API

```bash
python app.py
```

A aplicação estará disponível em:
📍 `http://127.0.0.1:5000`

📝 **Observação:** O banco de dados é criado automaticamente na primeira execução.

---

## 📡 Endpoints Principais

- `GET /reservas` – Lista todas as reservas
- `POST /reservas` – Cria uma nova reserva
- `GET /reservas/<id>` – Detalha uma reserva
- `PUT /reservas/<id>` – Atualiza uma reserva
- `DELETE /reservas/<id>` – Remove uma reserva

### Exemplo de corpo JSON para criação:

```json
{
  "turma_id": 1,
  "sala": "101",
  "data": "2025-05-06",
  "hora_inicio": "14:00",
  "hora_fim": "16:00"
}
```

---

## 🔗 Dependência Externa

Certifique-se de que a **API de Gerenciamento Escolar** esteja rodando em:

```
http://127.0.0.1:8001
```

E que o endpoint de `GET /turma/<id>` corretamente para que a validação seja feita com sucesso.

---

## 📦 Estrutura do Projeto

```
reserva-de-salas-flask/
│
├── controller/
│   └── reserva_route.py      
│
├── instance/
│   └── reservas.db           
│
├── models/
│   └── reserva_model.py      
│
├── app.py                    
├── config.py                 
├── database.py               
├── Dockerfile                
├── requirements.txt          
└── README.md

```

---

## 🛠️ Futuras Melhorias

- Validação de conflito de horário na sala;
- Integração via fila (RabbitMQ) com outros microsserviços;
- Autenticação de usuários.

---

## 🧑‍💻 Autores

- Beatriz Bramont 
- Isadora Silva
- Giovanna Petrilli