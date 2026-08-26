# Constr Up - API de Produtos (Backend)

API RESTful desenvolvida em **Laravel 11** e **MySQL** para gerenciamento e CRUD de produtos para o teste técnico da Constr Up.

---

## Tecnologias e Requisitos

- **PHP**: 8.2 ou superior
- **Laravel**: 11.x
- **Banco de Dados**: MySQL
- **Gerenciador de Dependências**: Composer
- **Ambiente de Desenvolvimento**: Laragon (ou similar)

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

Abra o arquivo `.env` e configure o banco de dados MySQL:

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

Todas as rotas possuem o prefixo `/api`.

| Método     | Endpoint             | Descrição                                 | Status de Sucesso |
| :--------- | :------------------- | :---------------------------------------- | :---------------- |
| **GET**    | `/api/products`      | Lista todos os produtos                   | `200 OK`          |
| **POST**   | `/api/products`      | Cadastra um novo produto                  | `201 Created`     |
| **GET**    | `/api/products/{id}` | Retorna detalhes de um produto específico | `200 OK`          |
| **PUT**    | `/api/products/{id}` | Atualiza os dados de um produto           | `200 OK`          |
| **DELETE** | `/api/products/{id}` | Remove um produto                         | `200 OK`          |

---
