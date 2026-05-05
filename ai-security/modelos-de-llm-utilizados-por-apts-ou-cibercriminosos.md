# modelos de LLM utilizados por APTs ou cibercriminosos

\
**Modelos treinados por APTs/cibercriminosos**\
\
Os atacantes estão criando os seus próprios modelos de AI para geração de malwares.\
\
Com apenas um código de malware/ransomware e algumas intruções, podem ser gerados milhares de outros códigos maliciosos diferentes e personalizados para diversos ambientes. \
\
**Antigamente era necessários meses para a criação personalizada de um malware, hoje em dia é questão de segundos.**&#x20;

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

**Exemplos de LLMs vendidos na darkweb**

| **PoisonGPT** (conceito) | Técnica onde atores criam modelos LLM envenenados para desinformar usuários ou ferramentas automatizadas.                                                      | Pode ser usado para ataques de supply chain de IA.                      |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **WormGPT**              | Modelo de linguagem baseado no GPT-J, vendido em fóruns da dark web. Usado para gerar phishing, BEC (Business Email Compromise), etc.                          | Sem filtros de ética. Semelhante ao GPT, mas voltado a fins maliciosos. |
| **DarkBERT / DarkGPT**   | Modelos baseados em dados da dark web e fóruns de hacking. Usados para responder sobre exploits, scripts, engenharia social, etc.                              | Baseados em BERT/GPT com corpus treinado em fontes ilegais.             |
| **FraudGPT**             | LLM vendido em fóruns criminosos, especializado em crafting de payloads, engenharia social, etc.                                                               | Específico para phishing e ataques de malware.                          |
| **APT-Custom LLMs**      | Alguns relatórios sugerem que grupos APT estatais (China, Rússia, Coreia do Norte) treinam seus próprios LLMs em dados técnicos, exploits e linguagem de rede. | Difíceis de rastrear. Foco em OPSEC, SIGINT e automação.                |

Principais usos por criminosos&#x20;

**Phishing avançado**: Geração de e-mails altamente personalizados e sem erros de gramática.\
**Engenharia social automatizada**: Chats falsos, deepfakes de texto, simulações de atendimento.\
**Reconhecimento e OSINT**: Automação de coleta e resumo de informações sobre alvos.\
**Geração de scripts maliciosos**: Criação de scripts PowerShell, macros, shellcodes.\
**Tradução de exploits**: Adaptar exploits públicos para targets específicos.\
**Análise reversa automatizada**: Uso de LLM para descrever funcionamento de código alvo (ex: malware).



Fontes?:

* Check Point Research: WormGPT & FraudGPT analysis.
* Recorded Future: Atividades em fóruns de hacking com LLMs.
* Microsoft Threat Intelligence: Exploração de IA generativa por grupos APT.
* Black Hat & Defcon papers (2023–2024): Diversos artigos sobre LLMs ofensivos.
