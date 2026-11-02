## BASE

Modelo de consistência que os bancos **NoSQL** tentam seguir. É o "contraponto" ao ACID.
### Basically Available
- Garante que **toda request recebe uma response**, mas não garante que os dados estejam 100% atualizados para todas as requests.
- Prefere **availability e uptime** a consistência.
- Típico de sistemas distribuídos.

### Soft State
- O estado do sistema pode mudar **mesmo sem input**.
- Os dados podem ficar **temporariamente inconsistentes**.

### Eventual Consistency
- Os dados **convergem** para um estado consistente com o tempo.
- A consistência é propagada de forma **assíncrona**.
### Trade-off: ACID vs BASE
Se você quiser que um sistema seja **apenas ACID**:
- fica mais difícil escalar;
- o tempo de resposta tende a ser maior, com escritas mais lentas;
- os serviços podem ficar indisponíveis em alguns momentos.

O BASE **"relaxa" as restrições do ACID** em troca de escala e disponibilidade.

> [!example] Exemplo: views do YouTube

> Seria ruim clicar em um vídeo e ter que esperar uma request garantir que o número de views está 100% atualizado. Com BASE o número é **próximo do real**, e não faz diferença se o vídeo tem 100 ou 104 visualizações.

> Já o **saldo bancário** precisa ser persistido de forma consistente, e aí o ACID faz sentido.


---
Relacionado: [[Teorema CAP]] · [[Banco de dados#SQL|ACID]]
Nota principal: [[Banco de dados]]
