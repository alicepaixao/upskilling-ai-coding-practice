<div align="center">

<img src="https://bit.ly/4eBWUgq" alt="Tropicália AI Logo" width="120" />

# UPSKILLING AI CODING PRACTICE

**Base de estudos, desafios práticos e mentoria em Inteligência Artificial aplicada ao desenvolvimento de software**

---

| 🚀 | Aprenda IA aplicada ao ciclo de desenvolvimento real: geração de código, refatoração, testes e revisão com IA. |
|----|---------------------------------------------------------------------------------------------------------------|

---

## Sobre as autoras e mentores

Somos **Alice Paixão** e **Silas Fernandes**, especialistas em backend, IA aplicada, DevOps e ensino de tecnologia. Atuamos como mentores, instrutores e consultores para empresas e profissionais que querem acelerar sua jornada em IA e desenvolvimento moderno.

**Quer transformar seu time ou aprender IA aplicada na prática? Entre em contato!**

[LinkedIn Alice](https://www.linkedin.com/in/alicepaixao/) | [E-mail Alice](mailto:paixaogomesalice@gmail.com)  
[LinkedIn Silas](https://www.linkedin.com/in/silasfernandes/) | [E-mail Silas](mailto:s.fernandes.silas@gmail.com)

[LinkedIn Tropicália AI](https://www.linkedin.com/company/tropicalia-ai) | [Site Tropicália AI](https://tropicalia.ai/)

---

> **Este repositório foi adaptado a partir do [node-express-boilerplate](https://github.com/hagopj13/node-express-boilerplate)**

<div align="center">

| Propósito |
|-----------|
| Explorar como aplicar ferramentas de inteligência artificial no ciclo de desenvolvimento real, com foco em geração de código, refatoração, testes e revisão com IA. |

</div>

---

## Instalação e Configuração

Clone o repositório:

```bash
git clone https://github.com/alicepaixao/upskilling-ai-coding-practice.git
cd upskilling-ai-coding-practice
```

Instale as dependências:

```bash
yarn install
```

Configure as variáveis de ambiente:

```bash
cp .env.example .env
# Edite o arquivo .env conforme necessário
```

## Índice

- [Funcionalidades](#funcionalidades)
- [Comandos](#comandos)
- [Variáveis de Ambiente](#variaveis-de-ambiente)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Documentação da API](#documentacao-da-api)
- [Tratamento de Erros](#tratamento-de-erros)
- [Validação](#validacao)
- [Autenticação](#autenticacao)
- [Autorização](#autorizacao)
- [Logs](#logs)
- [Plugins Customizados do Mongoose](#plugins-customizados-do-mongoose)
- [Lint](#lint)
- [Contribuindo](#contribuindo)

## Funcionalidades

- **Banco NoSQL**: Modelagem de dados MongoDB usando Mongoose
- **Autenticação e autorização**: usando Passport
- **Validação**: validação de dados das requisições com Joi
- **Logs**: usando Winston e Morgan
- **Testes**: testes unitários e de integração com Jest
- **Tratamento de erros**: mecanismo centralizado
- **Documentação da API**: com swagger-jsdoc e swagger-ui-express
- **Gerenciamento de processos**: com PM2
- **Gerenciamento de dependências**: com Yarn
- **Variáveis de ambiente**: usando dotenv e cross-env
- **Segurança**: headers HTTP seguros com Helmet
- **Sanitização**: proteção contra XSS e injeção de queries
- **CORS**: habilitado com cors
- **Compressão**: gzip com compression
- **CI**: integração contínua com Travis CI
- **Suporte a Docker**
- **Cobertura de código**: com coveralls
- **Qualidade de código**: com Codacy
- **Git hooks**: com husky e lint-staged
- **Lint**: com ESLint e Prettier
- **Editor config**: configuração consistente com EditorConfig

## Comandos

### Executando localmente

```bash
yarn dev
```
> Inicia o servidor em modo desenvolvimento com recarregamento automático (nodemon).

### Executando em produção

```bash
yarn start
```
> Inicia o servidor em modo produção usando PM2.

### Testes

```bash
yarn test
```
> Executa todos os testes unitários e de integração.

```bash
yarn test:watch
```
> Executa todos os testes em modo observação (watch).

```bash
yarn coverage
```
> Gera relatório de cobertura de testes.

### Docker

```bash
yarn docker:dev
```
> Sobe o ambiente de desenvolvimento com Docker (inclui MongoDB).

```bash
yarn docker:prod
```
> Sobe o ambiente de produção com Docker.

```bash
yarn docker:test
```
> Executa os testes em ambiente Docker.

### Lint e Prettier

```bash
yarn lint
```
> Executa o ESLint para análise de código.

```bash
yarn lint:fix
```
> Corrige automaticamente problemas encontrados pelo ESLint.

```bash
yarn prettier
```
> Verifica a formatação do código com Prettier.

```bash
yarn prettier:fix
```
> Corrige a formatação do código com Prettier.

## Variáveis de Ambiente

As variáveis de ambiente podem ser encontradas e modificadas no arquivo `.env`. Valores padrão:

```bash
# Porta
PORT=3001

# URL do MongoDB
MONGODB_URL=mongodb://127.0.0.1:27017/node-boilerplate

# JWT
JWT_SECRET=thisisasamplesecret
JWT_ACCESS_EXPIRATION_MINUTES=30
JWT_REFRESH_EXPIRATION_DAYS=30

# Configuração SMTP para serviço de e-mail
SMTP_HOST=email-server
SMTP_PORT=587
SMTP_USERNAME=email-server-username
SMTP_PASSWORD=email-server-password
EMAIL_FROM=support@yourapp.com
```

## Estrutura do Projeto

```
src\
 |--config\         # Variáveis de ambiente e configurações
 |--controllers\    # Controllers das rotas
 |--docs\           # Arquivos Swagger
 |--middlewares\    # Middlewares customizados do Express
 |--models\         # Modelos Mongoose (camada de dados)
 |--routes\         # Rotas
 |--services\       # Lógica de negócio
 |--utils\          # Utilitários
 |--validations\    # Schemas de validação
 |--app.js          # App Express
 |--index.js        # Ponto de entrada
```

## Documentação da API

Para ver a lista de APIs disponíveis e suas especificações, rode o servidor e acesse `http://localhost:3001/v1/docs` no navegador. Esta página é gerada automaticamente usando as definições Swagger escritas nos arquivos de rota.

### Endpoints

**Rotas de autenticação:**  
`POST /v1/auth/register` - registrar  
`POST /v1/auth/login` - login  
`POST /v1/auth/refresh-tokens` - renovar tokens  
`POST /v1/auth/forgot-password` - enviar e-mail de redefinição de senha  
`POST /v1/auth/reset-password` - redefinir senha  
`POST /v1/auth/send-verification-email` - enviar e-mail de verificação  
`POST /v1/auth/verify-email` - verificar e-mail

**Rotas de usuário:**  
`POST /v1/users` - criar usuário  
`GET /v1/users` - listar usuários  
`GET /v1/users/:userId` - obter usuário  
`PATCH /v1/users/:userId` - atualizar usuário  
`DELETE /v1/users/:userId` - deletar usuário

## Tratamento de Erros

A aplicação possui um mecanismo centralizado de tratamento de erros.

Controllers devem capturar erros e encaminhá-los para o middleware de erro (usando `next(error)`). Para facilitar, pode-se usar o utilitário `catchAsync`:

```javascript
const catchAsync = require('../utils/catchAsync');

const controller = catchAsync(async (req, res) => {
  // este erro será encaminhado para o middleware de erro
  throw new Error('Algo deu errado');
});
```

O middleware de erro envia uma resposta no formato:

```json
{
  "code": 404,
  "message": "Não encontrado"
}
```

Em modo desenvolvimento, a resposta também inclui a stack do erro.

A aplicação possui a classe utilitária `ApiError` para anexar código de resposta e mensagem, podendo ser lançada de qualquer lugar (o `catchAsync` captura):

```javascript
const httpStatus = require('http-status');
const ApiError = require('../utils/ApiError');
const User = require('../models/User');

const getUser = async (userId) => {
  const user = await User.findById(userId);
  if (!user) {
    throw new ApiError(httpStatus.NOT_FOUND, 'Usuário não encontrado');
  }
};
```

## Validação

Os dados das requisições são validados usando [Joi](https://joi.dev/). Os schemas ficam em `src/validations` e são usados nas rotas via middleware `validate`:

```javascript
const express = require('express');
const validate = require('../../middlewares/validate');
const userValidation = require('../../validations/user.validation');
const userController = require('../../controllers/user.controller');

const router = express.Router();

router.post('/users', validate(userValidation.createUser), userController.createUser);
```

## Autenticação

Para exigir autenticação em rotas, use o middleware `auth`:

```javascript
const express = require('express');
const auth = require('../../middlewares/auth');
const userController = require('../../controllers/user.controller');

const router = express.Router();

router.post('/users', auth(), userController.createUser);
```

Essas rotas exigem um token JWT válido no header Authorization usando o esquema Bearer. Se não houver token válido, retorna erro 401.

**Gerando tokens de acesso:**

Um token de acesso é gerado ao registrar (`POST /v1/auth/register`) ou fazer login (`POST /v1/auth/login`). A resposta inclui também o refresh token.

O token de acesso é válido por 30 minutos (configurável via `JWT_ACCESS_EXPIRATION_MINUTES`).

**Renovando tokens de acesso:**

Após expirar, um novo token pode ser gerado via `POST /v1/auth/refresh-tokens` enviando um refresh token válido. A resposta traz novos tokens.

O refresh token é válido por 30 dias (configurável via `JWT_REFRESH_EXPIRATION_DAYS`).

## Autorização

O middleware `auth` também pode exigir permissões específicas:

```javascript
const express = require('express');
const auth = require('../../middlewares/auth');
const userController = require('../../controllers/user.controller');

const router = express.Router();

router.post('/users', auth('manageUsers'), userController.createUser);
```

No exemplo acima, só usuários autenticados com permissão `manageUsers` podem acessar a rota.

As permissões são baseadas em papéis (roles), definidos em `src/config/roles.js`.

Se o usuário não tiver permissão, retorna erro 403.

## Logs

Importe o logger de `src/config/logger.js` (usa Winston):

```javascript
const logger = require('<caminho para src>/config/logger');

logger.error('mensagem'); // nível 0
logger.warn('mensagem'); // nível 1
logger.info('mensagem'); // nível 2
logger.http('mensagem'); // nível 3
logger.verbose('mensagem'); // nível 4
logger.debug('mensagem'); // nível 5
```

No modo desenvolvimento, todos os níveis são exibidos no console. Em produção, apenas info, warn e error.

As requisições HTTP também são logadas automaticamente (usando Morgan).

## Plugins Customizados do Mongoose

O projeto inclui dois plugins customizados para schemas Mongoose, em `src/models/plugins`:

```javascript
const mongoose = require('mongoose');
const { toJSON, paginate } = require('./plugins');

const userSchema = mongoose.Schema(
  {
    /* definição do schema */
  },
  { timestamps: true }
);

userSchema.plugin(toJSON);
userSchema.plugin(paginate);

const User = mongoose.model('User', userSchema);
```

### toJSON

Remove campos como __v, createdAt, updatedAt e qualquer campo com `private: true`, além de substituir _id por id.

### paginate

Adiciona o método estático `paginate` ao schema:

```javascript
const queryUsers = async (filter, options) => {
  const users = await User.paginate(filter, options);
  return users;
};
```

O parâmetro `options` pode conter:

```javascript
const options = {
  sortBy: 'name:desc', // ordenação
  limit: 5, // resultados por página
  page: 2, // número da página
};
```

O método retorna:

```json
{
  "results": [],
  "page": 2,
  "limit": 5,
  "totalPages": 10,
  "totalResults": 48
}
```

## Lint

O projeto usa ESLint e Prettier, seguindo o guia de estilo do Airbnb com modificações. Para alterar configurações, edite `.eslintrc.json` e `.prettierrc.json`.

Arquivos e pastas ignorados devem ser adicionados em `.eslintignore` e `.prettierignore`.

Para manter o estilo consistente entre editores, o projeto inclui `.editorconfig`.

## Contribuindo

Contribuições são muito bem-vindas! Veja o [guia de contribuição](CONTRIBUTING.md).

## Inspirações

- [danielfsousa/express-rest-es2017-boilerplate](https://github.com/danielfsousa/express-rest-es2017-boilerplate)
- [madhums/node-express-mongoose](https://github.com/madhums/node-express-mongoose)
- [kunalkapadia/express-mongoose-es6-rest-api](https://github.com/kunalkapadia/express-mongoose-es6-rest-api)

## Licença

[MIT](LICENSE)
