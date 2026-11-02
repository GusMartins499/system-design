## O que é
**Sharding** é dividir os dados entre **vários bancos de dados** (shards).
O sistema precisa saber para qual banco cada requisição vai: A, B ou C.

| Tipo       | Divide por         | Ideia                                                |
| ---------- | ------------------ | ---------------------------------------------------- |
| Horizontal | Linhas             | Mesmo schema, cada shard guarda um pedaço das linhas |
| Vertical   | Colunas ou tabelas | Separa por responsabilidade                          |
### Por que fazer particionamento vertical
- **SoC (Separation of Concerns)**: cada banco cuida de uma responsabilidade
- Os dados podem **escalar de forma independente**
- Tirar do caminho as **colunas raramente acessadas**

## Estratégias para distribuir os dados
### Key-range
Separa por faixa de ID:
- `1–1000` → banco A
- `1001–2000` → banco B
- ...
### Módulo (hash mod N)
`id % N`, onde **N** é o número de bancos. O resultado é um inteiro que diz para qual banco o dado vai.
### Consistent hashing
Tanto os **bancos** quanto os **dados** recebem um hash. Um cálculo define para qual banco o dado vai, que é o banco "mais próximo" do hash do dado.

> [!note] Complemento

> Normalmente se imagina um **anel de hashes**: o dado vai para o primeiro banco que aparece seguindo o anel no sentido horário. A vantagem sobre o módulo é que, quando um banco entra ou sai, **só uma parte pequena dos dados precisa ser movida**. Com `id % N`, mudar N remaneja quase tudo.
 
 ## Trade-offs
- **Joins lentos**, porque os dados ficam espalhados em shards diferentes
- **Mais complexidade** no sistema
## Particionamento lógico e índice secundário global
- Com partições lógicas fica **mais fácil mover dados** para outro banco: você move a partição inteira.
- Essas partições costumam ser definidas pela **chave primária (id)**.

**Problema:** buscar por um campo que **não é o id**. Seria preciso consultar **todas as partições em todos os shards**, o que é custoso.
**Solução:** criar um **índice secundário global**, que aponta para o **shard** onde o dado está.

---
Relacionado: [[Como escolher um banco de dados]]
Nota principal: [[Banco de dados]]
