# Gerênciando Instâncias EC2 na AWS

## Cenário: 
Necessidade de criar um outro ambiente de qualidade baseado na imagem que foi criado em desenvolvimento. 

## Criação e uso de imagens (AMI)
    ### Imagem de máquina da Amazon (AMI)
    - No Amazon EC2(Elastic Computing Cloud), uma AMI (Amazon Machine Image) é uma imagem de máquina virtual pré-configurada, que inclui as informações necessárias para iniciar uma instância, como o sistema operativo, o servidor de aplicações e as aplicações.

    ### Principais características:
    1. Criação: AMIs podem ser criadas a partir de instâncias em execução ou paradas.
    2. AMIs públicas e privadas: a AWS fornece uma variedade de AMIs públicas, ou você pode criar suas próprias AMIs privadas para segurança e personalização.
    3. Personalização: é possível personalizar sua instância e em seguida criar uma AMI a partir dela.
    4. Iniciar instâncias: para executar instâncias no EC2, seleciona uma AMI. A AMI fornece as informações necessárias para iniciar a instância, como o volume do dispositivo raiz e as permissões de inicialização.
    5. Tipos de AMI: incluindo Amazon Linux, Windows e outros.

## Diferença entre Snapshot e AMI
- Uma AMI faz o backup de um servidor inteiro, incluindo todos os volumes EBS anexados.
- Um Snapshot é uma cópia pontual de um determinado volume. Você tira um snapshot de seus volumes EBS e salvar no armazenamento S3.
