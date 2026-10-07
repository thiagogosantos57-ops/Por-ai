graph TD
    %% Atores
    Usuario("👤 Usuário / Viajante")
    Admin("🛠️ Administrador")
    API_Clima["☁️ API Externa de Clima"]

    subgraph TravelCalendar ["✈️ Sistema TravelCalendar"]
        UC01("UC01: Cadastrar / Autenticar Usuário")
        UC02("UC02: Selecionar Disponibilidade de Datas")
        UC03("UC03: Consultar Matriz de Recomendação por Sazonalidade")
        UC04("UC04: Filtrar Destinos por Clima, Orçamento e Estilo")
        UC05("UC05: Visualizar Guia do Destino e Gráfico de 12 Meses")
        UC06("UC06: Fixar Destino no Roadmap Anual")
        UC07("UC07: Gerenciar Checklist e Preparativos")
        UC08("UC08: Gerenciar Cadastro de Destinos e Sazonalidade")
        UC09("UC09: Sincronizar Dados Climatológicos")
    end

    %% Relacionamentos do Usuário
    Usuario --> UC01
    Usuario --> UC02
    Usuario --> UC03
    Usuario --> UC04
    Usuario --> UC05
    Usuario --> UC06
    Usuario --> UC07

    %% Relacionamentos Incluir / Estender
    UC03 ..->|"«include»"| UC02
    UC04 ..->|"«extend»"| UC03
    UC05 ..->|"«extend»"| UC03
    UC06 ..->|"«include»"| UC05
    UC07 ..->|"«extend»"| UC06

    %% Relacionamentos Admin e Sistema Externo
    Admin --> UC08
    API_Clima --> UC09
    UC09 ..->|"«include»"| UC03
