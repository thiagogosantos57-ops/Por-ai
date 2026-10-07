```markdown
```mermaid
flowchart TD
    subgraph FRONTEND ["Frontend (Interface)"]
        UI["Interface Web (HTML/Tailwind)"]
        JS["App JS (Lógica de Calendário)"]
    end

    subgraph BACKEND ["Backend (API Python)"]
        API["API REST (FastAPI/Flask)"]
        ENGINE["Motor de Sazonalidade"]
        AUTH["Serviço de Autenticação"]
    end

    subgraph DATABASE ["Banco de Dados"]
        DB[("MySQL Database")]
    end

    UI --> JS
    JS -->|Requisição HTTP / JSON| API
    API --> AUTH
    API --> ENGINE
    ENGINE -->|Consultas SQL| DB
    AUTH -->|Validação de Usuário| DB
