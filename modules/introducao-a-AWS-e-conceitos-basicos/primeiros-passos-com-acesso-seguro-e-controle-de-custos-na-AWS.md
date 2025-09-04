# 🌩️ Resumo: Primeiros Passos com Acesso Seguro e Controle de Custos na AWS

## Acessando a conta pela primeira vez
- Questão de prova: de que forma que posso criar meus recursos na AWS?
    1. via portal
    2. via AWS SDK
    3. via Cloud Shell

## Entendendo e conhecendo o IAM
- IAM significa Identity and Access Management (Gerenciamento de Identidade e Acesso)
- 📌 Exemplo prático:
    Você tem uma equipe de desenvolvedores e outra de analistas de dados.
        • Os devs precisam criar e modificar instâncias EC2.
        • Os analistas só precisam ler dados do S3.
    Com o IAM, você cria grupos diferentes, aplica políticas adequadas e garante que cada equipe só veja o que precisa.
- Ao criar um usuário IAM, fique atento ao selecionar o tipo de usuário. Atualmente, a AWS passa por uma reformulação no gerenciamento de usuários. São disponibilizadas duas opções:
    1. **Specify a user in Identity Center – Recommended**
        Refere-se ao AWS IAM Identity Center (antigo AWS SSO – Single Sign-On). Recomendado para pessoas que vão acessar o Console da AWS.
    2. **I want to create an IAM user**
        Cria um usuário clássico do IAM (dentro da própria conta AWS). Usado mais para acesso programático (máquinas/aplicações/scripts) ou casos pontuais.
- IAM User (clássico) vs IAM Identity Center (recomendado)
    🟠 IAM User (clássico)
        → Cada pessoa do time teria um usuário criado direto no IAM.
        → Você teria que configurar senha ou chaves de acesso para cada um.
        → Se tiver múltiplas contas AWS, teria que criar o mesmo usuário em cada conta.
        → Atribuir permissões = criar ou anexar policies individuais para cada usuário.
        → Gerenciamento fica mais trabalhoso (imagina trocar 10 senhas/chaves quando alguém sai do time).
        → Bom para: aplicações/sistemas que precisam de chaves de acesso.

    📌 Exemplo:
        → Usuário "joao-dev" com senha + permissões EC2.
        → Usuário "maria-analista" com senha + permissões S3.
        → Se você tiver 3 contas AWS, repete o processo 3 vezes.
    
    🟢 IAM Identity Center (recomendado)
        → Cada pessoa do time tem um login individual no Identity Center
        → Você não cria usuários direto no IAM, e sim no portal central de identidade.
        → Se tiver múltiplas contas AWS, cada usuário já pode receber acesso a todas, sem duplicar nada.
        → Permissões são atribuídas por grupos e perfis de permissão → muito mais organizado.
        → Gerenciamento é simples (se alguém sai, basta desativar a conta no Identity Center).
        → Bom para: pessoas/humanos que acessam console ou CLI.

    📌 Exemplo:
        → Usuário "joao@empresa.com" → grupo Devs → acesso EC2 em conta de desenvolvimento.
        → Usuário "maria@empresa.com" → grupo Analistas → leitura de S3 em todas as contas.
        → Usuário "ana@empresa.com" → grupo Admins → acesso total.

## Aplicando no IAM Políticas e Permissões
- Chave de acesso
    1. Um par de chave de acesso = um usuário IAM
        • Cada usuário IAM pode ter até 2 pares de chaves ativas ao mesmo tempo.
        • Um par de chave (Access Key ID + Secret Access Key) pode ser usado para qualquer um dos casos: CLI, SDK, API, aplicações externas etc.
    2. O que muda é como você usa a chave
        • CLI → você coloca a chave no seu terminal ou configura com aws configure.
        • SDK → você coloca a mesma chave no código da aplicação.
        • Serviços de terceiros → você fornece a chave para autenticar esses serviços com a AWS.
        • Aplicação executada fora da AWS → também usa a mesma chave.
    3. Quando criar mais de uma chave
        • Para rotacionar chaves (uma ativa, outra pronta para substituir quando a primeira expirar).
        • Para uso de automações diferentes que exigem separar credenciais (por segurança).

## Controle de gastos e alertas
- Aprendemos a criar um orçamento de gastos e a programar alertas para cada valor de orçamento

## Formas de Acesso: AWS CLI, Cloud Shell e Console AWS
- Pergunta de prova: quais formas de acessar a plataforma AWS?
    1. Console
    2. CLI
    3. Cloud Shell

## Acesso ao AWS CLI e criação de grupos de usuários
- Aula prática: o que fizemos?
    1. Configuramos usuário administrador e criamos a key de acesso ao CLI AWS
    2. Instalamos na máquina o GitBash e o CLI AWS
    3. Criamos 4 grupos de usuários, com suas permissões, pelo console AWS
    4. Criamos 5 usuários para cada grupo através do CLI. Isso foi feito rodando no GitBash o scriptIAM.sh e um arquivo csv com o nome do usuário, seu grupo de destino e uma senha temporária.
    5. Dessa forma, fizemos nossa primeira automação utilizando o Command Line Interface (CLI).

🔗 [Guia oficial de boas práticas IAM](https://docs.aws.amazon.com/pt_br/IAM/latest/UserGuide/best-practices.html)
