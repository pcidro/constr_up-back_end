# Constr Up - API de Produtos (Backend)

API RESTful desenvolvida em **Laravel 11** e **MySQL** para gerenciamento e CRUD de produtos para o teste técnico da Constr Up.

---

## Tecnologias e Requisitos

- **PHP**: 8.2 ou superior
- **Laravel**: 11.x
- **Banco de Dados**: MySQL
- **Gerenciador de Dependências**: Composer
- **Ambiente de Desenvolvimento**: Laragon (ou similar)

## Repositório Front End

- **Frontend (Vue 3 + TypeScript + Vite)**: [https://github.com/pcidro/constr_up-front-end](https://github.com/pcidro/constr_up-front-end)

---

## Como Executar o Projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/pcidro/constr_up-back_end.git
cd constr_up-back_end
```

### 2. Instalar as dependências do PHP

```bash
composer install
```

### 3. Configurar as Variáveis de Ambiente

Copie o arquivo de exemplo `.env.example` para `.env`:

```bash
cp .env.example .env
```

Abra o arquivo `.env` e configure a conexão com o MySQL:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=constr_up
DB_USERNAME=root
DB_PASSWORD=
```

### 4. Gerar a chave da aplicação

```bash
php artisan key:generate
```

### 5. Executar as Migrations (Criar as tabelas no banco)

```bash
php artisan migrate
```

### 6. Iniciar o Servidor de Desenvolvimento

```bash
php artisan serve
```

A API estará acessível em: `http://127.0.0.1:8000`

---

## Endpoints da API

Todas as rotas possuem o prefixo `/api` e aceitam o header `Accept: application/json`.

| Método     | Endpoint             | Descrição                                 | Status de Sucesso |
| :--------- | :------------------- | :---------------------------------------- | :---------------- |
| **GET**    | `/api/products`      | Lista todos os produtos                   | `200 OK`          |
| **POST**   | `/api/products`      | Cadastra um novo produto                  | `201 Created`     |
| **GET**    | `/api/products/{id}` | Retorna detalhes de um produto específico | `200 OK`          |
| **PUT**    | `/api/products/{id}` | Atualiza os dados de um produto           | `200 OK`          |
| **DELETE** | `/api/products/{id}` | Remove um produto                         | `200 OK`          |

---

## Exemplos de Uso dos Endpoints

### 1. Listar todos os produtos (GET)

- **Requisição**: `GET /api/products`
- **Resposta (200 OK)**:

```json
[
    {
        "id": 1,
        "name": "Arroz Branco Tipo 1 5kg",
        "description": "Arroz branco tipo 1 para consumo diário",
        "brand": "Camil",
        "price": 9.99,
        "stock": 80,
        "created_at": "2026-08-26T12:14:26.000000Z",
        "updated_at": "2026-08-26T12:36:07.000000Z"
    }
]
```

---

### 2. Cadastrar novo produto (POST)

- **Requisição**: `POST /api/products`
- **Headers**: `Content-Type: application/json`, `Accept: application/json`
- **Body**:

```json
{
    "name": "Caldo de Cana 500ml",
    "description": "Caldo de cana natural, fresco e pronto para consumo",
    "brand": "Jandaia",
    "price": 7.5,
    "stock": 50
}
```

- **Resposta (201 Created)**:

```json
{
    "name": "Caldo de Cana 500ml",
    "description": "Caldo de cana natural, fresco e pronto para consumo",
    "brand": "Jandaia",
    "price": 7.5,
    "stock": 50,
    "updated_at": "2026-08-26T12:30:05.000000Z",
    "created_at": "2026-08-26T12:30:05.000000Z",
    "id": 2
}
```

---

### 3. Exibir um produto por ID (GET)

- **Requisição**: `GET /api/products/ID`
- **Resposta (200 OK)**:

```json
{
    "id": 1,
    "name": "Arroz Branco Tipo 1 5kg",
    "description": "Arroz branco tipo 1 para consumo diário",
    "brand": "Camil",
    "price": "29.90",
    "stock": 80,
    "created_at": "2026-08-26T12:14:26.000000Z",
    "updated_at": "2026-08-26T12:14:26.000000Z"
}
```

---

### 4. Atualizar um produto (PUT)

- **Requisição**: `PUT /api/products/ID`
- **Headers**: `Content-Type: application/json`, `Accept: application/json`
- **Body**:

```json
{
    "price": 9.99
}
```

- **Resposta (200 OK)**:

```json
{
    "id": 1,
    "name": "Arroz Branco Tipo 1 5kg",
    "description": "Arroz branco tipo 1 para consumo diário",
    "brand": "Camil",
    "price": "29.90",
    "stock": 80,
    "created_at": "2026-08-26T12:14:26.000000Z",
    "updated_at": "2026-08-26T12:14:26.000000Z"
}
```

---

### 5. Excluir um produto (DELETE)

- **Requisição**: `DELETE /api/products/ID`
- **Resposta (200 OK)**:

```json
{
    "message": "Product deleted"
}
```

---
