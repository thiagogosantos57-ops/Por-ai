
```mermaid
stateDiagram-v2
    [*] --> Inicio
    Inicio --> SelecionandoDatas : Abre Calendário
    SelecionandoDatas --> BuscandoDestinos : Seleciona Mês ou Dias
    BuscandoDestinos --> VisualizandoOpcoes : Processa Clima e Sazonalidade
    VisualizandoOpcoes --> DestinoSelecionado : Escolhe Cidade
    DestinoSelecionado --> ViagemFixada : Adiciona ao Roadmap Anual
    ViagemFixada --> ChecklistPendente : Gera Checklist
    ChecklistPendente --> ViagemConcluida : Conclui Tarefas
    ViagemConcluida --> [*]
