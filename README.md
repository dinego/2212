# Desafio técnico — Estagiário / Júnior (Angular)

Bem-vindo(a). Este desafio avalia familiaridade com ambiente de desenvolvimento, Angular básico, Git e GitHub. O objetivo é **aprendizado**: se algo bloquear, use a seção **Se der erro** e peça ajuda no canal indicado no final — não é uma competição sem apoio.

**Tempo estimado:** cerca de 2 a 4 horas se você já usa terminal e editor; reserve **mais tempo** se for a primeira vez com **branch** e **Pull Request** — isso é normal.

---

## O que é obrigatório e o que é bônus

| Obrigatório | Bônus (opcional, pontos extras) |
|-------------|----------------------------------|
| Clonar o repositório, instalar dependências e rodar o projeto localmente | Rota `/login` e link no menu |
| Criar um componente de login com formulário simples (template-driven) | Estilo/CSS alinhado ao app, validação `required`, mensagem se campo vazio, botão desabilitado até preencher |
| Exibir o login na primeira tela (via `app`, sem precisar de rota) | — |
| `console.log` dos valores ao enviar **e** mensagem visível na página | — |
| Branch, commit e Pull Request conforme instruções | — |

---

## Pré-requisitos

- Conta no [GitHub](https://github.com/)
- Editor de código (por exemplo, VS Code) e terminal
- Se **nunca** criou branch nem abriu um PR, reserve tempo extra — as etapas estão descritas abaixo

---

## Parte 1 — Ambiente

### Node.js (LTS)

1. Baixe e instale o **Node.js LTS** a partir do site oficial: [https://nodejs.org/](https://nodejs.org/)
2. Feche e abra de novo o terminal (ou reinicie o computador se necessário).
3. Confira:

```bash
node -v
npm -v
```

Use uma versão **compatível** com o projeto. Se o **README** do repositório pedir uma versão específica do Node, **siga o README**.

### Angular CLI

1. Leia a documentação oficial da CLI se quiser contexto: [https://angular.dev/tools/cli](https://angular.dev/tools/cli)
2. Instale a CLI globalmente:

```bash
npm install -g @angular/cli
```

3. Confira:

```bash
ng version
```

Se o README do projeto indicar outro procedimento, priorize o README.

---

## Parte 2 — Repositório

Substitua a URL abaixo pela URL **real** do repositório do desafio:

```bash
git clone https://github.com/SEU-USUARIO/SEU-REPO.git
cd SEU-REPO
```

(Use o nome real da pasta que o `git clone` criar.)

---

## Parte 3 — Dependências e execução

Na pasta do projeto:

```bash
npm install
```

Suba o servidor de desenvolvimento. O mais comum é:

```bash
ng serve
```

Se o `package.json` tiver um script diferente (ex.: `npm start`), **use o que o README do repositório indicar**.

Abra o navegador em [http://localhost:4200](http://localhost:4200/) (ou na porta que o terminal mostrar).

---

## Se der erro (referência rápida)

- **`node` ou `npm` não encontrado:** confira se instalou o Node LTS e **reabriu o terminal** após instalar.
- **`ng` não é reconhecido:** confirme `npm install -g @angular/cli`, reinicie o terminal; no Windows, às vezes é preciso reiniciar a sessão ou verificar o PATH.
- **`npm install` falha:** teste rede/VPN; apague `node_modules` e o arquivo de lock **só se o responsável pelo projeto autorizar** — em dúvida, peça ajuda antes.
- **Porta 4200 em uso:** rode em outra porta, por exemplo:

```bash
ng serve --port 4300
```

- **Erro de versão do Node:** alinhe com a versão pedida no README ou no `engines` do `package.json`, se existir.

---

## Parte 4 — Entrega obrigatória: componente de login

### Criar o componente

Gere um componente (ajuste o caminho se o time pedir outro):

```bash
ng generate component login
```

Isso costuma criar o seletor `app-login` (confira o prefixo no `angular.json` se for diferente).

### Formulário (template-driven)

Use **apenas** formulário dirigido por template:

- Importe **`FormsModule`**:
  - Se o projeto usar componentes **standalone** (padrão atual do Angular CLI), adicione `FormsModule` ao array **`imports`** do `@Component` do `login`.
  - Se o projeto usar **NgModule**, importe `FormsModule` no módulo que declara o `LoginComponent`, conforme o template do repositório.

- Campos:
  - **Usuário** ou **e-mail** (um campo de texto)
  - **Senha** (input `type="password"`)

Use **`ngModel`** nos campos (não é necessário Reactive Forms).

### Botão Entrar

Ao clicar em **Entrar**:

1. Faça **`console.log`** com os valores do formulário (ou de um objeto simples que represente usuário e senha).
2. Mostre uma **mensagem visível na página** (por exemplo: “Formulário enviado — veja o console do navegador (F12).”).

**Não** integre com API, HTTP nem autenticação real.

### Obrigatório: ver na primeira tela

Inclua o seletor do seu componente no template do **`app`** para o login aparecer ao abrir [http://localhost:4200](http://localhost:4200/), **sem depender de rota**.

Exemplo (o prefixo pode ser `app` ou outro — use o que o seu componente gerou):

```html
<app-login></app-login>
```

Coloque isso em `app.component.html` (ou no container que o README indicar).

---

## Bônus (opcional)

- Configurar **rota** `/login` e um **link** no menu ou na home para essa rota (não substitui a exibição na home se o time quiser ambos — aqui o mínimo já foi cumprido com o trecho acima).
- Melhorar layout com CSS consistente com o restante do app.
- Validação: `required`, mensagem se campo vazio, ou botão desabilitado até os campos válidos.

---

## Parte 5 — Git: branch, commit e push

1. Crie uma branch (troque `seu-nome` pelo seu nome ou usuário):

```bash
git checkout -b feature/desafio-login-seu-nome
```

2. Adicione as alterações e faça o commit com mensagem clara:

```bash
git add .
git commit -m "feat: adiciona componente de login com formulário template-driven"
```

(Outras mensagens em português ou inglês são aceitáveis, desde que **descrevam** o que foi feito.)

3. Envie a branch para o GitHub:

```bash
git push -u origin feature/desafio-login-seu-nome
```

---

## Parte 6 — Pull Request

1. No GitHub, abra um **Pull Request** da sua branch para a branch base do projeto.
2. **Branch base (placeholder):** abra o PR contra **`main`** **ou** **`develop`**, conforme instrução do time ou do README. Se não souber, pergunte no canal de dúvidas.

Sugestão de descrição no PR:

- O que foi feito (componente de login, `FormsModule`, mensagem + `console.log`).
- Como testar (`npm install`, `ng serve`, abrir `localhost`, preencher e clicar em Entrar).
- Prints opcionais da tela.

Checklist mental antes de marcar como pronto:

- [ ] Projeto sobe sem erro localmente
- [ ] Login visível na home (primeira tela)
- [ ] Botão Entrar mostra mensagem na página e registra valores no console
- [ ] Branch nomeada de forma clara; commit com mensagem útil
- [ ] PR aberto para a branch base correta

---

## Critérios de aceite (resumo)

1. Repositório clonado; `npm install` executado; aplicação roda localmente.
2. Existe componente de login com campos usuário/e-mail e senha (`type="password"`).
3. Uso de **template-driven** (`FormsModule` + `ngModel`).
4. Ao enviar: **mensagem na tela** + **`console.log`** dos dados (sem API).
5. Seletor do componente incluído no template do **`app`** para aparecer em `http://localhost:4200`.
6. PR aberto com branch dedicada e descrição que permita revisar o trabalho.

---

## Dúvidas

**Canal / contato (placeholder):** _preencha aqui o Slack, e-mail ou nome da pessoa responsável pelo processo._

Quando o repositório real existir, atualize neste arquivo:

- URL do `git clone`
- Branch base exata para o PR (`main` / `develop`)
- Qualquer regra adicional do time (prefixo do projeto, pasta do componente, etc.)

Boa sorte.
