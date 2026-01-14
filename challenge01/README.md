# Desafio Técnico — Desenvolvedor Backend Python

## Contexto

O setor jurídico de uma organização recebe diariamente pacotes de documentos para validação de novos contratos com fornecedores. Atualmente, a análise é feita manualmente, verificando:

- Se os dados entre documentos são consistentes (ex: CNPJ, razão social)
- Se os documentos estão dentro da validade (prazo de 6 meses)
- Se há divergências que impedem a aprovação do contrato

Seu desafio é construir uma **API que automatize a extração e validação cruzada** desses documentos, gerando insights que auxiliem o time jurídico na tomada de decisão.

---

## O Desafio

Desenvolver uma API REST que receba 3 tipos de documentos PDF e retorne uma análise de validação com os seguintes pontos:

### Documentos de entrada

| # | Documento | Descrição |
|---|-----------|-----------|
| 1 | **Contrato Social** | Documento base com dados da empresa (razão social, CNPJ, endereço, sócios, objeto social) |
| 2 | **Cartão CNPJ** | Comprovante de inscrição na Receita Federal |
| 3 | **Certidão Negativa de Débitos** | Certidão que comprova regularidade fiscal |

### Análise esperada

A API deve ser capaz de:

1. **Extrair dados estruturados** de cada documento
2. **Cruzar informações** entre os documentos para identificar inconsistências
3. **Validar regras de negócio** (ex: documento dentro da validade)
4. **Gerar um parecer** com o status da validação (`APROVADO` ou `REPROVADO`) e lista de inconsistências encontradas

### Exemplo de inconsistências a detectar

- Razão social divergente entre documentos
- CNPJ com dígitos diferentes
- Certidão com data de validade expirada
- Endereço divergente entre contrato social e cartão CNPJ

---

## Requisitos Técnicos

### Stack obrigatória
- **Python 3.10+**
- **FastAPI**
- **Integração com LLM via OpenRouter** (chave será fornecida)

### Requisitos de código
- Código organizado e legível
- Tipagem com Type Hints
- Tratamento adequado de erros
- README com instruções de execução

### Diferenciais (não obrigatórios)
- Testes automatizados
- Documentação da API (Swagger/OpenAPI)
- Containerização com Docker
- Logs estruturados
- Arquitetura limpa / separação de responsabilidades

---

## Entregáveis

1. **Repositório Git** (GitHub, GitLab ou similar) contendo:
   - Código fonte da aplicação
   - README.md com instruções de instalação e execução
   - Arquivo de dependências (requirements.txt ou pyproject.toml)

---

## Critérios de Avaliação

| Critério | O que avaliamos |
|----------|-----------------|
| **Integração com LLM** | Qualidade dos prompts, estruturação das respostas, tratamento de erros da API |
| **Lógica de validação** | Capacidade de cruzar dados, identificar inconsistências, aplicar regras de negócio |
| **Design da API** | Endpoints bem definidos, contratos claros, responses adequados |
| **Qualidade de código** | Organização, legibilidade, boas práticas, tipagem |
| **Documentação** | Clareza do README, explicação das decisões |
| **Extras** | Testes, Docker, logs, tratamento de edge cases |

---

## Recursos Fornecidos

### Chave de API
Será fornecida uma chave da **OpenRouter** para acesso aos modelos de LLM. Você pode escolher o modelo que preferir dentre os disponíveis.

Documentação OpenRouter: https://openrouter.ai/docs

### Documentos de exemplo
Disponibilizamos 3 PDFs de exemplo para desenvolvimento e testes:

- `01_contrato_social.pdf`
- `02_cartao_cnpj.pdf`
- `03_certidao_negativa_federal.pdf`

> ⚠️ **Importante:** Os documentos de exemplo contêm inconsistências propositais. Sua API deve ser capaz de identificá-las.

---

## Prazo

**4 dias corridos** a partir do recebimento deste desafio.

---

## Dúvidas

Caso tenha dúvidas sobre o desafio, entre em contato. Responderemos o mais breve possível.

---

## Observações finais

- Não existe uma única solução correta. Queremos entender como você pensa e resolve problemas.
- Valorizamos código funcional e bem organizado mais do que features extras incompletas.
- O desafio simula um cenário real do projeto em que você atuará.

**Boa sorte!** 🚀
