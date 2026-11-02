## Resumo rápido: SQL vs. NoSQL

| Critério        | SQL                                          | NoSQL                                                      |
| --------------- | -------------------------------------------- | ---------------------------------------------------------- |
| Estrutura       | Tabelas, schema fixo (schema-on-write)       | Schema flexível                                            |
| Garantias       | [[Banco de dados#SQL\|ACID]]                 | [[BASE - NoSQL\|BASE]] (ACID não obrigatório)              |
| Consistência    | Forte                                        | Eventual                                                   |
| [[Teorema CAP\|CAP]] | Tende a **CP**                          | Tende a **AP**                                             |
| Escala          | Vertical; writes distribuídos são difíceis   | Horizontal                                                 |
| Escrita         | Mais lenta                                   | Mais rápida                                                |
| Ponto forte     | Consistência, integridade, queries complexas | Velocidade de escrita, flexibilidade, escala               |
| Casos de uso    | Financeiro, marketplace, CRM, ERP, lógica de negócio core | Logs, cache, sessões, big data, recomendações, busca por similaridade |

### Tipos de NoSQL

| Tipo      | Exemplos        | Casos de uso                                                   |
| --------- | --------------- | -------------------------------------------------------------- |
| Key-Value | Redis, DynamoDB | Cache, sessões, feature flags, rate limits, idempotência       |
| Colunar   | —               | Big data                                                       |
| Grafo     | Neo4j           | Recomendações, detecção de fraude, redes sociais               |
| Vetorial  | Pinecone        | Busca por similaridade (RAG)                                   |

### Quando os dados não cabem em um banco só
Dividir entre vários bancos com [[Partitioning - Sharding|sharding]]: key-range, módulo (`id % N`) ou consistent hashing. Custo: joins lentos e mais complexidade.

---
Nota principal: [[Banco de dados]] · Como decidir: [[Como escolher um banco de dados]]
