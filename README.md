# EcoIA - Assistente Inteligente de Descarte de Resíduos

Projeto desenvolvido para as disciplinas de **Projeto de IA** e **Segurança e Otimização de BD**.

## 🎯 O Projeto
O EcoIA é um assistente virtual que ajuda usuários a identificarem a lixeira correta para cada tipo de resíduo. A interface principal é um bot no Telegram (com protótipo de Mini App em HTML) e o motor de IA roda via n8n integrado ao Gemini.

## 🏗️ Arquitetura da Versão 1.0
1. **Telegram:** Interface de conversa com o usuário.
2. **n8n:** Orquestrador do fluxo (Gatilho -> IA -> Banco -> Resposta).
3. **Google Gemini (IA):** Processamento de linguagem natural com *System Prompt* restrito ao tema reciclagem.
4. **Google Sheets:** Banco de dados inicial para auditoria (log de usuário, pergunta, resposta e timestamp).

## 🖥️ Protótipo da Interface (Mobile)
Desenvolvemos uma interface interativa com globo 3D para ser o futuro Mini App do Telegram. 
[Acesse o protótipo aqui](COLE_O_LINK_DO_SEU_GITHUB_PAGES_AQUI)

## 🚀 Como rodar o projeto
Como o projeto utiliza n8n (SaaS), a execução local requer:
1. Criar um bot no BotFather do Telegram e obter o Token.
2. Obter uma API Key do Google Gemini.
3. Importar o fluxo (workflow.json) no n8n.
4. Configurar as credenciais do Telegram, Gemini e Google Sheets nos respectivos nós.
5. Ativar o workflow.

## 🔒 Segurança
* O fluxo conta com validação de entrada para evitar prompt injection.
* Os logs são anonimizados (ID do Telegram é o único dado de identificação).
* A IA tem permissão de *append* (escrita apenas) no banco, sem poder deletar registros.
