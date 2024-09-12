# Nutricionista Cardápio API

API RESTful para gerenciamento de cardápios por nutricionistas e visualização por usuários. Desenvolvida com Spring Boot, Spring Data JPA, Flyway e JWT.

## Tarefas

- [ ] CRUD de Nutricionistas
- [ ] CRUD de Usuários
- [ ] CRUD de Cardápios
- [ ] Autenticação com JWT
- [ ] Paginação e Busca

## Documentação da API

### Endpoint
- [Cadastrar Nutricionista](#cadastrar-nutricionista)
- [Apagar Nutricionista](#apagar-nutricionista)
- [Atualizar Nutricionista](#atualizar-nutricionista)
- [Cadastrar Usuário](#cadastrar-usuário)
- [Detalhes do Usuário](#detalhes-do-usuário)
- [Apagar Usuário](#apagar-usuário)
- [Atualizar Usuário](#atualizar-usuário)
- [Listar Todos os Cardápios](#listar-todos-os-cardápios)
- [Cadastrar Cardápio](#cadastrar-cardápio)
- [Detalhes do Cardápio](#detalhes-do-cardápio)
- [Apagar Cardápio](#apagar-cardápio)
- [Atualizar Cardápio](#atualizar-cardápio)

### Listar Todos os Nutricionistas

`GET` /nutricionistas

Retorna uma lista de todos os nutricionistas cadastrados.

#### Exemplo de Resposta

```json
[
    {
        "id": 1,
        "nome": "Dr. João Silva",
        "email": "joao.silva@exemplo.com"
    }
]
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Os dados dos nutricionistas foram retornados com sucesso |
| 401    | Acesso negado. Você deve se autenticar |

---

### Cadastrar Nutricionista

`POST` /nutricionistas

Cria um novo nutricionista com os dados enviados no corpo da requisição.

#### Corpo da Requisição

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| nome  | string | ✅ | Nome completo do nutricionista |
| email | string | ✅ | Email válido do nutricionista |
| senha | string | ✅ | Senha para autenticação |

```json
{
    "nome": "Dr. João Silva",
    "email": "joao.silva@exemplo.com",
    "senha": "senha123"
}
```

#### Exemplo de Resposta

```json
{
    "id": 1,
    "nome": "Dr. João Silva",
    "email": "joao.silva@exemplo.com"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 201    | Nutricionista cadastrado com sucesso |
| 400    | Dados enviados são inválidos. Verifique o corpo da requisição |
| 401    | Acesso negado. Você deve se autenticar |

---

### Detalhes do Nutricionista

`GET` /nutricionistas/{id}

Retorna os detalhes do nutricionista com o `id` informado como parâmetro de path.

#### Exemplo de Resposta

```json
// requisição para /nutricionistas/1
{
    "id": 1,
    "nome": "Dr. João Silva",
    "email": "joao.silva@exemplo.com"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Os dados do nutricionista foram retornados com sucesso |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe nutricionista com o `id` informado |

---

### Apagar Nutricionista

`DELETE` /nutricionistas/{id}

Apaga o nutricionista com o `id` especificado no parâmetro de path.

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 204    | Nutricionista apagado com sucesso |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe nutricionista com o `id` informado |

---

### Atualizar Nutricionista

`PUT` /nutricionistas/{id}

Altera os dados do nutricionista especificado no `id`, utilizando as informações enviadas no corpo da requisição.

#### Corpo da Requisição

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| nome  | string | ✅ | Nome completo do nutricionista |
| email | string | ✅ | Email válido do nutricionista |
| senha | string | ❌ | Senha para autenticação |

```json
{
    "nome": "Dr. João Silva",
    "email": "joao.silva@exemplo.com"
}
```

#### Exemplo de Resposta

```json
{
    "id": 1,
    "nome": "Dr. João Silva",
    "email": "joao.silva@exemplo.com"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Nutricionista alterado com sucesso |
| 400    | Dados enviados são inválidos. Verifique o corpo da requisição |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe nutricionista com o `id` informado |

---

### Listar Todos os Usuários

`GET` /usuarios

Retorna uma lista de todos os usuários cadastrados.

#### Exemplo de Resposta

```json
[
    {
        "id": 1,
        "nome": "Maria Oliveira",
        "email": "maria.oliveira@exemplo.com"
    }
]
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Os dados dos usuários foram retornados com sucesso |
| 401    | Acesso negado. Você deve se autenticar |

---

### Cadastrar Usuário

`POST` /usuarios

Cria um novo usuário com os dados enviados no corpo da requisição.

#### Corpo da Requisição

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| nome  | string | ✅ | Nome completo do usuário |
| email | string | ✅ | Email válido do usuário |
| senha | string | ✅ | Senha para autenticação |

```json
{
    "nome": "Maria Oliveira",
    "email": "maria.oliveira@exemplo.com",
    "senha": "senha123"
}
```

#### Exemplo de Resposta

```json
{
    "id": 1,
    "nome": "Maria Oliveira",
    "email": "maria.oliveira@exemplo.com"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 201    | Usuário cadastrado com sucesso |
| 400    | Dados enviados são inválidos. Verifique o corpo da requisição |
| 401    | Acesso negado. Você deve se autenticar |

---

### Detalhes do Usuário

`GET` /usuarios/{id}

Retorna os detalhes do usuário com o `id` informado como parâmetro de path.

#### Exemplo de Resposta

```json
// requisição para /usuarios/1
{
    "id": 1,
    "nome": "Maria Oliveira",
    "email": "maria.oliveira@exemplo.com"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Os dados do usuário foram retornados com sucesso |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe usuário com o `id` informado |

---

### Apagar Usuário

`DELETE` /usuarios/{id}

Apaga o usuário com o `id` especificado no parâmetro de path.

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 204    | Usuário apagado com sucesso |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe usuário com o `id` informado |

---

### Atualizar Usuário

`PUT` /usuarios/{id}

Altera os dados do usuário especificado no `id`, utilizando as informações enviadas no corpo da requisição.

#### Corpo da Requisição

| Campo | Tipo | Obrigatório | Descrição |
|-------|------|-------------|-----------|
| nome  | string | ✅ | Nome completo do usuário |
| email | string | ✅ | Email válido do usuário |
| senha | string | ❌ | Senha para autenticação |

```json
{
    "nome": "Maria Oliveira",
    "email": "maria.oliveira@exemplo.com"
}
```

#### Exemplo de Resposta

```json
{
    "id": 1,
    "

nome": "Maria Oliveira",
    "email": "maria.oliveira@exemplo.com"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Usuário alterado com sucesso |
| 400    | Dados enviados são inválidos. Verifique o corpo da requisição |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe usuário com o `id` informado |

---

### Listar Todos os Cardápios

`GET` /cardapios

Retorna uma lista de todos os cardápios cadastrados.

#### Exemplo de Resposta

```json
[
    {
        "id": 1,
        "nome": "Cardápio do Dia",
        "descricao": "Cardápio para hoje"
    }
]
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Os dados dos cardápios foram retornados com sucesso |
| 401    | Acesso negado. Você deve se autenticar |

---

### Cadastrar Cardápio

`POST` /cardapios

Cria um novo cardápio com os dados enviados no corpo da requisição.

#### Corpo da Requisição

| Campo      | Tipo   | Obrigatório | Descrição |
|------------|--------|-------------|-----------|
| nome       | string | ✅          | Nome do cardápio |
| descricao  | string | ✅          | Descrição do cardápio |

```json
{
    "nome": "Cardápio do Dia",
    "descricao": "Cardápio para hoje"
}
```

#### Exemplo de Resposta

```json
{
    "id": 1,
    "nome": "Cardápio do Dia",
    "descricao": "Cardápio para hoje"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 201    | Cardápio cadastrado com sucesso |
| 400    | Dados enviados são inválidos. Verifique o corpo da requisição |
| 401    | Acesso negado. Você deve se autenticar |

---

### Detalhes do Cardápio

`GET` /cardapios/{id}

Retorna os detalhes do cardápio com o `id` informado como parâmetro de path.

#### Exemplo de Resposta

```json
// requisição para /cardapios/1
{
    "id": 1,
    "nome": "Cardápio do Dia",
    "descricao": "Cardápio para hoje"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Os dados do cardápio foram retornados com sucesso |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe cardápio com o `id` informado |

---

### Apagar Cardápio

`DELETE` /cardapios/{id}

Apaga o cardápio com o `id` especificado no parâmetro de path.

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 204    | Cardápio apagado com sucesso |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe cardápio com o `id` informado |

---

### Atualizar Cardápio

`PUT` /cardapios/{id}

Altera os dados do cardápio especificado no `id`, utilizando as informações enviadas no corpo da requisição.

#### Corpo da Requisição

| Campo      | Tipo   | Obrigatório | Descrição |
|------------|--------|-------------|-----------|
| nome       | string | ✅          | Nome do cardápio |
| descricao  | string | ✅          | Descrição do cardápio |

```json
{
    "nome": "Cardápio do Dia",
    "descricao": "Cardápio atualizado para hoje"
}
```

#### Exemplo de Resposta

```json
{
    "id": 1,
    "nome": "Cardápio do Dia",
    "descricao": "Cardápio atualizado para hoje"
}
```

#### Códigos de Status

| Código | Descrição |
|--------|-----------|
| 200    | Cardápio alterado com sucesso |
| 400    | Dados enviados são inválidos. Verifique o corpo da requisição |
| 401    | Acesso negado. Você deve se autenticar |
| 404    | Não existe cardápio com o `id` informado |
```

Se precisar de mais ajustes ou detalhes, só avisar!
