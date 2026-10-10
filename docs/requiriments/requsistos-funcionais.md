# Requisitos Funcionais (RF) — TravelCalendar

O documento descreve as principais funcionalidades exigidas para o funcionamento da aplicação TravelCalendar.

## Fase 1 - Gestão de Usuários e Acesso

* Cadastro de novos usuários com nome, e-mail e senha;
* Autenticação e login com geração de token de sessão seguro (JWT);
* Gestão de perfil e preferências do viajante.

## Fase 2 - Motor de Busca e Sazonalidade (Date-First)

* Seleção flexível de datas manuais (dia inicial e final do intervalo de viagem);
* Escolha de qualquer mês do ano (Janeiro a Dezembro) via dropdown;
* Consulta da Matriz Climatológica e de Sazonalidade (Alta, Média e Baixa temporada);
* Filtro de destinos por clima (Quente, Ameno, Frio);
* Filtro de destinos por perfil e estilo (#Praia, #Aventura, #Cultura, #Gastronomia).

## Fase 3 - Planejamento e Itinerário

* Adição/Fixação de destinos no Calendário Anual do usuário;
* Criação e gerenciamento de Checklists de Viagem (ex: "Reservar hotel", "Comprar passagens");
* Alteração de status do planejamento de viagem (Rascunho / Confirmado / Concluído).
