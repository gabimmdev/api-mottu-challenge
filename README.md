# 🚀 API .NET - Projeto Mottu Pátio

## 👥 Integrantes
+ Gabriela Gomes - rm556941
+ Emily Maria - rm556941
+ Felipe de Santana - rm558916

---

## 🏛️ Justificativa da Arquitetura

A API foi desenvolvida em **ASP.NET Core 7.0** seguindo princípios de **Clean Architecture** e **RESTful** para garantir:
- Separação clara de responsabilidades (Controllers, Services, Repositories, Models).
- Escalabilidade: fácil de expandir endpoints e adicionar novas entidades.
- Testabilidade: suporte a testes unitários e de integração.
- Padrões de mercado: uso de `Entity Framework Core` para persistência de dados.

### Estrutura de pastas

```
📦 MottuPatioApi
 ┣ 📂 Controllers   → Camada de entrada (HTTP endpoints)
 ┣ 📂 Services      → Regras de negócio
 ┣ 📂 Repositories  → Acesso a dados (EF Core)
 ┣ 📂 Models        → Entidades e DTOs
 ┣ 📂 Data          → Contexto do banco (DbContext)
 ┣ 📂 Tests         → Projetos de teste
 ┗ Program.cs       → Configuração inicial da API
```

---

## ⚙️ Instruções de execução da API

### 1️⃣ Pré-requisitos
- [.NET 7 SDK](https://dotnet.microsoft.com/download)
- Banco de dados SQL Server (local ou Docker)

### 2️⃣ Clonar o repositório
```bash
git clone https://github.com/seu-repo/mottu-patio-api.git
cd mottu-patio-api
```

### 3️⃣ Configurar conexão com o banco
No arquivo `appsettings.json` edite a connection string:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=MottuPatioDb;User Id=sa;Password=Your_password123;"
}
```

### 4️⃣ Criar o banco de dados
```bash
dotnet ef database update
```

### 5️⃣ Rodar a API
```bash
dotnet run --project MottuPatioApi
```

A API ficará disponível em:
```
http://localhost:5000
```

---

## 📌 Exemplos de uso dos endpoints

### 🔑 Autenticação
**Registrar usuário**
```http
POST /api/auth/register
Content-Type: application/json

{
  "username": "joao",
  "password": "123456"
}
```

**Login**
```http
POST /api/auth/login
Content-Type: application/json

{
  "username": "joao",
  "password": "123456"
}
```

---

### 🛵 Motos (CRUD completo)

**Listar motos**
```http
GET /api/motos
Authorization: Bearer {token}
```

**Obter moto por ID**
```http
GET /api/motos/1
Authorization: Bearer {token}
```

**Cadastrar moto**
```http
POST /api/motos
Content-Type: application/json
Authorization: Bearer {token}

{
  "placa": "ABC1234",
  "marca": "Honda",
  "modelo": "CG 160"
}
```

**Atualizar moto**
```http
PUT /api/motos/1
Content-Type: application/json
Authorization: Bearer {token}

{
  "placa": "XYZ9876",
  "marca": "Yamaha",
  "modelo": "Fazer 250"
}
```

**Excluir moto**
```http
DELETE /api/motos/1
Authorization: Bearer {token}
```

---

## 🧪 Rodar os testes

### Executar todos os testes unitários:
```bash
dotnet test
```

### Executar testes com relatório detalhado:
```bash
dotnet test --logger "trx;LogFileName=TestResults.trx"
```

---

## ✅ Tecnologias usadas
- ASP.NET Core 7
- Entity Framework Core
- SQL Server
- JWT Authentication
- xUnit (testes)

---
