<h1 align="center">GussCloud</h1>

<p align="center">
  <b>Arquitetura de Soluções</b> · Sistemas distribuídos, integrações e plataformas escaláveis
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Solutions-Architecture-0A66C2?style=flat-square" alt="Solutions Architecture" />
  <img src="https://img.shields.io/badge/Cloud-Native-326CE5?style=flat-square" alt="Cloud Native" />
  <img src="https://img.shields.io/badge/Event--Driven-Design-FF6B35?style=flat-square" alt="Event Driven" />
  <img src="https://img.shields.io/badge/API-First-009688?style=flat-square" alt="API First" />
</p>

###

<br clear="both">

## 🧭 Sobre

Atuo com **arquitetura de soluções**, desenhando sistemas que precisam ser **escaláveis, resilientes e integráveis**. Meu foco está em traduzir necessidades de negócio em arquiteturas técnicas sustentáveis — do desenho de domínio e contratos de API até decisões de infraestrutura, dados e integração entre sistemas.

> Boa arquitetura não é a mais complexa — é a que resolve o problema certo com o menor acoplamento possível.

###

## 🏛️ Pilares de Arquitetura

| Domínio | Foco |
|---|---|
| **Sistemas Distribuídos** | Microsserviços, comunicação assíncrona, idempotência, consistência eventual |
| **Arquitetura Orientada a Eventos** | Message brokers, filas, pub/sub, choreography vs. orchestration |
| **API & Integração** | REST, contratos bem definidos, API Gateway, webhooks, integrações entre sistemas |
| **Dados** | Modelagem relacional, polyglot persistence, estratégias de cache e leitura |
| **Cloud & Infra** | Containers, escalabilidade horizontal, observabilidade, automação |
| **IA & Automação** | Orquestração de agentes, integração com LLMs (MCP), automação de fluxos |

###

## 🧩 Padrões & Práticas

<p align="left">
  <img src="https://img.shields.io/badge/Microservices-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Microservices" />
  <img src="https://img.shields.io/badge/Event--Driven-FF6B35?style=flat-square" alt="Event Driven" />
  <img src="https://img.shields.io/badge/Domain--Driven_Design-6DB33F?style=flat-square" alt="DDD" />
  <img src="https://img.shields.io/badge/Clean_Architecture-000000?style=flat-square" alt="Clean Architecture" />
  <img src="https://img.shields.io/badge/CQRS-512BD4?style=flat-square" alt="CQRS" />
  <img src="https://img.shields.io/badge/REST_API-009688?style=flat-square" alt="REST" />
  <img src="https://img.shields.io/badge/Observability-F46800?style=flat-square&logo=grafana&logoColor=white" alt="Observability" />
  <img src="https://img.shields.io/badge/CI%2FCD-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="CI/CD" />
</p>

###

## 🗺️ Arquitetura de Referência

Visão de uma plataforma real que projeto: **orientada a eventos**, com **API Gateway**, serviços desacoplados, mensageria assíncrona, integrações com canais e provedores, e observabilidade ponta a ponta.

```mermaid
flowchart LR
    subgraph Clients["Clientes"]
        Web["Web / SPA"]
        Mobile["Mobile / PDV"]
    end

    GW["API Gateway"]

    subgraph Services["Serviços de Domínio"]
        Auth["Auth Service"]
        Core["Core / Business"]
        Pay["Pagamentos"]
        Msg["Mensageria / Canais"]
        Fiscal["Fiscal / NF-e"]
    end

    Broker(["Message Broker<br/>(pub/sub · filas)"])

    subgraph Workers["Processamento Assíncrono"]
        W1["Workers / Consumers"]
        Auto["Automação & Agentes IA"]
    end

    subgraph Data["Dados"]
        DB[("PostgreSQL · Oracle")]
        Cache[("Redis")]
    end

    subgraph External["Integrações Externas"]
        Pix["Pix / PSP"]
        Wpp["WhatsApp API"]
        TG["Telegram"]
        IG["Instagram"]
        N8N["n8n (workflows)"]
        LLM["Claude / MCP"]
        SEFAZ["SEFAZ"]
    end

    Obs["Observabilidade<br/>logs · métricas · traces"]

    Web --> GW
    Mobile --> GW
    GW --> Auth
    GW --> Core
    GW --> Pay
    GW --> Msg
    GW --> Fiscal

    Core <--> DB
    Core <--> Cache
    Core -- eventos --> Broker
    Pay -- eventos --> Broker
    Msg -- eventos --> Broker
    Fiscal -- eventos --> Broker

    Broker --> W1
    Broker --> Auto
    W1 --> DB

    Pay <--> Pix
    Msg <--> Wpp
    Msg <--> TG
    Msg <--> IG
    Fiscal <--> SEFAZ
    Auto <--> LLM
    Auto <--> N8N

    Services -.-> Obs
    Workers -.-> Obs
```

###

## 🛠️ Stack Técnica

**Linguagens & Runtime**

<p align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" height="38" alt="typescript" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="38" alt="javascript" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" height="38" alt="nodejs" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" height="38" alt="react" />
</p>

**Dados & Persistência**

<p align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" height="38" alt="postgresql" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/oracle/oracle-original.svg" height="38" alt="oracle" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" height="38" alt="mysql" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/microsoftsqlserver/microsoftsqlserver-plain.svg" height="38" alt="sqlserver" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redis/redis-original.svg" height="38" alt="redis" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sqlite/sqlite-original.svg" height="38" alt="sqlite" />
</p>

**Infra & Plataforma**

<p align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" height="38" alt="docker" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" height="38" alt="linux" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nginx/nginx-original.svg" height="38" alt="nginx" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/githubactions/githubactions-original.svg" height="38" alt="github actions" />
  <img width="10" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/grafana/grafana-original.svg" height="38" alt="grafana" />
</p>

###

## 📊 Atividade

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/GussCloud/GussCloud/output/snake-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/GussCloud/GussCloud/output/snake.svg">
  <img alt="Snake animation da contribution graph" src="https://raw.githubusercontent.com/GussCloud/GussCloud/output/snake.svg">
</picture>

###
