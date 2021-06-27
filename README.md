# Simple Simple Raft

É um projeto que busca facilitar ainda mais o entendimento e aplicação dessa estrutura de sistema distribuído que é amplamente utilizada pelo mercado atual.

## Raft


Raft é um algoritmo de consenso em eleição de lider. Ele foi desenhado para ser seguro, performático e fácil de entender. Ele é muito utilizado em sistemas distribuídos onde multiplos servidores precisam verificar um recurso compartilhado mesmo em situação de falha. Esse recurso compartilhado normalmente é uma estrutura de dados que é replicada por meio de logs. Precisamos que o sistema seja completamente operacional mesmo com a maior parte dos servidores estando operante.

## Consenso é dividido entre 3 sub-problemas

- Eleição de lider: Um novo lider é eleito caso haja alguma falha com o atual lider.
- Replicação de log: O lider precisa manter os logs de todos os servidores sincronizados com os seus durante a replicação
- Segurança: Se um dos servidores escrever um de seus logs em um index específico nenhum dos outros servidores pode aplicar um outro log ao mesmo index.



## Estrutura básica e mudança de estados
Cada servidor possui três estados diferentes: Lider, Seguidor ou Candidato

![logo](https://cdn-media-1.freecodecamp.org/images/oN6xZLkKQrVnaWWlp7I8w9aep2NNgMz5fR9D)

## Tempo

o raft utiliza "term" como uma quantidade de tempo que nada mais é que o tempo entre duas eleições, caso o lider nunca sofra uma queda o termo pode durar indefinidamente, caso nenhum candidato ganhe a eleição é criada uma nova e o termo atual é terminado.

## Comunicação
Servidores raft usam RPCs para replicar informação no cluster. Existem 3 tipos de mensagens usadas:

- AppendEntries: Envio de log de dados para replicação do estado
- RequestVote: Inicia uma eleição de lider
- InstallSnapshot: Envia um arquivo de log compacto sobre a rede para nós que estiverem com lag ou sejam novos sincronizarem com o lider do cluster.

## Eleição de lider

## Replicação de log

## Segurança

## Cluster

