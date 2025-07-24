# Sistema

O seguinte diagrama de arquitetura tecnológica ilustra os componentes principais e os fluxos de dados do nosso ecossistema de pesquisa e desenvolvimento.

```mermaid
%%{
  init: {
    'theme': 'base',
    'themeVariables': {
      'primaryColor': '#00C0F3',
      'primaryTextColor': '#fff',
      'primaryBorderColor': '#005DA4',
      'lineColor': '#005DA4',
      'secondaryColor': '#005DA4',
      'tertiaryColor': '#DDDDDD'
    }
  }
}%%
flowchart TD
    subgraph Databús
        subgraph Veículo
            OPE@{ shape: manual, label: "Motorista"}
            SEN@{ shape: event, label: "Outros sensores"}
            OBE[Aplicativo móvel]
        end
        subgraph Operações
            GTFS[Editor GTFS]
            DCMS[Painel de administração]
            DAT((Servidor Databús))
        end
    end

    SC@{ shape: docs, label: "GTFS Schedule"}
    RT@{ shape: doc, label: "GTFS Realtime"}
    ADM@{ shape: manual, label: "Administração"}

    subgraph Infobús
        subgraph Conteúdos
            INF((Servidor Infobús))
            ICMS[Gestor de conteúdos]
            MCP[Servidor MCP]
        end
        subgraph Interfaces
            WEB[Site web]
            SSC[Servidor de telas]
            APP[Aplicativo móvel]
            ANA[Análise de dados]
        end

    end
    SCR@{ shape: display, label: "Telas"}
    PAS@{ shape: terminal, label: "Passageiro"}
    RES@{ shape: terminal, label: "Pesquisador"}

OPE --> OBE
SEN --> OBE
Veículo <--Databús API--> Operações
DAT --> RT
DAT --> SC

RT --> INF
SC --> INF

Conteúdos <--Infobús API--> Interfaces

WEB --> PAS
SSC --> SCR
SCR --> PAS
APP --> PAS
ANA ---> RES

Operações <--> ADM
ADM <--> Conteúdos

```

## Databús

> [!NOTE]
> Databús&reg; é uma marca registrada da Universidade da Costa Rica.

### Servidor

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus-005DA4?logo=github)](https://github.com/simovilab/databus)
![Static Badge](https://img.shields.io/badge/TRL-5-FFFF00)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Servidor de coleta, criação e distribuição de dados do serviço de transporte público. Permite a gestão e distribuição de dados estáticos (GTFS _Schedule_) e em tempo real (GTFS _Realtime_). Expõe uma API REST.

### Painel de administração

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--admin-005DA4?logo=github)
](https://github.com/simovilab/databus-admin)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-média-AAAAAA)

Interface de administração do servidor Databús. Permite a gestão de dados estáticos e em tempo real, bem como a configuração do sistema.

### Editor GTFS

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--editor-005DA4?logo=github)
](https://github.com/simovilab/databus-editor)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-baixa-555555)

Editor de dados estáticos do serviço de transporte público, compatível com o formato **GTFS** _Schedule_. Permite a criação e edição de rotas, paradas, horários e outros dados relevantes.

### Pacote Python

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--py-005DA4?logo=github)
](https://github.com/simovilab/databus-py)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Pacote de utilitários e ferramentas e CLI (interface de linha de comando) Python para interagir com o ecossistema Databús e seus dados.

### Orquestrador de fluxo de dados

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--airflow-005DA4?logo=github)
](https://github.com/simovilab/databus-airflow)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Plataforma de gestão do fluxo de dados para análise e processamento em tempo real.

### Aplicativo móvel operacional

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--app-005DA4?logo=github)
](https://github.com/simovilab/databus-app)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Aplicativo móvel operacional para a coleta de dados de rastreamento e telemetria dos veículos de transporte público. Permite aos motoristas registrar eventos, como início e fim de percursos, alertas e outros dados relevantes.

## Infobús

> [!NOTE]
> Infobús&reg; é uma marca registrada da Universidade da Costa Rica.

### Servidor

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus-005DA4?logo=github)](https://github.com/simovilab/infobus)
![Static Badge](https://img.shields.io/badge/TRL-5-FFFF00)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Servidor de distribuição de informações do serviço de transporte público. Permite a gestão e distribuição de conteúdos para diferentes interfaces, como sites, aplicativos móveis e telas.

### Gestor de conteúdos

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--cms-005DA4?logo=github)](https://github.com/simovilab/infobus-cms)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-média-AAAAAA)

Gestor de conteúdos para o servidor Infobús. Permite a criação e edição de conteúdos, como notícias, alertas e outros dados relevantes para os usuários do serviço.

### Servidor MCP

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--mcp-005DA4?logo=github)](https://github.com/simovilab/infobus-mcp)
![Static Badge](https://img.shields.io/badge/TRL-3-FF8800)
![Static Badge](https://img.shields.io/badge/Prioridade-média-AAAAAA)

Servidor MCP (_Model Context Protocol_) para a interação de agentes de inteligência artificial (IA) com a API do Infobús, com aplicação em chats com modelos extensos de linguagem (LLMs) e outros sistemas de IA.

### Pacote Python

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--py-005DA4?logo=github)
](https://github.com/simovilab/infobus-py)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Pacote de utilitários e ferramentas e CLI (interface de linha de comando) Python para interagir com o ecossistema Infobús e seus dados.

### Site web

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--web-005DA4?logo=github)](https://github.com/simovilab/infobus-web)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Site para consulta de informações do serviço de transporte público. Permite aos usuários consultar rotas, horários, alertas e outros dados relevantes.

### Servidor de telas

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--screens-005DA4?logo=github)](https://github.com/simovilab/infobus-screens)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Servidor de distribuição de conteúdos para telas informativas. Permite a gestão e distribuição de conteúdos específicos para telas localizadas em paradas, veículos e outros pontos estratégicos.

### Aplicativo móvel

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--app-005DA4?logo=github)](https://github.com/simovilab/infobus-app)
![Static Badge](https://img.shields.io/badge/TRL-1-FF0000)
![Static Badge](https://img.shields.io/badge/Prioridade-baixa-555555)

Aplicativo móvel para consulta de informações do serviço de transporte público. Permite aos usuários consultar rotas, horários, alertas e outros dados relevantes a partir de seus dispositivos móveis.

### Painel de análise de dados

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--data-005DA4?logo=github)](https://github.com/simovilab/infobus-data)
![Static Badge](https://img.shields.io/badge/TRL-3-FF8800)
![Static Badge](https://img.shields.io/badge/Prioridade-alta-FFFFFF)

Painel para análise de dados do serviço de transporte público. Permite a pesquisadores e analistas consultar e visualizar dados históricos e em tempo real do serviço, facilitando a tomada de decisões informadas.

> [!NOTE]
> TRL é um acrônimo de **Technology Readiness Level** (_Nível de Prontidão Tecnológica_). Os níveis vão de 1 a 9, onde 1 indica uma pesquisa básica e 9 indica que a tecnologia está completamente testada e pronta para uso em produção. Pode consultar a [escala aplicada](../TRL.md).
