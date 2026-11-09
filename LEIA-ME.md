# Entrelinhas — Brás Cubas

Protótipo educacional de plano de aula, apresentação e narrativa interativa sobre o episódio do emplasto em *Memórias Póstumas de Brás Cubas*.

## Arquivos do projeto

- `index.html` — o aplicativo completo, em um único arquivo; abra-o com Chrome, Firefox ou outro navegador atual.
- `plano-base-para-google-docs.docx` — cópia inicial do plano, com a rubrica e os seis nomes preenchidos. Ela **não acompanha automaticamente** as edições feitas no site. Para gerar um documento atualizado, use o botão dentro do aplicativo.
- `LEIA-ME.md` — este guia.

O plano prevê uma aula de **55 minutos**; a apresentação de **40 minutos** simula parte da aula. Os seis nomes estão preenchidos, mas é necessário confirmar com a professora se o limite do grupo é de 4, 5 ou 6 integrantes e escolher a quantidade no plano. A escola-campo e a turma ainda devem ser completadas.

## Abrir o projeto no computador

1. Extraia o arquivo ZIP. Não tente editar o `index.html` enquanto ele estiver dentro do ZIP.
2. Abra a pasta `entrelinhas-bras-cubas` extraída.
3. Dê dois cliques em `index.html`. Ele abre no navegador, sem instalar dependências e sem servidor.
4. Entre em **Plano de aula**, configure o tamanho do grupo e edite os campos.

O aplicativo usa o armazenamento local do navegador. As edições feitas em um computador não são enviadas aos colegas e não passam automaticamente do arquivo local para a versão hospedada no GitHub. Guardar uma cópia exportada é recomendável. As fontes Google usam internet; sem conexão, o site usa fontes alternativas do sistema.

## Abrir o plano no Google Docs

### Opção A — plano-base já incluído no ZIP

1. Acesse `https://drive.google.com/` e entre na sua conta Google.
2. Clique em **Novo → Upload de arquivo** e escolha `plano-base-para-google-docs.docx` da pasta extraída.
3. Após o upload, abra o arquivo com **Documentos Google**. Dependendo da configuração do Drive, clique duas vezes ou clique com o botão direito e escolha **Abrir com → Documentos Google**.
4. Se desejar convertê-lo ao formato nativo do Google, no editor procure **Arquivo → Salvar como Documentos Google**. O nome dos menus pode variar conforme a interface.
5. Edite e compartilhe o documento com os integrantes.

### Opção B — exportar sua versão atualizada

1. Abra o `index.html` extraído no navegador e entre em **Plano de aula**.
2. Faça as alterações necessárias.
3. Clique em **Baixar para Google Docs (.docx)** e aguarde o download.
4. No Google Drive, faça upload do arquivo baixado e abra-o conforme os passos da opção A.

O botão **Copiar texto formatado** é uma alternativa: cole o conteúdo em um documento do Google Docs. Se o navegador bloquear a cópia automática, aparecerá uma janela com o conteúdo selecionado: use Ctrl+C (ou Cmd+C no Mac), feche a janela e cole no Docs.

**Se o download não começar:** verifique se o navegador bloqueou downloads. Se estiver usando um visualizador embutido que não permite downloads, extraia o ZIP e abra o `index.html` diretamente no navegador. O `.docx` incluído no ZIP também pode ser enviado ao Drive imediatamente. A abertura no Google Docs não foi testada neste ambiente; revise a formatação após a importação.

## Publicar no GitHub usando Git

### 1. Antes de começar

- Tenha uma conta no GitHub e o Git instalado: `https://git-scm.com/downloads`.
- Entre no GitHub e crie um repositório chamado, por exemplo, `entrelinhas-bras-cubas`.
- Para seguir exatamente os comandos abaixo, crie o repositório **vazio**: não marque as opções de criar README, `.gitignore` ou licença no GitHub. O README já está no ZIP como `LEIA-ME.md`.
- Escolha **Private** se não quiser expor os nomes e arquivos publicamente. Um repositório **Public** pode ser visto por qualquer pessoa. Os nomes aparecem tanto no HTML como no documento-base.
- As instruções abaixo usam `SEU_USUARIO` como exemplo: substitua pelo seu nome de usuário real do GitHub.

### 2. Extraia e entre na pasta do projeto

Se o ZIP estiver na pasta Downloads, use um dos blocos abaixo. Se ele estiver em outro local, ajuste o caminho. Caso já tenha extraído o ZIP, pule o comando de extração e apenas entre na pasta.

**Windows — PowerShell:**

```powershell
cd "$HOME\Downloads"
Expand-Archive -Path ".\entrelinhas-bras-cubas.zip" -DestinationPath "."
cd ".\entrelinhas-bras-cubas"
```

**macOS ou Linux — Terminal:**

```bash
cd ~/Downloads
unzip entrelinhas-bras-cubas.zip
cd entrelinhas-bras-cubas
```

Confira que está na pasta correta: no Windows execute `dir`; no macOS/Linux execute `ls`. Você deve ver `index.html`, `plano-base-para-google-docs.docx` e `LEIA-ME.md`.

### 3. Configure sua identidade no Git, se ainda não tiver configurado

Substitua os dois valores entre aspas pelos seus dados. Este endereço aparecerá nos metadados dos commits; você pode usar o e-mail `noreply` configurado no GitHub se preferir não expor seu e-mail pessoal.

```bash
git config --global user.name "Seu nome"
git config --global user.email "seu-email@example.com"
```

### 4. Envie os arquivos

Execute os comandos **na ordem**, dentro da pasta extraída. No endereço do repositório, troque `SEU_USUARIO` pelo seu usuário e, se tiver escolhido outro nome para o repositório, troque também `entrelinhas-bras-cubas`.

```bash
git init
git add .
git commit -m "Adiciona protótipo Entrelinhas"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/entrelinhas-bras-cubas.git
git push -u origin main
```

Se o Git pedir autenticação, conclua o login pelo navegador/gerenciador de credenciais ou use um **personal access token** quando solicitado. O GitHub não aceita a senha da conta como senha do Git via HTTPS. Nunca coloque tokens no arquivo, no comando da URL ou no repositório.

Ao terminar, atualize a página do repositório no GitHub para conferir os arquivos.

### 5. Opcional: publicar como site com GitHub Pages

1. No repositório, abra **Settings → Pages**.
2. Em **Build and deployment**, selecione **Deploy from a branch**.
3. Em **Branch**, escolha `main` e `/ (root)`; clique em **Save**.
4. Aguarde a publicação e abra o endereço exibido na própria página de configurações. Geralmente ele tem o formato `https://SEU_USUARIO.github.io/entrelinhas-bras-cubas/`.

A disponibilidade do GitHub Pages para repositórios privados depende do plano e das configurações da conta/organização. Em um site público, qualquer pessoa com o endereço poderá ver os nomes incluídos. O site publicado não é colaborativo: as edições ficam no navegador de quem as fez.

### 6. Para enviar alterações futuras

Depois de modificar os arquivos da pasta, use:

```bash
git add .
git commit -m "Atualiza plano e apresentação"
git push
```

Alterações feitas apenas nos campos do navegador ficam no armazenamento local: elas **não modificam automaticamente** o arquivo `index.html` nem são enviadas com `git push`. Exporte o `.docx` para compartilhar a versão editada.
