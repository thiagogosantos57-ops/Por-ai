```mermaid
sequenceDiagram
    participant U as Usuario
    participant F as Frontend
    participant B as Backend
    participant DB as Banco de Dados

    U->>F: Seleciona Outubro de 2027
    F->>B: Requisicao de Destinos para o Mes 10
    B->>DB: Consulta Sazonalidade Excelente
    DB-->>B: Retorna Destinos e Dados de Clima
    B-->>F: Envia Lista de Sugestões em JSON
    F-->>U: Exibe Cards dos Destinos
    U->>F: Clica em Fixar Viagem
    F->>B: Envia Dados para Salvar
    B->>DB: Salva Viagem no Banco
    DB-->>B: Confirma Gravacao
    B-->>F: Retorna Sucesso
    F-->>U: Exibe Confirmacao na Tela
