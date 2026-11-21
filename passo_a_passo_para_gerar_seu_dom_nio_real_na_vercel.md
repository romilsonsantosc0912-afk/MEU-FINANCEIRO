# Como Gerar o Domínio HTTPS Real do MEU FINANCEIRO na Vercel

O seu aplicativo **MEU FINANCEIRO** ainda não foi publicado na sua conta da Vercel, então o endereço exato **`https://<nome-do-seu-projeto>.vercel.app`** só passa a existir depois que você fizer o deploy na sua conta Vercel (com o nome do projeto que você escolher).

---

## 1. Prepare os arquivos do projeto em uma pasta

Coloque os arquivos do **MEU FINANCEIRO** dentro de uma mesma pasta (por exemplo, `meu-financeiro`):
* `index.html`
* `vercel.json`
* `manifest.json`
* `sw.js`
* `icon.svg`

---

## 2. Publique na Vercel para obter o endereço `.vercel.app` real

### Opção A — Pelo site da Vercel (via GitHub, sem usar terminal)
1. Crie um repositório no **GitHub** (ex.: `meu-financeiro-app`) e envie os arquivos da pasta para a raiz dele.
2. Acesse **[vercel.com](https://vercel.com)** e faça login com sua conta GitHub.
3. Clique em **Add New... > Project**.
4. Clique em **Import** ao lado do repositório criado.
5. Em **Project Name**, você pode escolher o nome que vai compor o domínio (por exemplo, `meu-financeiro-belem` -> gerará `https://meu-financeiro-belem.vercel.app`, caso esteja disponível).
6. Clique em **Deploy** e aguarde concluir.
7. Na tela de conclusão (ou em **Domains** dentro do projeto na Vercel), copie o domínio real exibido (ex.: `meu-financeiro-belem.vercel.app`).

### Opção B — Pelo terminal com a Vercel CLI
1. Abra o terminal dentro da pasta `meu-financeiro`.
2. Rode:
   ```bash
   npx vercel --prod
   ```
3. Responda às perguntas iniciais (login na Vercel, confirmar o diretório e o nome do projeto).
4. Ao final, o terminal exibirá a URL de produção real em **`https://...vercel.app`**.

---

## 3. Cadastre o domínio real no Firebase Authentication

Assim que a Vercel mostrar o domínio real do seu projeto:

1. Abra o **[Firebase Console](https://console.firebase.google.com)** e entre no projeto **`meu-financeiro-aebc7`**.
2. Vá em **Authentication** > aba **Settings** > **Authorized domains**.
3. Clique em **Add domain**.
4. Cole **apenas** o domínio gerado pela Vercel (sem `https://` e sem barra no final), por exemplo:
   `meu-financeiro-belem.vercel.app`
5. Clique em **Add**.
6. Confira também em **Authentication > Sign-in method** se **Google** e **E-mail/senha** estão ativados.

---

## 4. Teste o Login com Google

Abra o endereço `https://` gerado pela Vercel no navegador ou no celular e clique em **Entrar com Google**. Se quiser, cole aqui depois o domínio que a Vercel gerou para eu conferir qualquer detalhe com você.