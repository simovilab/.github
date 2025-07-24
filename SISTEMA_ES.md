# Sistema

El siguiente diagrama de arquitectura tecnológica ilustra los componentes principales y los flujos de datos de nuestro ecosistema de investigación y desarrollo.

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

## Databús

> [!NOTE]
> Databús&reg; es una marca registrada de la Universidad de Costa Rica.

### Servidor

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus-005DA4?logo=github)](https://github.com/simovilab/databus)
![Static Badge](https://img.shields.io/badge/TRL-5-FFFF00)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Servidor de recolección, creación y distribución de datos del servicio de transporte público. Permite la gestión y distribución de datos estáticos (GTFS _Schedule_) y en tiempo real (GTFS _Realtime_). Expone una API REST.

### Panel de administración

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--admin-005DA4?logo=github)
](https://github.com/simovilab/databus-admin)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-media-AAAAAA)

Interfaz de administración del servidor Databús. Permite la gestión de datos estáticos y en tiempo real, así como la configuración del sistema.

### Editor GTFS

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--editor-005DA4?logo=github)
](https://github.com/simovilab/databus-editor)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-baja-555555)

Editor de datos estáticos del servicio de transporte público, compatible con el formato **GTFS** _Schedule_. Permite la creación y edición de rutas, paradas, horarios y otros datos relevantes.

### Paquete de Python

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--py-005DA4?logo=github)
](https://github.com/simovilab/databus-py)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Paquete de utilidades y herramientas y CLI (interfaz de línea de comandos) de Python para interactuar con el ecosistema de Databús y sus datos.

### Orquestador de flujo de datos

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--airflow-005DA4?logo=github)
](https://github.com/simovilab/databus-airflow)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Plataforma de gestión del flujo de datos para análisis y procesamiento en tiempo real.

### Aplicación móvil operativa

[![Static Badge](https://img.shields.io/badge/simovilab%2Fdatabus--app-005DA4?logo=github)
](https://github.com/simovilab/databus-app)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Aplicación móvil operativa para la recolección de datos de rastreo y telemetría de los vehículos de transporte público. Permite a los conductores registrar eventos, como el inicio y fin de recorridos, alertas, y otros datos relevantes.

## Infobús

> [!NOTE]
> Infobús&reg; es una marca registrada de la Universidad de Costa Rica.

### Servidor

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus-005DA4?logo=github)](https://github.com/simovilab/infobus)
![Static Badge](https://img.shields.io/badge/TRL-5-FFFF00)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Servidor de distribución de información del servicio de transporte público. Permite la gestión y distribución de contenidos para diferentes interfaces, como sitios web, aplicaciones móviles y pantallas.

### Gestor de contenidos

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--cms-005DA4?logo=github)](https://github.com/simovilab/infobus-cms)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-media-AAAAAA)

Gestor de contenidos para el servidor Infobús. Permite la creación y edición de contenidos, como noticias, alertas, y otros datos relevantes para las personas usuarias del servicio.

### Servidor MCP

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--mcp-005DA4?logo=github)](https://github.com/simovilab/infobus-mcp)
![Static Badge](https://img.shields.io/badge/TRL-3-FF8800)
![Static Badge](https://img.shields.io/badge/Prioridad-media-AAAAAA)

Servidor MCP (_Model Context Protocol_) para la interacción de agentes de inteligencia artificial (IA) con la API de Infobús, con aplicación en chats con modelos extensos de lenguaje (LLMs) y otros sistemas de IA.

### Paquete de Python

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--py-005DA4?logo=github)
](https://github.com/simovilab/infobus-py)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Paquete de utilidades y herramientas y CLI (interfaz de línea de comandos) de Python para interactuar con el ecosistema de Infobús y sus datos.

### Sitio web

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--web-005DA4?logo=github)](https://github.com/simovilab/infobus-web)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Sitio web para la consulta de información del servicio de transporte público. Permite a las personas usuarias consultar rutas, horarios, alertas y otros datos relevantes.

### Servidor de pantallas

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--screens-005DA4?logo=github)](https://github.com/simovilab/infobus-screens)
![Static Badge](https://img.shields.io/badge/TRL-2-FF4400)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Servidor de distribución de contenidos para pantallas informativas. Permite la gestión y distribución de contenidos específicos para pantallas ubicadas en paradas, vehículos y otros puntos estratégicos.

### Aplicación móvil

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--app-005DA4?logo=github)](https://github.com/simovilab/infobus-app)
![Static Badge](https://img.shields.io/badge/TRL-1-FF0000)
![Static Badge](https://img.shields.io/badge/Prioridad-baja-555555)

Aplicación móvil para la consulta de información del servicio de transporte público. Permite a las personas usuarias consultar rutas, horarios, alertas y otros datos relevantes desde sus dispositivos móviles.

### Panel de análisis de datos

[![Static Badge](https://img.shields.io/badge/simovilab%2Finfobus--data-005DA4?logo=github)](https://github.com/simovilab/infobus-data)
![Static Badge](https://img.shields.io/badge/TRL-3-FF8800)
![Static Badge](https://img.shields.io/badge/Prioridad-alta-FFFFFF)

Panel para el análisis de datos del servicio de transporte público. Permite a investigadores y analistas consultar y visualizar datos históricos y en tiempo real del servicio, facilitando la toma de decisiones informadas.

> [!NOTE]
> TRL es un acrónimo de **Technology Readiness Level** (_Nivel de madurez tecnológica_). Los niveles van del 1 al 9, donde 1 indica una investigación básica y 9 indica que la tecnología está completamente probada y lista para su uso en producción. Puede consultar la [escala aplicada](../TRL.md).
