# 🌩️ Resumo – Fundamentos Essenciais da Infraestrutura AWS  

## 🔹 Regiões  
- Cada **região (region)** é projetada para ser isolada das outras → aumenta tolerância a falhas e estabilidade.  
- Uma região é composta por **2 ou mais zonas de disponibilidade (AZs)**.  
- Fatores importantes ao escolher uma região:  
  - **Compliance** (requisitos legais e regulatórios)  
  - **Disponibilidade de serviços** (nem todos estão em todas as regiões)  
  - **Custo** (pode variar entre regiões)  
  - **Latência** (proximidade dos usuários finais)  

---

## 🔹 Zonas de Disponibilidade (AZs)  
- São **conjuntos de data centers redundantes**, projetados para operar de forma independente em caso de falhas em outras zonas.  
- Cada região possui **várias AZs isoladas fisicamente, mas conectadas logicamente**, garantindo **alta disponibilidade**.  
- **Isolamento entre regiões** → cada região é independente, não há replicação automática entre elas (deve ser configurada pelo administrador).  
- Exemplo: região **US-West (Norte da Califórnia)** possui AZs **us-west-1a, us-west-1b e us-west-1c**.  
- Ao criar uma conta AWS, o usuário tem acesso a várias regiões e pode escolher onde rodar seus recursos (ex.: instâncias EC2 na Europa para menor latência ou atender requisitos legais).  

---

## 🔹 Serviços Gerenciados  
- AWS é uma plataforma de nuvem **altamente escalável e robusta**, usada por empresas como **Amazon.com, Netflix e bancos**.  
- Serviços gerenciados permitem que a AWS cuide da **infraestrutura**, enquanto o cliente foca no **uso e configuração** do serviço.  
- Isso simplifica a operação e reduz a carga administrativa.  

---

👉 **Em resumo:** este curso detalha os **conceitos fundamentais da AWS**, como **regiões, zonas de disponibilidade e serviços gerenciados**, explicando como esses elementos garantem **resiliência, escalabilidade e flexibilidade** para diferentes necessidades de negócios.  
