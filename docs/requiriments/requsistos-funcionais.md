## Requisitos Funcionais (RF) — TravelCalendar

Este documento detalha as funcionalidades que o sistema **TravelCalendar** oferece para permitir a busca por sazonalidade, o planejamento de viagens e a gestão do itinerário do usuário.

---

## 1. Módulo de Gestão de Usuários e Autenticação

* **RF01 - Cadastro de Conta de Usuário:**
  * O sistema deve permitir que novos viajantes se cadastrem informando nome completo, endereço de e-mail válido, senha e preferências iniciais de viagem.
  * **Regra de Negócio:** O e-mail deve ser único no sistema. A senha deve ter no mínimo 8 caracteres.

* **RF02 - Autenticação e Sessão Segura:**
  * O sistema deve realizar o login do usuário autenticando o e-mail e a senha informados.
  * **Regra de Negócio:** O backend deve emitir um Token de Acesso (JWT) com tempo de expiração padrão de 24 horas para validar requisições subsequentes.

* **RF03 - Perfil e Preferências de Viagem:**
  * O usuário deve conseguir visualizar e atualizar suas informações cadastrais e definir preferências padrão (ex: clima preferido, estilo de viagem recorrente e orçamento habitual).

---

## 2. Módulo do Motor de Sazonalidade e Busca (*Date-First*)

* **RF04 - Seleção Flexível de Intervalo de Datas:**
  * O seletor da página principal deve permitir ao usuário escolher manualmente qualquer mês do ano (de Janeiro a Dezembro) e determinar livremente o dia inicial (entrada) e o dia final (saída), cobrindo do dia 01 ao dia 31 de cada mês.

* **RF05 - Matriz de Sazonalidade Climatológica:**
  * Ao selecionar o mês/período, o sistema deve consultar a base histórica e retornar a classificação do destino no período:
    * **Classificação de Temporada:** Alta Temporada, Média Temporada ou Baixa Temporada.
    * **Histórico do Clima:** Temperatura média estimada (°C) e condição do tempo (ex: Ensolarado, Chuvoso, Neve).

* **RF06 - Filtros Avançados de Busca:**
  * O motor de busca deve permitir combinar e filtrar os destinos por:
    * **Clima Desejado:** Sol/Quente, Ameno, Frio/Neve.
    * **Estilo de Viagem:** #Praia, #Aventura, #Cultura, #Gastronomia, #Ecoturismo.
    * **Faixa de Orçamento Estimado:** Econômico ($), Intermediário ($$), Luxo ($$$).

* **RF07 - Detalhamento e Guia do Destino:**
  * Ao clicar em um destino recomendado, o sistema deve exibir uma modal/página com o guia de 12 meses do local, informando os melhores meses de visitação e atracações recomendadas para cada época.
