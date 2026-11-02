Critérios para avaliar os trade-offs:
- **Forma/formato dos dados**: flexível ou rígido
- **Padrões de acesso**
- **Latência**
- **CAP**: o que priorizar
- **Proporção e complexidade de reads/writes**: escrita em SQL tende a ser mais lenta que em NoSQL

### SQL
**Pontos fortes**
- Padronizado
- Queries complexas
- Consistência
- Lógica de negócio core

**Dificuldades**
- Escala vertical
- Writes distribuídos
### NoSQL
- Schema flexível
- Escala
#### Tipos de NoSQL e casos de uso

| Tipo      | Casos de uso                                                                                                |
| --------- | ----------------------------------------------------------------------------------------------------------- |
| Key-Value | Caching, sessões, feature flags, rate limits, chaves de idempotência                                        |
| Colunar   | Big Data                                                                                                    |
| Grafo     | Recomendações, detecção de fraude, redes sociais, quando o **relacionamento** entre os dados é o importante |
| Vetorial  | Busca por similaridade (ex.: RAG)                                                                           |

> [!example] Vector DB: sistema com IA que busca documentos (RAG)

> 1. Os documentos são transformados em **vetores** e indexados.
> 2. O que o usuário digita também vira vetor.
> 3. A busca retorna os documentos com maior **similaridade** com a pergunta.

---
Relacionado: [[Teorema CAP]] · [[BASE - NoSQL]] · [[Resumo rápido sobre banco de dados]]
Nota principal: [[Banco de dados]]
