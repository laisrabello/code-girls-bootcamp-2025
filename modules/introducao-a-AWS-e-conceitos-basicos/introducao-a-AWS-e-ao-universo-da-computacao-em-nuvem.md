# 🌩️ Resumo da Unidade – Introdução à AWS e ao Universo da Computação em Nuvem  

### 🔹 Introdução à AWS  
- História, infraestrutura global, modelo de negócio  
- Conceitos: regiões, zonas de disponibilidade, serviços gerenciados  
- Configuração da conta e práticas de segurança  

### 🔹 História da AWS  
- Amazon fundada em **1994** como livraria online por Jeff Bezos  
- Nome **“Amazon”** escolhido por ser o maior rio do mundo (antes pensou em “Cadabra”)  
- AWS lançada em **2006**, oferecendo serviços de infraestrutura em nuvem  

### 🔹 Infraestrutura Global  
- Plataforma **segura, confiável e abrangente** com +200 serviços  
- Conceitos:  
  - **Regiões** → áreas geográficas com múltiplas "Availability Zones"(AZs)  
  - **AZs** → data centers independentes fisicamente, mas interligados logicamente  
- Presença global: **105 zonas de disponibilidade em 33 regiões** (expansão contínua)

  #### Notas pessoais(Laís Rabello):
    ##### Workload
      - Em computação em nuvem, “workload” significa todo o conjunto de recursos, processos e operações que uma aplicação precisa para rodar:
        1. Código da aplicação
        2. Banco de dados
        3. Processamento (CPU, GPU)
        4. Armazenamento
        5. Rede

      👉 Em resumo: workload = aplicação + tudo o que ela consome e processa na nuvem.

    ##### Latência
      - É o tempo que leva para uma requisição sair do usuário → chegar na nuvem → ser processada → voltar a resposta.
      - Principais desafios:
        1. Distância geográfica: se o servidor está em outro continente, a resposta demora mais. Por isso existem CDNs (Content Delivery Networks) e regiões cloud espalhadas pelo mundo.
        2. Sobrecarga de rede e concorrência: muitas requisições ao mesmo tempo podem aumentar a latência. Escalabilidade automática (auto-scaling) é usada para mitigar.
        3. Dependência entre serviços: uma aplicação moderna pode chamar dezenas de microserviços (login, pagamento, estoque...). Cada chamada encadeada aumenta a latência total.
        4. Processamento pesado no backend: workloads de IA, Big Data ou análises complexas exigem muito processamento, impactando o tempo de resposta.
        5. Balanço entre custo e performance: reduzir latência geralmente significa investir em mais recursos (máquinas mais potentes, servidores mais próximos do usuário) e isso nem sempre é viável financeiramente. 

### 🔹 Modelo de Negócio AWS  
- OPEX → pagamento apenas pelo uso operacional
- CAPEX → comprar toda infraestrutura antes de começar usar
- Flexibilidade de preços e escalabilidade  
- Grande variedade de serviços (computação, banco de dados, IoT, ML, analytics etc.)
- Cloud Pública:
  1. Maior risco de privacidade
  2. Alto desempenho
  3. Acesso imediato
  4. Baixo custo
  5. Escalabilidade
- Cloud Privada:
  1. Segurança
  2. Controle total
  3. Alto investimento
  4. Custo contínuo da operação
- Cloud Hibrida:
  1. Alto desempenho
  2. Acesso imediato
  3. Baixo custo
  4. Escalabilidade
  5. Segurança
  6. Controle total
- Modelos de nuvem: **IaaS, PaaS, SaaS** (diferentes níveis de controle e responsabilidade)
  1. IaaS (MIGRO): infraestrutura como serviço (Ex.: sistema legado, servidor de arquivo, segurança,...)
  2. Paas (CONSTRUO): plataforma como serviço (Ex.: desenvolvimento de aplicação Streaming, Web, decisões de suporte, ...)
  3. Saas (USO): software como serviço (Ex.: E-mail, CRM, ERP, ...)
- Destaque pela **inovação constante** e adaptação ao mercado  
