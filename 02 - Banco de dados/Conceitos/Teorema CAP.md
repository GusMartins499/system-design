## Teorema CAP

Em um sistema distribuído só dá para garantir **2 das 3** propriedades ao mesmo tempo.

```
                 C
            Consistency
                /\
               /  \
          CP  /    \  CA
             /      \
            /        \
           /__________\
          P     AP     A
  Partition         Availability
  Tolerance
```

| Letra | Propriedade             | O que significa                                                                  |
| ----- | ----------------------- | -------------------------------------------------------------------------------- |
| **C** | Consistency             | Toda leitura recebe o dado mais recente (ou um erro).                            |
| **A** | Availability            | Toda request recebe uma response, mesmo que o dado não seja o mais atualizado.  |
| **P** | Partition Tolerance     | O sistema continua funcionando mesmo quando a rede entre os nós falha.           |

> [!note] Complemento
> Em um sistema distribuído, **partições de rede vão acontecer**, então na prática P é obrigatório. A escolha real é entre **CP** (consistência) e **AP** (disponibilidade) quando ocorre uma partição. BASE/NoSQL geralmente tende para **AP**, e bancos SQL tradicionais para **CP**.

---
Relacionado: [[BASE - NoSQL]] · [[Como escolher um banco de dados]]
Nota principal: [[Banco de dados]]
