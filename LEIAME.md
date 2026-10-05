# Dunamis Kids - Inscrições do Evento

Site simples (arquivos estáticos) + banco de dados Firebase (grátis). Hospedagem: GitHub Pages (grátis).

Arquivos:
- `index.html` - o site inteiro
- `firebase-config.js` - onde você cola os dados do seu banco (passo 5)
- `firestore.rules` - regras de segurança do banco (passo 3)

IMPORTANTE: não escreva as senhas de acesso em nenhum arquivo do GitHub, porque o repositório é público.

## PARTE 1 - Criar o banco de dados (Firebase)

1. Entre em https://console.firebase.google.com com sua conta Google. Clique em **Criar um projeto**, dê o nome `dunamis-kids`, desative o Google Analytics e clique em **Criar projeto**.
2. No menu da esquerda, abra **Criação > Firestore Database > Criar banco de dados**. Escolha o local **southamerica-east1 (São Paulo)**, modo **produção**, e clique em **Ativar**.
3. Na aba **Regras** do Firestore, apague tudo, cole o conteúdo do arquivo `firestore.rules` e clique em **Publicar**.
4. Abra **Criação > Authentication > Vamos começar > E-mail/senha**, ative a primeira opção e salve. Na aba **Usuários**, clique em **Adicionar usuário** duas vezes:
   - e-mail `normal@dunamis-kids.app` e, como senha, a senha de acesso normal;
   - e-mail `emanuel@dunamis-kids.app` e, como senha, a senha do acesso que pode excluir.
   (Os e-mails são só identificadores, não precisam existir. As senhas devem ter no mínimo 6 caracteres e ser escritas em letras minúsculas.)
   Depois, em **Authentication > Configurações > Ações do usuário**, desmarque **Ativar criação (cadastro)**, se a opção aparecer.
5. Clique na engrenagem **Configurações do projeto**. Em **Seus aplicativos**, clique no ícone **</>** (Web), dê um apelido, clique em **Registrar app** e copie o bloco `firebaseConfig`. Abra `firebase-config.js` e troque cada `COLE_AQUI` pelo valor correspondente.

## PARTE 2 - Colocar no GitHub

1. Crie uma conta em https://github.com. Clique em **New repository**, nome `dunamis-kids-evento`, marque **Public** e clique em **Create repository**.
2. Na página do repositório, clique em **uploading an existing file**, arraste `index.html`, `firebase-config.js` e `firestore.rules` e clique em **Commit changes**.
3. Vá em **Settings > Pages**. Em **Build and deployment > Source**, escolha **Deploy from a branch**, branch **main**, pasta **/(root)** e clique em **Save**.
4. Espere 1 a 2 minutos. O endereço do site será `https://SEU-USUARIO.github.io/dunamis-kids-evento/`.
5. Volte ao Firebase, em **Authentication > Configurações > Domínios autorizados**, clique em **Adicionar domínio** e coloque `SEU-USUARIO.github.io`.

## PARTE 3 - Testar

1. Abra o endereço do site e faça uma inscrição de teste. Baixe o PDF do ingresso.
2. Entre em **Ver Inscritos (Admin)** com cada senha e confira a lista, a planilha e a validação.
3. Para apagar os testes, entre com a senha do acesso completo e use o botão **Excluir**.

## Como o banco guarda os dados

Coleção `inscritos` (um documento por criança): `nome`, `idade`, `resp` (responsável), `tel`, `alergia` (vazio se não tiver), `presente` (verdadeiro/falso), `presenteEm` (horário da validação), `como` ("QR Code" ou "Manual") e `criadoEm`.
Ver os dados: Firebase > Firestore Database > Dados.

## Atualizar o site depois

No GitHub, abra o arquivo, clique no lápis, edite e clique em **Commit changes**. O site atualiza sozinho em 1 a 2 minutos.

## Observações

- Sem o `firebase-config.js` preenchido, o site funciona em modo de teste: guarda os dados só no aparelho e qualquer senha entra no painel.
- Os dados são de crianças (nome, telefone, alergias). Apague as inscrições depois do evento.
- O plano gratuito do Firebase é suficiente para um evento de igreja.
