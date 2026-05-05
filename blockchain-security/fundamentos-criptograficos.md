# Fundamentos criptográficos

* **Funções de Hash**
  * **Determinísticas:** Sempre geram o **mesmo hash** para a mesma entrada.
  * **Unidirecionais:** Não é possível descobrir a entrada original a partir do hash.
  * **Resistentes a colisões:** É **muito difícil** (quase impossível) encontrar duas entradas diferentes que gerem o **mesmo hash**.
  * Entrada: "senha123"    \
    Saída (SHA-256): ef92b778bafe771e89245b89ecbc08a44a4e166c06659911881f383d4473e94f
* **Criptografia de chave assimétrica**
  * Usa **dois pares de chaves**:
    * **Chave pública:** Pode ser compartilhada com todos.
    * **Chave privada:** Deve ser mantida em segredo.
* **Assinatura digital**
  * **Garantir que um doc foi:**
    * Foi **realmente enviado pela pessoa certa**.
      * **Não foi alterado** no caminho.

<details>

<summary>Blockchain utiliza o SHA3</summary>

A **blockchain** usa funções de hash para garantir **segurança, integridade e imutabilidade** dos blocos.

O **SHA-3 (Secure Hash Algorithm 3)** é uma família de funções de hash segura, definida pelo NIST, usada em alguns sistemas blockchain por ser:

* **Determinística**: sempre gera o mesmo hash para a mesma entrada.
* **Unidirecional**: não dá para descobrir os dados originais a partir do hash.
* **Resistente a colisões**: é extremamente difícil encontrar duas entradas com o mesmo hash.

Embora o **Bitcoin use SHA-256**, **SHA-3 pode ser usado em outras blockchains ou aplicações** por ser mais recente e seguro contra certas vulnerabilidades.

</details>

**Tipos de endereços Bitcoin**

|  Tipo  | Prefixo |    Script    | Eficiência |
| :----: | :-----: | :----------: | :--------: |
| Legacy |    1    |     P2PKH    |    Baixa   |
| SegWit |    3    |     P2SH     |    Média   |
| Bech32 |   bc1   | P2WPKH/P2WSH |    Alta    |

Estrutura de um Bloco

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

**Header**

Contém informações para validar o bloco:

* `HPrev`: Hash do bloco anterior (liga os blocos).
* `Hroot`: Raiz da árvore de Merkle (garante integridade das transações).
* `Nonce`, `Time`, `Version`, `Difficulty`: Usados na mineração e validação.

**Body**

Contém as **transações** e a **árvore de Merkle**:

* Transações (`Tx1`, `Tx2`, ...).
* Hashes das transações e seus agrupamentos.
* A raiz da Merkle (`Hroot`) vai para o cabeçalho.

<details>

<summary>Máquina de Estado</summary>

A blockchain funciona como uma **máquina de estado distribuída**:

* **Estado**: representa dados como saldos e contratos.
* **Transações**: são entradas que mudam o estado.
* **Regras do protocolo**: definem como as mudanças ocorrem.
* **Cada nó** aplica as mesmas regras e chega ao mesmo estado final.

📌 **Exemplo**:\
Se Alice envia 2 ETH para Bob, o estado da blockchain muda:

* Antes: Alice = 10 ETH
* Depois: Alice = 8 ETH, Bob = saldo + 2 ETH

Tudo isso é registrado de forma **imutável e sincronizada** entre todos os nós da rede.

</details>

<details>

<summary>Scripts</summary>

Na blockchain, **scripts** são pequenos programas usados para **validar transações**. Eles definem **regras que precisam ser cumpridas** para que uma transação seja considerada válida.

O Bitcoin usa uma linguagem chamada **Script**, que é:

* Simples e baseada em **pilha** (stack).
* **Não Turing-completa** (sem loops infinitos).
* Usada para **verificar assinaturas e condições de gasto**.

**Exemplo: Script de pagamento padrão (P2PKH)**

```
ScriptPubKey (do receptor):
OP_DUP OP_HASH160 <Hash da chave pública> OP_EQUALVERIFY OP_CHECKSIG

ScriptSig (do remetente):
<Assinatura> <Chave pública>
```

* O script é executado juntando `ScriptSig + ScriptPubKey`.
* Se o resultado for verdadeiro, a transação é válida.





**Cada transação carrega a sua própria lógica.**

</details>

<details>

<summary>Mecanismos de Consenso</summary>

Proof of Work

**Proof of Work (Prova de Trabalho)** é um **mecanismo de consenso** usado por blockchains como o **Bitcoin** para validar blocos e manter a rede segura.

#### **Como funciona:**

1. Os **mineradores** competem para resolver um **problema matemático difícil** (encontrar um hash abaixo de um alvo).
2. O primeiro que resolver **propaga o bloco** para a rede.
3. Os nós verificam se o trabalho é válido.
4. Se for, o bloco é adicionado à blockchain.

#### **Características principais:**

* **Gasto de energia computacional** para validar blocos.
* **Dificuldade ajustável** conforme o poder de mineração da rede.
* **Segurança**: torna ataques (como o 51%) caros e difíceis.

Minerador precisa achar um **nonce** tal que:

```plaintext
plaintextCopyEditSHA-256(header do bloco + nonce) < alvo de dificuldade
```

**Em resumo o PoW exige que mineradores gastem poder computacional para validar blocos, garantindo segurança e descentralização da blockchain.**

</details>

<details>

<summary>Rede P2P</summary>

Nodes\
\
**Nodes** são os computadores ou dispositivos que fazem parte de uma rede.

A rede é **P2P (peer-to-peer)** porque esses nodes se conectam e comunicam diretamente entre si, sem precisar de um servidor central para controlar ou coordenar as informações.\
\
**DNS Seed**

DNS Seed é um mecanismo usado por blockchains (como Bitcoin) para ajudar novos nós a descobrirem outros nós da rede quando se conectam pela primeira vez.

**Exemplo de DNS Seed**

* dnsseed.bluematt.me
* seed.bitcoinstats.com
* seed.bitcoin.jonasschnelli.ch
* seed.bitcoin.sipa.be

**Gossip Protocol - Totalmente descentralizado**

O **Gossip Protocol** é um método de comunicação em redes onde cada nó repassa informações para outros nós aleatoriamente, como se fosse um “boca a boca”, garantindo que a mensagem se espalhe rápido e de forma confiável por toda a rede.

</details>

<details>

<summary>Interação com a Blockchain</summary>

RPC

**Interação com a blockchain via RPC** (Remote Procedure Call) significa que um programa ou usuário pode enviar comandos para um nó da blockchain para consultar dados, enviar transações ou executar funções específicas.

#### Resumo:

* **RPC** é um protocolo que permite chamar funções de um programa remoto (nó da blockchain).
* Usado para pedir informações (ex: saldo, histórico) ou enviar transações.
* A comunicação é feita via rede, geralmente usando JSON-RPC sobre HTTP ou WebSocket.





</details>

