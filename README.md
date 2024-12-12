# QuickNotes

QuickNotes é um aplicativo web para anotações rápidas, desenvolvido com o objetivo de fornecer uma plataforma simples, moderna e eficiente para organização de ideias, tarefas e lembretes. Inspirado no estilo minimalista e intuitivo de ferramentas como OneNote, o QuickNotes é voltado para usuários que buscam praticidade no gerenciamento de suas anotações.

## Funcionalidades Principais
- **Criação de anotações**: Adicione títulos e conteúdos com facilidade.
- **Listagem de anotações**: Visualize todas as suas anotações em um formato organizado.
- **Edição de anotações**: Altere títulos ou conteúdos conforme necessário.
- **Exclusão de anotações**: Remova anotações que não são mais necessárias.
- **Interface responsiva**: Experiência otimizada para dispositivos desktop e móveis.

## Tecnologias Utilizadas
- **Frontend**: React.js (criado com Create React App)
- **Backend**: Node.js com Express
- **Banco de Dados**: MongoDB (usando Mongoose para modelagem)
- **Estilização**: CSS simples para um design limpo e funcional
- **Comunicação**: Axios para chamadas às APIs

## Estrutura do Projeto
```
/note-app
  /client      # Aplicativo Frontend (React)
  /server      # Servidor Backend (Node.js + Express)
  /db          # Configurações do MongoDB (opcional)
```

## Configuração do Ambiente

### Requisitos
- Node.js instalado (v16 ou superior)
- MongoDB Atlas ou servidor local MongoDB

### Passos para Instalação

1. **Clone o repositório**:
   ```bash
   git clone https://github.com/seu-usuario/quicknotes.git
   cd quicknotes
   ```

2. **Configuração do Backend**:
   ```bash
   cd server
   npm install
   ```
   - Crie um arquivo `.env` no diretório `server` e adicione:
     ```env
     MONGO_URI=<sua-string-de-conexão-do-MongoDB>
     PORT=5000
     ```
   - Inicie o servidor:
     ```bash
     npm start
     ```

3. **Configuração do Frontend**:
   ```bash
   cd ../client
   npm install
   npm start
   ```

4. **Acesse o aplicativo**:
   - Frontend: `http://localhost:3000`
   - Backend: `http://localhost:5000/api/notes`

## APIs Disponíveis

### Criar uma Nota
**POST** `/api/notes`
- **Body:**
  ```json
  {
    "title": "Minha Nota",
    "content": "Conteúdo da nota."
  }
  ```
- **Resposta:**
  ```json
  {
    "_id": "unique-id",
    "title": "Minha Nota",
    "content": "Conteúdo da nota.",
    "createdAt": "2024-12-12T10:00:00.000Z"
  }
  ```

### Listar Todas as Notas
**GET** `/api/notes`
- **Resposta:**
  ```json
  [
    {
      "_id": "unique-id",
      "title": "Nota 1",
      "content": "Conteúdo 1",
      "createdAt": "2024-12-12T10:00:00.000Z"
    },
    {
      "_id": "unique-id-2",
      "title": "Nota 2",
      "content": "Conteúdo 2",
      "createdAt": "2024-12-12T11:00:00.000Z"
    }
  ]
  ```

### Atualizar uma Nota
**PUT** `/api/notes/:id`
- **Body:**
  ```json
  {
    "title": "Nota Atualizada",
    "content": "Conteúdo atualizado."
  }
  ```
- **Resposta:**
  ```json
  {
    "_id": "unique-id",
    "title": "Nota Atualizada",
    "content": "Conteúdo atualizado.",
    "createdAt": "2024-12-12T10:00:00.000Z"
  }
  ```

### Excluir uma Nota
**DELETE** `/api/notes/:id`
- **Resposta:**
  ```json
  {
    "message": "Nota excluída com sucesso."
  }
  ```

## Contribuição
Se desejar contribuir, siga estes passos:
1. Fork o repositório.
2. Crie uma branch para sua feature (`git checkout -b minha-feature`).
3. Faça commit das mudanças (`git commit -m 'Adiciona nova feature'`).
4. Envie para a branch principal (`git push origin minha-feature`).
5. Abra um Pull Request.


