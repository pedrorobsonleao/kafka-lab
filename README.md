# Kafka Lab - Development Workspace

Laboratório de progamação stand-alone.

A ideia deste projeto é disponibilizar um ambiente local usando a tecnologia [Docker Compose] para criar uma stack de desenvolvimento em um ambiente controlado, sem a necessidade de competir com uma infraestrutura cloud compartilhada.

Esta iniciativa visa minimizar tempo e custo, dando ao desenvolvedor(a) total liberdade para realizar seu trabalho sem comprometer o ambiente de desenvolvimento.

## Arquitetura
![docker-compose]

### Banco de Dados
#### PostgreSql

O [PostgreSQL] é um sistema de gerenciamento de banco de dados relacional de código aberto, que oferece suporte a várias funções de SQL, como: chaves estrangeiras, subconsultas, triggers, tipos e funções definidas pelo usuário.

O [PostgreSQL] é um dos bancos de dados relacionais mais estabelecidos e é utilizado em vários campos, como: serviços financeiros, manufatura, retalho, logística.

O [PostgreSQL] é conhecido por ser: robusto, seguro, extensível, conformante com os padrões SQL, pioneiro em muitos conceitos. 

Algumas das características do [PostgreSQL] são: 

* Suporte a propriedades ACID (atomicidade, consistência, isolamento e durabilidade)
* Tolerante a falhas
* Suporte a texto, imagens, sons e vídeos
* Suporte a várias linguagens de programação e protocolos
* Gerencia a concorrência de forma eficiente por meio do seu uso do MVCC (Multiversion Concurrency Control)

O [PostgreSQL] é compatível com quase todos os principais sistemas operacionais, incluindo Linux, Microsoft, OS X e Unix. 

#### PgAdmin4

O [pgAdmin4] é uma ferramenta de código aberto para administração e desenvolvimento de bases de dados do PostgreSQL: 

* É uma plataforma popular e rica em recursos 
* É útil para: 
    - Gerenciar bases de dados 
    - Restaurar e fazer backups do sistema 
    - Verificar objetos 
    - Realizar consultas 
* Tem uma interface intuitiva e uma baixa curva de aprendizado 
* Está disponível para Windows, Mac e Linux 

![pgadmin 4]
http://localhost:8087

### Infraestrutura Kafka

#### Zookeeper

O [Apache ZooKeeper] é um serviço centralizado para manter informações de configuração, nomear, fornecer sincronização distribuída e fornecer serviços de grupo.

#### Apache Kafka

O [Apache Kafka] é uma plataforma de streaming de eventos open source que permite coletar, processar, armazenar e transmitir dados em tempo real. 

O Kafka é uma alternativa aos sistemas de mensageria empresariais tradicionais e é ideal para situações que exigem escalabilidade e produtividade, como o comércio eletrônico, a Internet das Coisas (IoT) e operações de TI. 

Algumas das principais características do Kafka são: 

* Processamento de grandes volumes de dados de diversas fontes
* Entrega de dados a vários clientes simultaneamente
* Integração de dados entre aplicações e equipas
* Transmissão de dados de forma ágil e versátil
* Gerenciamento de streaming de dados
* Tolerância a falhas
* Escalabilidade horizontal

O Kafka usa o protocolo binário via TCP para transmitir mensagens em canais de dados em tempo real. 

#### Kafka Manager

[Kafka Manager], agora conhecido como CMAK (Cluster Manager for Apache Kafka), é uma ferramenta para gerir clusters do Apache Kafka. 

O CMAK permite: 
* Gerir vários clusters
* Inspecionar o estado do cluster (tópicos, consumidores, offsets, brokers, distribuição de replicação, distribuição de partição)
* Executar a eleição de replica preferida
* Gerar atribuições de partição com a opção de selecionar brokers a usar
* Executar a reatribuição de partição (com base nas atribuições geradas)
* Criar um tópico com configurações opcionais
* Apagar tópico
* Adicionar partições ao tópico existente
* Atualizar configuração para tópico existente

![kafka-manager]
http://localhost:8000

#### Kafka-UI

O [Kafka-UI] é uma interface web gratuita e de código aberto que permite monitorar e gerenciar clusters do Apache Kafka. Ele é uma ferramenta que:
* Ajuda a observar fluxos de dados
* Auxilia na detecção e solução de problemas
* Permite a gestão e análise de desempenho
* Permite rastrear métricas de brokers, tópicos, partições, produção e consumo de eventos

O [Kafka-UI] adiciona uma dimensão visual e prática à gestão de tópicos, partições e mensagens dentro do ambiente Kafka. 
O Apache Kafka é uma plataforma de streaming de eventos distribuídos de código aberto que permite:
* Coletar, processar e armazenar dados de eventos de streaming
* Criar pipelines de dados de streaming em tempo real
* Criar aplicações que se adaptam aos fluxos de dados


![kafka ui]
http://localhost:8080

## Como executar

Basta configurar as variáveis abaixo em um arquivo `.env` na raiz do projeto:

```bash
POSTGRES_DB=<dbname>
POSTGRES_USER=<user>
POSTGRES_PASSWORD=<password>
PGADMIN_DEFAULT_EMAIL=<email>
PGADMIN_DEFAULT_PASSWORD=<password>
```

E executar o comando [docker compose].

```bash
docker-compose up --detach
```

[docker-compose]:./.assets/images/docker-compose.png
[docker compose]: https://docs.docker.com/compose/
[PostgreSQL]: https://www.postgresQL.org/
[pgadmin4]: https://www.pgadmin.org/
[pgadmin 4]: ./.assets/images/pgadmin.png
[Apache ZooKeeper]: https://zookeeper.apache.org/
[Apache Kafka]: https://kafka.apache.org/
[Kafka Manager]:https://github.com/zheolong/kafka-manager
[kafka-manager]:./.assets/images/kafka-manager.png
[Kafka-UI]:https://github.com/provectus/kafka-ui
[kafka ui]:./.assets/images/kafka-ui.png