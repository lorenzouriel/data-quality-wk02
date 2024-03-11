# Data Quality com Pandera
Para desenvolver o desafio de negocio, vamos montar a seguinte ETL

## Fluxo
- ***Para desenvolver o ETL vamos utiliza esse fluxo***
```mermaid
graph TD;
    A[Configura Variáveis] --> B[Ler o Banco SQL];
    B --> V[Validação do Schema de Entrada];
    V -->|Falha| X[Alerta de Erro];
    V -->|Sucesso| C[Transformar os KPIs];
    C --> Y[Validação do Schema de Saída];
    Y -->|Falha| Z[Alerta de Erro];
    Y -->|Sucesso| D[Salvar no DuckDB];
```

# Contrato de dados

::: app.schema.ProdutoSchema