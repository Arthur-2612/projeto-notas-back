# 📝 Projeto Notas - Backend API

API RESTful simples e eficiente desenvolvida em Node.js e Express para o gerenciamento de notas e lembretes. O projeto utiliza persistência em arquivo JSON local (`data.json`) e possui suporte a CORS configurado para integração com front-ends.

---

## 🚀 Tecnologias Utilizadas

- **[Node.js](https://nodejs.org/)**: Ambiente de execução JavaScript no servidor.
- **[Express](https://expressjs.com/)**: Framework web para criação de rotas e manipulação de requisições HTTP.
- **[Body-Parser](https://www.npmjs.com/package/body-parser)**: Middleware para parsing do corpo das requisições JSON.
- **FS (File System)**: Módulo nativo do Node.js para leitura e escrita de dados no arquivo `data.json`.

---

## 📁 Estrutura do Projeto

```text
projeto-notas/
├── data.json           # Arquivo JSON onde as notas são salvas
├── node_modules/       # Dependências do projeto
├── package.json        # Configurações e dependências do Node.js
├── package-lock.json   # Trava de versões das dependências
├── server.js           # Código principal do servidor Express e rotas da API
└── README.md           # Documentação do projeto
```

---

## 🔗 Rotas da API

A API aceita e retorna dados no formato JSON.

| Método | Rota | Descrição | Corpo da Requisição (Payload) | Resposta |
| :--- | :--- | :--- | :--- | :--- |
| **GET** | `/api/notes` | Retorna a lista de todas as notas cadastradas | *Nenhum* | `[ { "id": "...", "titulo": "...", "texto": "..." } ]` |
| **POST** | `/api/notes` | Cria uma nova nota | `{ "titulo": "Título", "texto": "Conteúdo" }` | Objeto da nota criada com `id` gerado |
| **PUT** | `/api/notes/:id` | Atualiza uma nota existente pelo ID | `{ "titulo": "Novo Título", "texto": "Novo Conteúdo" }` | Objeto da nota atualizada ou erro 404 |
| **DELETE** | `/api/notes/:id` | Remove uma nota pelo ID | *Nenhum* | `{ "mensagem": "Nota removida" }` |

---

## 📦 Estrutura dos Dados (`data.json`)

Exemplo de objeto de nota armazenado:

```json
{
  "id": "1714305600000",
  "titulo": "Lembretes",
  "texto": "Comprar leite e pão",
  "criadoEm": "2026-04-28T10:00:00Z"
}
```

---

## 🛠️ Como Executar o Projeto

### Pré-requisitos

Certifique-se de ter o [Node.js](https://nodejs.org/) instalado em sua máquina.

### Passos para execução:

1. **Clonar o repositório:**
   ```bash
   git clone https://github.com/Arthur-2612/projeto-notas-back.git
   cd projeto-notas
   ```

2. **Instalar as dependências:**
   ```bash
   npm install
   ```

3. **Iniciar o servidor:**
   ```bash
   node server.js
   ```

4. O servidor estará rodando em: `http://localhost:3000`

---

## 🧪 Exemplos de Requisição

### Criar uma Nota (`POST /api/notes`)

```bash
curl -X POST http://localhost:3000/api/notes \
  -H "Content-Type: application/json" \
  -d '{"titulo": "Estudar Node.js", "texto": "Aprender sobre Express e manipulação de arquivos com FS"}'
```

### Listar Notas (`GET /api/notes`)

```bash
curl -X GET http://localhost:3000/api/notes
```

---

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se à vontade para utilizar e contribuir!
