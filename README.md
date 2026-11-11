AI Customer Support Automation

Projeto pessoal de automação de atendimento ao cliente utilizando Inteligência Artificial, desenvolvido em Python com integração ao Gmail, banco de dados Supabase e modelos de linguagem da Anthropic.

Objetivo do projeto

A ideia é desenvolver um sistema capaz de automatizar parte do atendimento de uma loja virtual.

O sistema monitora uma caixa de entrada do Gmail, identifica novas mensagens, utiliza IA para compreender as solicitações dos clientes e consulta uma base de conhecimento para elaborar respostas.

Quando a solicitação pode ser resolvida com as informações disponíveis, o sistema prepara uma resposta automática. Quando identifica uma situação que precisa de intervenção humana, encaminha o atendimento para análise.

Tecnologias utilizadas

Backend

Python 3.13 – Linguagem principal do projeto.

FastAPI – Desenvolvimento da API e disponibilização dos endpoints.

uv – Gerenciamento de dependências e ambientes Python.

Pydantic AI – Desenvolvimento dos agentes de inteligência artificial.

Pydantic Settings – Gerenciamento das configurações da aplicação.

Watchfiles – Monitoramento de alterações durante o desenvolvimento.

Inteligência Artificial

Anthropic Claude Haiku – Classificação das mensagens.

Anthropic Claude Sonnet – Análise das solicitações e elaboração de respostas.

Pydantic Evals – Avaliação do comportamento e das decisões dos agentes.

Integrações e banco de dados

Gmail API – Leitura, envio e gerenciamento de mensagens.

Google OAuth 2.0 – Autenticação e autorização para acessar o Gmail.

Supabase – Banco de dados PostgreSQL e armazenamento das informações do sistema.

Frontend

React

TypeScript

Vite

Tailwind CSS

shadcn/ui

Infraestrutura e deploy

Oracle Cloud Infrastructure (OCI) – Hospedagem da aplicação.

Ubuntu 22.04.5 LTS – Sistema operacional do servidor.

ARM64 (aarch64) – Arquitetura da instância.

Docker – Containerização da aplicação.

Docker Compose – Orquestração dos serviços.

Git e GitHub – Controle de versão e gerenciamento do código.

Como funciona

O fluxo principal da aplicação foi planejado da seguinte maneira:

O sistema verifica periodicamente a caixa de entrada do Gmail.

Identifica mensagens que ainda não foram processadas.

Registra os eventos e as informações das mensagens no Supabase.

Verifica se a mensagem pode ser processada com segurança, evitando responder mensagens enviadas pelo próprio sistema, respostas automáticas ou e-mails em massa.

Um modelo de IA classifica a solicitação do cliente.

Outro agente consulta a base de conhecimento e prepara uma resposta.

Regras implementadas em Python validam a decisão final.

O sistema responde ao cliente ou encaminha o atendimento para análise humana.

As informações ficam disponíveis para acompanhamento no dashboard.

Uma decisão importante na arquitetura: o modelo de IA sugere a ação, mas a decisão final é controlada pelo código Python. Isso ajuda a evitar que o sistema execute automaticamente respostas inadequadas.