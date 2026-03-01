📬 Gmail Intelligent Cleaner
🚀 Intelligent Email Governance Automation with n8n


📌 Sobre o Projeto

O Gmail Intelligent Cleaner é uma automação desenvolvida em n8n com o objetivo de aplicar regras inteligentes na caixa de entrada do Gmail, reduzindo ruído operacional e automatizando tarefas repetitivas.

O workflow executa automaticamente a cada 1 minuto, analisa os e-mails da INBOX e aplica políticas configuráveis de exclusão com base em critérios definidos pelo usuário.

Este projeto demonstra:

Integração com API

Lógica condicional em JavaScript

Estruturação profissional de automação

Mentalidade de governança de e-mails

🎯 Problema Resolvido

Caixas de entrada corporativas frequentemente acumulam:

📩 Emails operacionais irrelevantes

🔔 Notificações automáticas

⚠️ Mensagens sem prioridade

Isso gera perda de produtividade e ruído informacional.

Este projeto implementa uma política automatizada de governança de e-mails.

⚙️ Regra Implementada (Versão Atual)

O workflow remove automaticamente emails que:

❌ Não possuem anexos

❌ Não estão marcados como STARRED

A lógica pode ser facilmente modificada conforme necessidade.

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

A lógica pode ser editada diretamente no Function Node (JavaScript) dentro do n8n, transformando o workflow em um mecanismo de regras personalizado.

Casos de Uso

🏢 Times de suporte

💰 Departamentos financeiros

📊 Governança corporativa

🤖 Triagem automática inicial

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

Nenhuma chave ou token está incluído neste repositório.

🚀 Como Utilizar

Instalar n8n

Importar o arquivo workflow/gmail-cleaner.json

Configurar credenciais Gmail OAuth2

Ajustar regras conforme necessidade

Ativar workflow

📈 Possíveis Evoluções

📊 Implementação de logs estruturados

📑 Relatório automático de emails removidos

🔔 Integração com Slack

🏷 Classificação automática por categoria

🏢 Aplicação de políticas corporativas avançadas

💼 Competências Demonstradas

Automação de processos

Integração com APIs

Lógica condicional

Estruturação de workflow escalável

Mentalidade de eficiência operacional

🤝 Contribuição

Sugestões, melhorias e forks são bem-vindos.
Sinta-se à vontade para abrir issues ou propor melhorias.

⭐ Se este projeto foi útil

Deixe uma estrela no repositório e conecte-se comigo no LinkedIn.

👩‍💻 Autora
Paula Sabino

Automation | Cloud | Security | Process Optimization

🔗 GitHub: https://github.com/Paula-Tech007

🔗 LinkedIn: https://www.linkedin.com/in/paula-sabino-49830573/
