# Projeto 01 - Gerenciando Instâncias EC2 na AWS
    📘 README — Sistema de Inventário e Alterações de Equipamentos

## O Desafio
Explorar todos os conceitos abordados até aqui, aplicando os conhecimentos adquiridos nas aulas e documentando minha experiência para demonstrar compreensão dos temas discutidos.

## Descrição do Desafio
Consolidar meus conhecimentos em gerenciamento de instâncias EC2 na AWS. O entregável é um repositório organizado contendo anotações e insights adquiridos durante a prática, servindo como material de apoio para os meus estudos e futuras implementações.

## Objetivos de Aprendizagem
- Aplicar os conceitos aprendidos em um ambiente prático; 
- Documentar processos técnicos de forma clara e estruturada;
- Utilizar o GitHub como ferramenta para compartilhamento de documentação técnica.


# 📌 Visão Geral do Projeto

Este projeto apresenta a arquitetura de um sistema de automação para gerenciar equipamentos físicos.

A ideia central é disponibilizar um dashboard acessível via navegador, que permite acompanhar informações dos equipamentos e suas alterações em tempo real. O sistema integra aplicações On Premises (Inventário e Software de Alterações) com serviços em nuvem da AWS, garantindo escalabilidade, monitoramento e notificações automáticas.

## 🖼️ Arquitetura do Sistema

Você pode visualiar a imagem da Arquitetura no caminho abaixo. Ou também, você pode baixar a pasta Projeto01 na sua máquina e abrir em seu navegador o arquivo index.html que mostra a explicação de cada componente de uma forma mais dinâmica.
[(Projeto01)](https://github.com/laisrabello/code-girls-bootcamp-2025/tree/main/projects/Projeto01)

## 🔎 Explicação do Fluxo

O Usuário acessa o dashboard a partir do navegador.

O CloudFront entrega o conteúdo do dashboard hospedado no S3.

Caso o usuário precise consultar ou registrar informações, a requisição segue pelo API Gateway, que encaminha para o Lambda.

O Lambda atua como orquestrador, integrando-se com:

Inventário de Equipamentos (On Premises) para consultas de dados.

Software de Alterações (On Premises) para registro e consulta de alterações.

Alterações ou eventos relevantes são enviados para o EventBridge, que os distribui para diferentes destinos:

SES (Simple Email Service) → envia notificações por e-mail.

Webhook Teams → integra alertas diretamente no Microsoft Teams.

AppSync/WebSocket → atualiza o dashboard em tempo real para os usuários.

## Componentes da Arquitetura

#### 👤 Usuário

Acessa o sistema por meio de um navegador e visualiza o dashboard.

#### 🌐 CloudFront

Serviço de CDN (Content Delivery Network) que distribui o dashboard de forma rápida e segura, reduzindo latência e aumentando a disponibilidade.

#### 🗂️ S3 (Simple Storage Service)

Armazena os arquivos estáticos do dashboard (HTML, CSS, JS).

#### 🚪 API Gateway

Ponto de entrada para as requisições feitas pelo usuário. Garante controle, segurança e escalabilidade para as chamadas de API.

#### 🖥️ Lambda

Funções serverless que processam as requisições, aplicam regras de negócio e fazem a integração entre os serviços da nuvem e os sistemas On Premises.

#### 🗄️ Inventário de Equipamentos (On Premises)

Banco de dados/sistema local que mantém informações detalhadas dos equipamentos.

#### 🔧 Software de Alterações (On Premises)

Sistema local responsável por registrar alterações realizadas nos equipamentos.

#### 🔔 EventBridge

Barramento de eventos que recebe alterações do sistema e as distribui para diferentes destinos de acordo com regras configuradas.

#### 📩 SES (Simple Email Service)

Serviço de envio de e-mails, usado para notificar os usuários sobre alterações relevantes no inventário.

#### 💬 Webhook Teams

Integração com o Microsoft Teams para envio de notificações diretamente em canais de comunicação da equipe.

#### 🔄 AppSync / WebSocket

Responsável por atualizar em tempo real o dashboard do usuário sempre que um novo evento ocorre.

## 🚀 Benefícios da Arquitetura

Escalabilidade: Uso de Lambda e EventBridge garante que o sistema responda sob demanda.

Baixa latência: CloudFront melhora a experiência do usuário.

Confiabilidade: Integração entre On Premises e AWS de forma resiliente.

Monitoramento em tempo real: Atualização automática do dashboard via WebSockets.

Comunicação eficaz: Notificações entregues por e-mail e via Teams.

