# Bitcoin: A Peer-to-Peer Electronic Cash System

{% file src="../.gitbook/assets/bitcoin.pdf" %}
Bitcoin: A Peer-to-Peer Electronic Cash System
{% endfile %}

O documento de Satoshi Nakamoto propõe o Bitcoin, um novo sistema de dinheiro eletrônico _peer-to-peer_ (P2P) que permite que pagamentos online sejam feitos diretamente entre duas pessoas, sem a necessidade de um banco ou outra instituição financeira.

O problema central que o Bitcoin resolve é o gasto duplo (_double-spending_), que é quando alguém tenta usar a mesma moeda digital duas vezes. Em sistemas tradicionais, o banco é o responsável por verificar se isso não acontece.

#### A Solução do Bitcoin

Para resolver o gasto duplo sem um intermediário, o Bitcoin cria um registro público e cronológico de todas as transações, mantido pela própria rede de usuários, e não por uma autoridade central.

1. Cadeia de Transações: Cada moeda é essencialmente uma cadeia de assinaturas digitais. Para gastar uma moeda, você assina digitalmente a transação e a repassa ao próximo dono.
2. Prova de Trabalho (_Proof-of-Work - PoW_): As transações são agrupadas em blocos e conectadas umas às outras em uma cadeia (_blockchain_). Para que um bloco seja considerado válido, os participantes da rede (os mineradores) precisam gastar poder computacional (eletricidade) para resolver um problema matemático complexo. Isso é a Prova de Trabalho.
3. Consenso pela Maioria: A cadeia com a maior quantidade de Prova de Trabalho é sempre a considerada a correta pela rede. Isso significa que, para um atacante tentar reverter uma transação, ele teria que refazer o trabalho de todos os blocos seguintes e superar a velocidade de todos os nós honestos, o que se torna exponencialmente mais difícil com o tempo.

#### Incentivos e Segurança

* Incentivo para o Trabalho: Os participantes que usam seu poder de processamento para criar novos blocos válidos e estender a cadeia são recompensados com novas moedas (a criação de Bitcoin) e taxas de transação. Isso incentiva os nós a agirem honestamente.
* Robustez: O sistema é seguro contanto que a maioria do poder de processamento (CPU) da rede esteja nas mãos de participantes honestos. A rede é robusta e flexível: os nós podem entrar e sair a qualquer momento, e sempre aceitarão a cadeia mais longa como o registro verdadeiro.

Em suma, o Bitcoin substitui a confiança em uma instituição por uma prova criptográfica e computacionalmente verificável.
