# Requisitos Não-Funcionais (RNF) — TravelCalendar

O documento especifica os critérios de qualidade, segurança e arquitetura técnica do TravelCalendar.

## Fase 1 - Desempenho e Interface

* Interface web responsiva desenvolvida com Tailwind CSS e HTML5;
* Compatibilidade com os principais navegadores (Chrome, Firefox, Edge, Safari);
* Tempo de resposta da API de recomendação inferior a 2 segundos.

## Fase 2 - Segurança e Banco de Dados

* Criptografia de senhas no banco de dados com hash seguro (Bcrypt);
* Armazenamento relacional e integridade referencial no MySQL;
* Proteção contra acessos não autorizados nas rotas da API.

## Fase 3 - Arquitetura e Padrões Acadêmicos

* Arquitetura fullstack desacoplada (Frontend em HTML/JS, Backend em FastAPI e Banco MySQL);
* Padrão de repositório e documentação estruturada segundo as diretrizes da FATEC Araraquara.
