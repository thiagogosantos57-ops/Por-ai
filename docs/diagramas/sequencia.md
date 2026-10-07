``mermaid
sequenceDiagram
    autonumber
    actor U as Usuário
    participant F as Frontend (JS)
    participant B as Backend (Python)
    participant DB as Banco de Dados (MySQL)

    U->>F: Seleciona Outubro/2027 no Calendário
    F->>B: GET /api/destinos/sugerir?mes=10&ano=2027
    B->>DB: SELECT * FROM sazonalidade WHERE mes = 10 AND classificacao = 'Excelente'
    DB-->>B: Retorna Destinos e Dados Climáticos
    B-->>F: JSON com Lista de Sugestões
    F-->>U: Exibe Cards dos Destinos na Tela
    U->>F: Clica em "Fixar Viagem"
    F->>B: POST /api/planejamentos/salvar
    B->>DB: INSERT INTO itens_planejamento
    DB-->>B: Confirmação de Inserção
    B-->>F: HTTP 201 Created
    F-->>U: Exibe Notificação "Salvo no Calendário!"
