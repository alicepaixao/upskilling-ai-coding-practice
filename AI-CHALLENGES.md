# 📚 Upskilling AI in Development – Challenge Log

**Repositório:** [github.com/alicepaixao/upskilling-ai-coding-practice](https://github.com/alicepaixao/upskilling-ai-coding-practice)  
**Base:** [github.com/hagopj13/node-express-boilerplate](https://github.com/hagopj13/node-express-boilerplate)

> **Objetivo:**
> Explorar como aplicar ferramentas de inteligência artificial no ciclo de desenvolvimento real, focando em geração de código, refatoração, testes e revisão com IA.

**Tag comum:** `#referencia-em-ai-dev`

---

## 🎯 1. Refatoração com ChatGPT (Princípio da Responsabilidade Única - SRP)

**Feature:**
> Separar responsabilidades do controller de autenticação (`auth.controller.js`), organizando a lógica de validação, geração de token e resposta HTTP em serviços distintos.

- **Ferramenta:** ChatGPT
- **Prompt usado:**
  > "Refatore este controller Express para aplicar o princípio de responsabilidade única. Separe a lógica de validação, geração de token e resposta HTTP."
- **Output:**
  - Criado `authValidator.js` para validar credenciais
  - Criado `tokenService.js` para geração de JWT
  - `auth.controller.js` refatorado para apenas orquestrar os serviços
- **Riscos considerados:**
  - Quebra de autenticação em ambientes legados
  - Cobertura de testes comprometida se funções mudarem de assinatura

---

## 🧪 2. Geração de testes com GitHub Copilot

**Feature:**
> Criar testes unitários automatizados para `auth.service.js`.

- **Ferramenta:** GitHub Copilot
- **Prompt indireto:**
  > Ao digitar `describe('AuthService', () => {`, o Copilot sugeriu blocos `it` com casos de sucesso e erro.
- **Output:**
  - Arquivo `tests/unit/auth.service.test.js`
  - Casos de teste para login válido, inválido e usuário não encontrado
- **Riscos considerados:**
  - Testes falsos positivos por lógica incorreta da IA
  - Necessidade de mocks manuais com `jest`

---

## 🧾 3. Geração de documentação automática com JSDoc

**Feature:**
> Documentar `user.service.js` com anotações de tipo, descrição de funções e parâmetros.

- **Ferramentas:** ChatGPT + Copilot
- **Prompt usado:**
  > "Adicione comentários JSDoc explicando cada função e seus parâmetros neste serviço."
- **Output:**
  - Comentários gerados com descrição das funções e tipos esperados
  - Padrão JSDoc adotado para facilitar futuras integrações com Swagger
- **Riscos considerados:**
  - IA pode gerar descrições genéricas ou vagas
  - Reforçada revisão manual após geração

---

## 🔐 4. Criação do endpoint `GET /users/me`

**Feature:**
> Criar endpoint protegido que retorna os dados do usuário autenticado via JWT.

- **Ferramenta:** GitHub Copilot
- **Prompt usado:**
  > "Implemente uma rota Express que retorna os dados do usuário logado, usando middleware de autenticação JWT."
- **Output:**
  - Rota adicionada a `user.route.js`
  - Middleware reutilizado de `auth.middleware.js`
  - Dados do usuário extraídos do token
- **Riscos considerados:**
  - Exposição de dados sensíveis sem filtro
  - Necessidade de controle de escopo do token

---

## 🧠 5. Revisão com Jule AI

**Feature:**
> Enviar `auth.service.js` para revisão via Jule AI, avaliando sugestões de melhoria, boas práticas e refatorações.

- **Ferramenta:** Jule AI ([https://jule.ai](https://jule.ai))
- **Prompt indireto:**
  > Arquivo submetido para análise automática contextual no editor.
- **Output:**
  - Renomeação sugerida de funções para maior clareza
  - Sugestão de mover mensagens de erro para arquivo `constants.js`
  - Algumas sugestões ignoradas por não considerar contexto do projeto
- **Riscos considerados:**
  - Confiança cega em sugestões genéricas
  - IA pode ignorar restrições de negócio ou segurança

---

## 👩‍🏫 6. PR Educacional com base na revisão da IA

**Feature:**
> Aplicar (ou rejeitar) as sugestões feitas pela IA em um Pull Request, justificando tecnicamente cada decisão.

- **Ferramenta:** Jule AI + GitHub
- **Instruções:**
  1. Leia os comentários do Jule AI simulados em `user.service.js`
  2. Crie uma branch e abra um PR
  3. Justifique quais sugestões foram aplicadas ou não, explicando tecnicamente
- **Objetivo:**
  - Treinar argumentação técnica, pensamento crítico e boas práticas de revisão de código com IA no fluxo real de Pull Request.

---

## 💻 7. Geração de função com Cursor.sh

**Feature:**
> Criar a função `resetPassword(email)` no `auth.service.js`, utilizando geração assistida pelo Cursor.sh com IA contextual.

- **Ferramenta:** Cursor.sh ([https://cursor.sh](https://cursor.sh))
- **Prompt indireto:**
  > Função foi iniciada com `async resetPassword(email) {` e a IA sugeriu um fluxo completo com verificação de e-mail e envio de token.
- **Output:**
  - Função criada parcialmente com IA
  - Ajustes feitos para adicionar lógica de expiração e segurança
  - Integração com serviço de e-mail `email.service.js`
- **Riscos considerados:**
  - IA pode omitir validações críticas
  - Sugestões precisam sempre de revisão humana antes de commit

---

## 📌 Todos os desafios são abertos

Sinta-se livre para clonar o repositório, experimentar, adaptar e ampliar as tarefas.  
Esse material foi criado como parte da aula **"Tornando-se Referência em AI no Ciclo de Desenvolvimento de Software"** e pode ser usado para estudo, prática ou portfólio. 