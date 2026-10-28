## Por que banco de dados existem ?
### Memória não é suficiente
- Nem todos os dados que vamos precisar no futuro (dias, semanas, meses) podem ficar em memória.
- Isso vale mesmo para um servidor próprio: se o servidor for desligado ou cair, tudo que estava em memória se perde.
### Por que não salvar em um arquivo (ex.: uma planilha Excel) ?
- Para aplicações muito pequenas, pode até funcionar, mas não é uma boa solução.
- Com 10 usuários, tudo bem. Com 100 mil usuários gravados na mesma planilha, o sistema provavelmente teria que carregar tudo em memória para ler e encontrar um único usuário.
- Mesmo carregando o arquivo em pedaços, a solução fica complicada.
### O que o banco de dados resolve
- Uma tabela em um banco SQL é parecida com uma tabela do Excel, só que eficiente.
- Bancos de dados são robustos e permitem escalar melhor.

## Quando falamos sobre banco de dados existem 2 tipos: SQL e NoSQL
### SQL
- Dados organizados em **tabelas**.
- **Estruturado** (schema-on-write: o formato dos dados é definido antes de gravar).
- Segue **ACID**: Atomicity, Consistency, Isolation, Durability.
- Bom para: aplicações financeiras, marketplaces, CRM, ERP.

| Propriedade     | O que significa                                                                                              |
| --------------- | ------------------------------------------------------------------------------------------------------------ |
| **Atomicity**   | Transações são "tudo ou nada": não existe escrita parcial. Um update que falha no meio não corrompe o banco. |
| **Consistency** | O banco sempre respeita suas regras e restrições (FKs, triggers etc.), sem exceções.                         |
| **Isolation**   | Transações rodando em paralelo/concorrência não interferem umas nas outras.                                  |
| **Durability**  | Depois que uma transação é confirmada (commit), os dados continuam persistidos mesmo se o sistema falhar.    

### NoSQL
- **Schema flexível**.
- Não precisa necessariamente implementar ACID completo (durabilidade, em geral, sim).
- Consegue escrever muito rapidamente.
- Bom para: logs, cache.

#### Tipos de NoSQL

| Tipo            | Exemplos        |
| --------------- | --------------- |
| Key/Value store | Redis, DynamoDB |
| Banco de grafos | Neo4j           |
| Banco vetorial  | Pinecone        |

---
Resumo: [[Resumo rápido sobre banco de dados]]
