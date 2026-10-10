# Documento de Requisitos Não-Funcionais (RNF) — TravelCalendar

Este documento estabelece as restrições técnicas, os atributos de qualidade, os padrões de segurança e as diretrizes de arquitetura aplicados ao projeto **TravelCalendar**.

---

## 1. Desempenho e Eficiência

* **RNF01 - Tempo de Resposta da API:**
  * As requisições de busca de destinos por sazonalidade e filtros devem responder em menos de **1.5 segundos** sob condições normais de uso.

* **RNF02 - Otimização de Imagens e Assets:**
  * As imagens dos destinos turísticos devem ser carregadas de forma otimizada (formatos leves como WebP/JPEG comprimido) para garantir carregamento rápido no frontend.

---

## 2. Usabilidade e Responsividade

* **RNF03 - Interface Responsiva (Mobile e Desktop):**
  * O frontend construído com Tailwind CSS deve adaptar seu layout dinamicamente para diferentes resoluções de tela (smartphones, tablets e computadores de mesa).

* **RNF04 - Acessibilidade e Feedback Visual:**
  * A interface deve fornecer feedback claro ao usuário em ações de busca, erros de validação (ex: e-mail inválido) e estados de carregamento (*spinners* ou *placeholders* durante a requisição).

---

## 3. Segurança e Proteção de Dados

* **RNF05 - Criptografia de Senhas:**
  * As senhas dos usuários nunca devem ser salvas em texto puro no banco de dados. Elas devem obrigatoriamente passar por um processo de hash seguro utilizando a biblioteca `Bcrypt` antes do armazenamento.

* **RNF06 - Proteção de Rotas e Validação JWT:**
  * As rotas privadas da API (como salvar uma viagem ou alterar um checklist) devem validar o token JWT enviado nos cabeçalhos (`Authorization: Bearer <token>`).

---

## 4. Arquitetura e Engenharia de Software

* **RNF07 - Arquitetura Fullstack Desacoplada:**
  * O projeto deve manter uma separação rígida entre as camadas:
    * **Frontend:** Interface estática (HTML5, JavaScript ES6, Tailwind CSS).
    * **Backend:** API RESTful desenvolvida em Python (`FastAPI`).
    * **Persistência:** Banco de dados relacional (`MySQL`).

* **RNF08 - Integridade Referencial no Banco de Dados:**
  * O banco de dados MySQL deve manter restrições de Chaves Estrangeiras (`FOREIGN KEY`) com ações em cascata (`ON DELETE CASCADE`) apropriadas para garantir a integridade dos dados de planejamento e checklists.

* **RNF09 - Padronização do Repositório (GitHub):**
  * A estrutura de documentação deve seguir a organização hierárquica estipulada para a avaliação técnica na FATEC Araraquara (pastas `database`, `diagrams`, `requirements` e `roadmap`).
