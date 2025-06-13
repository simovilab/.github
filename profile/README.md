![simovi_horizontal](https://github.com/user-attachments/assets/c14514f1-9117-4714-8aa3-04ccaac01a32)

Escuela de Ingeniería Eléctrica | **Universidad de Costa Rica**

[🇨🇷 Español](#nuestro-trabajo) | [🇺🇸 English](#our-work) | [🇧🇷 Português](#nosso-trabalho)

## Nuestro trabajo

Investigamos tecnologías para el análisis de datos del transporte público, con énfasis en sistemas de información para las personas usuarias. Actualmente desarrollamos dos sistemas complementarios:

- **Databús**: plataforma de recolección, creación y distribución de datos del servicio de transporte público, tanto la información estática de rutas, horarios, mapas y otros, como alertas y la información en tiempo real de los vehículos.
- **Infobús**: plataforma de distribución de información del servicio para las personas usuarias del servicio de buses. Incluye múltiples medios digitales, como pantallas, sitios web y otros componentes para el uso de los datos del servicio.

## Our work

We investigate technologies for the analysis of public transportation data, with an emphasis on information systems for users. We are currently developing two complementary systems:

- **Databús**: a platform for the collection, creation, and distribution of public transportation service data, including both static information such as routes, schedules, and maps, as well as alerts and real-time vehicle information.
- **Infobús**: a service information distribution platform for bus users. It includes multiple digital media, such as screens, websites, and other components for making use of service data.

## Nosso trabalho

Investigamos tecnologias para a análise de dados do transporte público, com ênfase em sistemas de informação para as pessoas usuárias. Atualmente, estamos desenvolvendo dois sistemas complementares:

- **Databús**: plataforma para coleta, criação e distribuição de dados do serviço de transporte público, incluindo tanto informações estáticas como rotas, horários e mapas, quanto alertas e informações em tempo real dos veículos.
- **Infobús**: plataforma de distribuição de informação do serviço para as pessoas usuárias de ônibus. Inclui diversos meios digitais, como telas, sites e outros componentes para o uso dos dados do serviço.

## Sistema

```mermaid
%%{init: {'theme':'forest'}}%%
flowchart TD
    subgraph Databús
        subgraph Vehículo
            OPE@{ shape: manual, label: "Conductor"}
            SEN@{ shape: event, label: "Otros sensores"}
            OBE[Aplicación móvil]
        end
        subgraph Operaciones
            GTFS[Editor GTFS]
            DCMS[Panel de administración]
            DAT((Servidor Databús))
        end
    end

    SC@{ shape: docs, label: "GTFS Schedule"}
    RT@{ shape: doc, label: "GTFS Realtime"}
    ADM@{ shape: manual, label: "Administración"}

    subgraph Infobús
        subgraph Contenidos
            INF((Servidor Infobús))
            ICMS[Gestor de contenidos]
            MCP[Servidor MCP]
        end
        subgraph Interfaces
            WEB[Sitio web]
            SSC[Servidor de pantallas]
            APP[Aplicación móvil]
            ANA[Análisis de datos]
        end

    end
    SCR@{ shape: display, label: "Pantallas"}
    PAS@{ shape: terminal, label: "Pasajero"}
    RES@{ shape: terminal, label: "Investigador"}

OPE --> OBE
SEN --> OBE
Vehículo <--Databús API--> Operaciones
DAT --> RT
DAT --> SC

RT --> INF
SC --> INF

Contenidos <--Infobús API--> Interfaces

WEB --> PAS
SSC --> SCR
SCR --> PAS
APP --> PAS
ANA ---> RES

Operaciones <--> ADM
ADM <--> Contenidos

```

## Subsistemas

### Databús

#### Servidor `databus` [:link:](https://github.com/simovilab/databus)

![Static Badge](https://img.shields.io/badge/TRL-5-FFFF00)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Servidor de recolección, creación y distribución de datos del servicio de transporte público. Permite la gestión y distribución de datos estáticos (GTFS _Schedule_) y en tiempo real (GTFS _Realtime_). Expone una API REST.

#### Panel de administración `databus-admin` [:link:](https://github.com/simovilab/databus-admin)

![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-media-AAAAAA)

Interfaz de administración del servidor Databús. Permite la gestión de datos estáticos y en tiempo real, así como la configuración del sistema.

#### Editor GTFS `databus-editor` [:link:](https://github.com/simovilab/databus-editor)

![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-baja-555555)

Editor de datos estáticos del servicio de transporte público, compatible con el formato **GTFS** _Schedule_. Permite la creación y edición de rutas, paradas, horarios y otros datos relevantes.

#### Aplicación móvil operativa `databus-app` [:link:](https://github.com/simovilab/databus-app)

![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Aplicación móvil operativa para la recolección de datos de rastreo y telemetría de los vehículos de transporte público. Permite a los conductores registrar eventos, como el inicio y fin de recorridos, alertas, y otros datos relevantes.

### Infobús

#### Servidor `infobus` [:link:](https://github.com/simovilab/infobus)

![Static Badge](https://img.shields.io/badge/TRL-5-FFFF00)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Servidor de distribución de información del servicio de transporte público. Permite la gestión y distribución de contenidos para diferentes interfaces, como sitios web, aplicaciones móviles y pantallas.

#### Gestor de contenidos `infobus-cms` [:link:](https://github.com/simovilab/infobus-cms)

![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-media-AAAAAA)

Gestor de contenidos para el servidor Infobús. Permite la creación y edición de contenidos, como noticias, alertas, y otros datos relevantes para las personas usuarias del servicio.

#### Servidor MCP `infobus-mcp` [:link:](https://github.com/simovilab/infobus-mcp)

![Static Badge](https://img.shields.io/badge/TRL-3-FF8800)
![Static Badge](https://img.shields.io/badge/Prioridad-media-AAAAAA)

Servidor MCP (_Model Context Protocol_) para la interacción de agentes de inteligencia artificial (IA) con la API de Infobús, con aplicación en chats con modelos extensos de lenguaje (LLMs) y otros sistemas de IA.

#### Sitio web `infobus-web` [:link:](https://github.com/simovilab/infobus-web)

![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Sitio web para la consulta de información del servicio de transporte público. Permite a las personas usuarias consultar rutas, horarios, alertas y otros datos relevantes.

#### Servidor de pantallas `infobus-screens` [:link:](https://github.com/simovilab/infobus-screens)

![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Servidor de distribución de contenidos para pantallas informativas. Permite la gestión y distribución de contenidos específicos para pantallas ubicadas en paradas, vehículos y otros puntos estratégicos.

#### Aplicación móvil `infobus-app` [:link:](https://github.com/simovilab/infobus-app)

![Static Badge](https://img.shields.io/badge/TRL-1-FF0000)
![Static Badge](https://img.shields.io/badge/Prioridad-baja-555555)

Aplicación móvil para la consulta de información del servicio de transporte público. Permite a las personas usuarias consultar rutas, horarios, alertas y otros datos relevantes desde sus dispositivos móviles.

#### Panel de análisis de datos `infobus-data` [:link:](https://github.com/simovilab/infobus-data)

![Static Badge](https://img.shields.io/badge/TRL-3-FF8800)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Panel para el análisis de datos del servicio de transporte público. Permite a investigadores y analistas consultar y visualizar datos históricos y en tiempo real del servicio, facilitando la toma de decisiones informadas.
