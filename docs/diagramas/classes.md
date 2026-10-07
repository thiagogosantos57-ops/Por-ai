classDiagram
    class Usuario {
        +int id
        +string nome
        +string email
        +string senha_hash
        +datetime data_cadastro
        +autenticar()
        +cadastrar()
    }

    class Destino {
        +int id
        +string nome
        +string pais
        +string continente
        +string descricao
        +string clima_predominante
        +obterDetalhes()
    }

    class Sazonalidade {
        +int id
        +int destino_id
        +int mes
        +float temp_media
        +int precipitacao_mm
        +string classificacao
        +string resumo_clima
    }

    class ItemPlanejamento {
        +int id
        +int usuario_id
        +int destino_id
        +date data_inicio
        +date data_fim
        +string status
        +int progresso_checklist
        +salvarRoadmap()
    }

    class Checklist {
        +int id
        +int viagem_id
        +string categoria
        +string item
        +boolean concluido
        +alternarStatus()
    }

    class ServicoClimaAPI {
        +string apiKey
        +sincronizarDados()
    }

    Usuario "1" -- "0..*" ItemPlanejamento : possui
    Destino "1" -- "12" Sazonalidade : possui
    Destino "1" -- "0..*" ItemPlanejamento : e_alvo_de
    ItemPlanejamento "1" -- "0..*" Checklist : possui
    ServicoClimaAPI ..> Sazonalidade : atualiza
