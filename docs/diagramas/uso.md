%%{init: {
  "theme": "base",
  "flowchart": {
    "htmlLabels": true,
    "padding": 30,
    "wrappingWidth": 300,
    "nodeSpacing": 35,
    "rankSpacing": 50
  },
  "themeVariables": {
    "background": "#ffffff",
    "primaryColor": "#ffffff",
    "primaryTextColor": "#000000",
    "primaryBorderColor": "#000000",
    "lineColor": "#000000",
    "clusterBkg": "#ffffff",
    "clusterBorder": "#000000"
  }
}}%%

flowchart LR

subgraph DIAGRAMA[" "]
direction LR

    USUARIO["◯<br/>╱│╲<br/>╱ ╲<br/>Usuário"]
    ADMIN["◯<br/>╱│╲<br/>╱ ╲<br/>Administrador"]

    subgraph SISTEMA["TravelCalendar"]

        AUTENTICAR(["Cadastrar / Acessar conta"])
        DATAS(["Selecionar datas<br/>de disponibilidade"])
        CONSULTAR(["Consultar destinos<br/>recomendados"])
        FILTRAR(["Filtrar por clima,<br/>estilo e orçamento"])
        GUIA(["Visualizar guia do destino<br/>e gráfico sazonal"])
        FIXAR(["Fixar viagem no<br/>calendário anual"])
        CHECKLIST(["Gerenciar checklist<br/>e preparativos"])

        GERENCIARDESTINOS(["Gerenciar destinos<br/>e sazonalidade"])
        GERENCIARUSUARIOS(["Gerenciar usuários"])
        MONITORAR(["Consultar métricas<br/>do sistema"])
    end

    USUARIO --- AUTENTICAR
    USUARIO --- DATAS
    USUARIO --- CONSULTAR
    USUARIO --- FILTRAR
    USUARIO --- GUIA
    USUARIO --- FIXAR
    USUARIO --- CHECKLIST

    ADMIN --- GERENCIARDESTINOS
    ADMIN --- GERENCIARUSUARIOS
    ADMIN --- MONITORAR

    CONSULTAR -.-> DATAS
    FIXAR -.-> GUIA

end

classDef ator fill:transparent,stroke:transparent,color:#000000,font-size:16px;
classDef caso fill:#ffffff,stroke:#000000,color:#000000,stroke-width:1.5px,font-size:15px;

class USUARIO,ADMIN ator;
class AUTENTICAR,DATAS,CONSULTAR,FILTRAR,GUIA,FIXAR,CHECKLIST,GERENCIARDESTINOS,GERENCIARUSUARIOS,MONITORAR caso;

style DIAGRAMA fill:#ffffff,stroke:#ffffff,color:#000000
style SISTEMA fill:#ffffff,stroke:#000000,stroke-width:2px,color:#000000

linkStyle default stroke:#000000,stroke-width:1.5px;
