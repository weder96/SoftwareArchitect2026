# 🏛️ Seminário de Arquitetura de Software: Sucessos, Fracassos e Lições Aprendidas

**Objetivo da Atividade:**
Analisar criticamente a evolução arquitetural de gigantes da tecnologia. Os alunos atuarão como "Comitês de Arquitetura", dissecando o ciclo de vida de sistemas em hiperescala, focando em *trade-offs*, decisões de design que permitiram o crescimento exponencial, e os cenários reais de falhas sistêmicas (análise de *post-mortem*).

---

## ⏱️ Formato e Regras da Apresentação

*   **Tempo Total por Grupo:** 20 minutos rigorosamente cronometrados.
    *   *15 minutos* para a exposição do tema.
    *   *5 minutos* para arguição (Perguntas do professor e da turma).
*   **Formato de Entrega:** Apresentação de slides contendo obrigatoriamente diagramas arquiteturais.

### 🎯 Ações Esperadas na Apresentação (Como Apresentar)
Cada grupo deve estruturar sua apresentação nas seguintes etapas obrigatórias:

1.  **Contexto e Domínio (O Cenário Real):** Explicar brevemente o modelo de negócio, o volume de dados e o desafio de escalabilidade da empresa.
2.  **A Arquitetura do Sucesso:** Demonstrar, através de **diagramas**, a arquitetura atual (ou a que permitiu a escala). Destacar padrões utilizados (ex: Microsserviços, Event-Driven, Clean Architecture, CQRS).
3.  **O Fracasso (Post-Mortem):** Detalhar um incidente real e catastrófico. O que quebrou? Foi um gargalo de banco de dados, falha de rede, complexidade excessiva ou acoplamento?
4.  **Lições Aprendidas e Evolução:** Como a engenharia resolveu o problema? Quais mudanças arquiteturais foram implementadas para garantir resiliência e evitar que o cenário se repetisse?

---

## 📂 Os 9 Projetos de Estudo de Caso

### 1. Netflix: O Preço da Disponibilidade
*   **Cenário de Sucesso:** Pioneirismo em microsserviços globais, uso de *Chaos Engineering* (Chaos Monkey) e resiliência máxima na nuvem.
*   **Cenário de Fracasso:** O apagão da véspera de Natal de 2012, causado por uma falha no *Elastic Load Balancer* (ELB) da AWS, que derrubou o serviço e forçou a reformulação de sua arquitetura de redundância multi-região.

### 2. Twitter (X): Sobrevivendo ao Hipercrescimento
*   **Cenário de Sucesso:** A transição bem-sucedida da arquitetura orientada a mensagens em Scala/JVM para suportar picos globais de eventos em tempo real.
*   **Cenário de Fracasso:** A infame era do "Fail Whale", onde o monólito original construído em Ruby on Rails colapsava constantemente sob carga simultânea e alto volume de leituras.

### 3. Uber: A Complexidade da Geocronologia
*   **Cenário de Sucesso:** Arquitetura de despacho em tempo real e rastreamento geoespacial em escala global.
*   **Cenário de Fracasso:** A "explosão de microsserviços" (mais de 4.000 serviços independentes). O excesso de granularidade gerou uma complexidade de rede tão alta que exigiu a criação do modelo "Domain-Oriented Microservices" (DOMA) para conter a latência e o caos operacional.

### 4. Spotify: O Fim da Era Descentralizada
*   **Cenário de Sucesso:** Arquitetura de microsserviços gerida por *Squads* independentes, permitindo inovação rápida e entrega contínua.
*   **Cenário de Fracasso:** A dependência inicial da arquitetura *Peer-to-Peer* (P2P) para distribuição de streaming. Tornou-se insustentável com a ascensão dos dispositivos móveis, forçando a migração total para um modelo cliente-servidor centralizado e CDN.

### 5. Amazon: O Colapso do Prime Day
*   **Cenário de Sucesso:** O "Mandato de Bezos" (2002) que forçou a transição para Arquitetura Orientada a Serviços (SOA), servindo de fundação técnica para a criação da AWS.
*   **Cenário de Fracasso:** O Prime Day de 2018. Uma falha no dimensionamento da arquitetura de cache e gargalos de *lock* no banco de dados causaram uma cascata de lentidão e falhas no e-commerce global.

### 6. Airbnb: Desmontando o "Monorail"
*   **Cenário de Sucesso:** A migração estruturada de um monólito gigante para uma arquitetura orientada a serviços de forma iterativa, sem parar o negócio.
*   **Cenário de Fracasso:** Incidentes críticos de indisponibilidade do banco de dados relacional central durante o hiper-crescimento da plataforma, forçando estratégias de *sharding* e divisão de persistência.

### 7. Meta (Facebook): O Efeito Dominó BGP
*   **Cenário de Sucesso:** Criação de padrões revolucionários como GraphQL e a arquitetura do TAO (banco de dados em grafo hiper-otimizado para fluxos de leitura massiva).
*   **Cenário de Fracasso:** O apagão global de 2021. Uma falha em um comando de manutenção automatizado removeu as rotas BGP, isolando completamente todos os data centers da empresa da internet (e uns dos outros).

### 8. Knight Capital: O Custo de um Deploy Defeituoso
*   **Cenário de Sucesso:** Infraestrutura arquitetural de altíssimo desempenho, construída para processar milhares de transações financeiras em milissegundos (*High-Frequency Trading*).
*   **Cenário de Fracasso:** A perda irreversível de 460 milhões de dólares em apenas 45 minutos. Falhas graves na arquitetura de automação de *deploy* (CI/CD) reativaram um código zumbi em produção que começou a comprar e vender ações descontroladamente.

### 9. Cloudflare: Quando um Regex Derruba a Internet
*   **Cenário de Sucesso:** Arquitetura *Edge Computing* global distribuída que protege e acelera grande parte da internet, mitigando ataques DDoS em escala massiva.
*   **Cenário de Fracasso:** O incidente de 2019, onde uma única regra de Expressão Regular (Regex) mal otimizada no Web Application Firewall (WAF) causou um pico de uso de CPU para 100% em todas as máquinas da borda global, derrubando metade da internet por cerca de 30 minutos.

---

## 📋 Critérios de Avaliação (Sugestão de Rubrica)
*   **Profundidade Técnica:** O grupo compreendeu os *trade-offs* arquiteturais ou apenas citou tecnologias?
*   **Clareza Visual:** Os diagramas apresentados refletem com precisão o cenário estudado?
*   **Análise Crítica:** A explicação do fracasso (post-mortem) focou na raiz do problema arquitetural e não apenas no erro humano?
*   **Maturidade e Postura:** Respeito ao tempo limite e capacidade de argumentação técnica durante a sessão de perguntas.