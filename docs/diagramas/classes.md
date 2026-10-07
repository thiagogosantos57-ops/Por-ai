```mermaid
classDiagram
    class Usuario {
        +int id
        +string nome
        +string email
        +string senha
        +cadastrar()
        +login()
    }

    class Destino {
        +int id
        +string cidade
        +string pais
        +string continente
        +string descricao
    }

    class SazonalidadeDestino {
        +int id
        +int destinoId
        +int mes
        +string classificacao
        +string clima
    }

    class Planejamento {
        +int id
        +int usuarioId
        +string titulo
        +int ano
    }

    class ItemPlanejamento {
        +int id
        +int planejamentoId
        +int destinoId
        +int mes
        +int dias
    }

    class Checklist {
        +int id
        +int planejamentoId
        +string tarefa
        +boolean concluido
    }

    Usuario "1" -- "N" Planejamento : possui
    Planejamento "1" -- "N" ItemPlanejamento : contem
    Destino "1" -- "N" ItemPlanejamento : refere
    Destino "1" -- "12" SazonalidadeDestino : possui
    Planejamento "1" -- "N" Checklist : possui
