📬 Gmail Intelligent Cleaner
Intelligent Email Governance Automation with n8n
🚀 Overview

O Gmail Intelligent Cleaner é uma automação desenvolvida em n8n com o objetivo de aplicar regras inteligentes na caixa de entrada do Gmail, reduzindo ruído operacional e automatizando tarefas repetitivas.

O workflow executa automaticamente a cada 1 minuto, analisa os e-mails da INBOX e aplica políticas configuráveis de exclusão com base em critérios definidos pelo usuário.

Este projeto demonstra integração com API, lógica condicional em JavaScript e estruturação profissional de automação.

🎯 Problema Resolvido

Caixas de entrada corporativas frequentemente acumulam:

Emails operacionais irrelevantes

Notificações automáticas

Mensagens sem prioridade

Isso gera perda de produtividade e ruído informacional.

Este projeto implementa uma política automatizada de governança de e-mails.

⚙️ Regra Implementada (Versão Atual)

O workflow remove automaticamente emails que:

❌ Não possuem anexos

❌ Não estão marcados como “STARRED”

Essa lógica pode ser facilmente modificada.

🔄 Customização e Escalabilidade

A arquitetura foi construída para permitir personalização completa das regras.

É possível configurar:

📎 Validação de anexos

⭐ Verificação de labels específicas

🏷 Filtro por remetente

📅 Filtro por período

📌 Palavras-chave no assunto

🗂 Outras labels do Gmail

⏱ Frequência de execução

A lógica pode ser editada diretamente no Function Node (JavaScript), transformando o workflow em um mecanismo de regras personalizado.

Isso permite adaptar a solução para:

Times de suporte

Departamentos financeiros

Governança corporativa

Triagem automática inicial

🏗 Arquitetura do Workflow
Cron Trigger (1 min)
        ↓
Gmail – Get All (INBOX)
        ↓
Function Node – Análise JavaScript
        ↓
IF – Validação da Regra
        ↓
Gmail – Delete (Move to Trash)
🧠 Lógica Principal (JavaScript)
return items.map(item => {
  const hasAttachment = item.json.attachments && item.json.attachments.length > 0;
  const isStarred = item.json.labelIds && item.json.labelIds.includes('STARRED');

  const deveriaApagar = !hasAttachment && !isStarred;

  return {
    json: {
      id: item.json.id,
      deveriaApagar
    }
  };
});
🛠 Tecnologias Utilizadas

n8n

Gmail API

JavaScript

🔐 Segurança

Este repositório não contém credenciais.

Para utilizar o projeto é necessário:

Configurar OAuth2 no n8n

Criar suas próprias credenciais Gmail

Nenhuma chave ou token está incluído.

🚀 Como Utilizar

Instalar n8n

Importar o arquivo workflow/gmail-cleaner.json

Configurar credenciais Gmail OAuth2

Ajustar regras conforme necessidade

Ativar workflow

📈 Possíveis Evoluções

Implementação de logs estruturados

Relatório automático de emails removidos

Integração com Slack

Classificação automática por categoria

Aplicação de políticas corporativas avançadas

💼 Competências Demonstradas

Automação de processos

Integração com APIs

Lógica condicional

Estruturação de workflow escalável

Mentalidade de governança e eficiência operacional