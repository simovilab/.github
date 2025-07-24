# Design Principles

The SIMOVI laboratory operates under a comprehensive framework of design principles that guide our research and development activities in intelligent mobility systems.

Some of these principles are derived from our published research, particularly the article "A System-Level Design for a Public Transportation Information System in Costa Rica" ([DOI](https://doi.org/10.1109/CONCAPAN63470.2024.10933847)). We also adhere to the Mobility Data Interoperability Principles ([MDIP](https://www.interoperablemobility.org/)), the [MACH](https://machalliance.org/mach-principles) Principles and the [TransitOPS](https://transitops.co/manifesto.html) Manifesto, which are also oriented towards creating sustainable, accessible, and interoperable transportation information and data analysis systems.

## SIMOVI Principles

Our ten core principles are organized into four complementary categories that address different aspects of system design: business considerations that ensure economic viability and user benefit, data principles that promote transparency and standardization, application principles that prioritize usability and accessibility, and technology principles that ensure robust and future-proof implementations.

These principles serve as the foundation for all SIMOVI projects and provide guidance for collaboration with industry partners, government agencies, and the broader research community working toward more intelligent and effective transportation systems.

### Business Principles

#### Maximize Benefits for Users

- **Statement**: A public service should prioritize the continuous improvement of its users' experience.
- **Rationale**: The economic and social benefits of technologies for public transportation derive, ultimately, from the effectiveness and convenience that it provides to its users.
- **Implications**: Continuous upgrades of the information system should be made to better address the evolving needs of its passengers.

#### Financial Sustainability and Service Affordability

- **Statement**: The implementation of new technologies must ensure proper funding so that the financial risks for the private companies, as service providers, are minimized, while keeping the costs for passengers reasonable.
- **Rationale**: Without a sustainable business model, the concession model of public transportation in Costa Rica cannot exist and, in fact, the service itself is threatened, as exemplified by several routes that are currently abandoned for the lack of companies willing to assume the operation. New operational costs derived from these technologies would worsen the situation, regardless of how useful and important they might be.
- **Implications**: The system design should be carefully planned to enable a gradual, low initial cost implementation. New legislation could be discussed to make structural changes related to, for example, the funding mechanisms for new technologies. Subsidies should also be discussed, as suggested by many technical entities.

### Data Principles

#### Service Data is Open and Standardized

- **Statement**: All data related to the service that should be provided to passengers to facilitate system usage must be open and readily accessible for public consumption.
- **Rationale**: There is an obligation for the providers of a public service to be clear and transparent about all the information that its users need to effectively make use of it, while there is an obligation of the governing bodies to coordinate the effort for sharing open and standardized transit data.
- **Implications**: The governing bodies will create the appropriate channels for sharing open data, including a technology architecture that allows sustainable evolution of the systems, available without restrictions for consumption and analysis by any interested party, including private companies, researchers, the press and others.

#### Operational Data is Shared

- **Statement**: Operational data is an asset for multiple stakeholders of the system and should be accessible for efficiency, regulation and continuous improvement.
- **Rationale**: The concession of a public service requires close inspection from governing and regulatory bodies. For this purpose, operational data is important and valuable for assessing the effectiveness and legal compliance of the company, which is in the highest public interest.
- **Implications**: The governing and regulatory bodies must rule what data needs to be shared with them. The data to be shared (occupancy, emissions, etc.) --although not necessarily publicly-- will help in examining, regulating and improving the service.

#### Common Vocabulary and Data Definitions

- **Statement**: All technological components of the system will follow a single set of concepts and definitions.
- **Rationale**: A complex technological system requires consistency among its components on the understanding of its definitions, elements and relationships. This will allow an easier expansion and integration with smart cities, in general.
- **Implications**: All databases and internal data exchanges must follow, as closely as possible, the definitions of any pre-defined, applicable standards. Service data and operational data either share a common vocabulary and data definitions or have a well-defined mapping function, avoiding duplicity or confusion in cases where legacy or external systems are included.

### Application Principles

#### Unicity of the Information

- **Statement**: The information available to the users is consistent, accurate, up-to-date and single-sourced, via as many communication channels as possible.
- **Rationale**: Passengers require information of the public transportation system as a whole. Currently, in Costa Rica, every private concessionaire is responsible for sharing the information of its service, resulting in a severe lack of availability, with less than 15% of the routes presenting complete and consistent data online and without any clear guidance on how to share this information.
- **Implications**: All concessionaires will follow the requirements for data collection and data sharing established by the governing bodies. This does not limit who can collect and share this data --for example, third-party ICT private companies-- but the technical details are previously established.

#### Ease-of-Use and Accessibility

- **Statement**: The service should be designed for all users.
- **Rationale**: Modern technological systems must be sensible to the needs of special users with different physical and cognitive abilities or background knowledge.
- **Implications**: Recommendations in service design must be followed for ensuring accessibility in graphic signage, digital media, communication strategies, and other "touch points" between the system and the users. The system should also follow from the start an internationalization (i18n) process by providing information that is understandable for most international visitors, given the importance of tourism and migration in Costa Rica. For example, translations should be made to, at least, English for wayfinding signage, alerts and other data in print and digital media. New generative artificial intelligence technologies like large language models (LLM) could and should be used to expand these capabilities.

### Technology Principles

#### Single System Architecture

- **Statement**: All stakeholders should follow and comply with the guidelines of a system-wide architecture devised by the governing bodies.
- **Rationale**: A complex system requires a well-defined blueprint to evolve more seamlessly. The internet is an essential example of a vast, intricate system with a multitude of applications and technologies, all coordinated through a set of standards and architectures. The new paradigms of design of engineering systems demand interventions with careful considerations of the complexities of a socio-technical system like public transportation.
- **Implications**: Governing bodies should function as technology planners, product owners and referees, and must develop the technical expertise required for these roles. However, in designing such an architecture, careful attention must be given to ensure it does not become an obstacle to future modernization and interoperability.

#### Technology Independence

- **Statement**: Implementations should be independent of particular technology choices, allowing them to function on multiple platforms and alongside external systems.
- **Rationale**: Technology independence results in flexibility, scalability and cost-effective implementations, while minimizing the risk of obsolescence. The accessibility and compatibility to different technology options is increased, as well as the innovation and resilience of results.
- **Implications**: Standards must be followed at major steps of the implementation. Critically, government bidding processes must add this in their requirements.

#### Interoperability

- **Statement**: Implementations should follow established standards to ensure compatibility and effective information exchange between systems.
- **Rationale**: This approach enhances efficiency by allowing seamless integration of different technologies. It reduces costs by using existing infrastructure, and fosters innovation through collaboration. Adhering to standards also ensures consistency and improves system management, while maximizing return on investment and supporting vendor integration and supply chain efficiency.
- **Implications**: A protocol for devising or adopting and reviewing relevant standards is needed. Current platforms must be identified and documented. Standards should be followed unless there is a strong business case for deviation. A digital governance mechanism should be put in place to oversee this principle.

## Mobility Data Interoperability Principles

> [!NOTE]
> Copyright © 2024 MDIP Coalition. All Rights Reserved.

From [https://www.interoperablemobility.org/](https://www.interoperablemobility.org/):

> Transit is a high-tech industry. Mobility service providers need tech components that are capable of working together in real time using standard formats.

1. All systems creating, modifying, or consuming mobility data should be interoperable.
1. Interoperability should be achieved through the development, adoption, and widespread implementation of open standards that support the efficient exchange and portability of mobility data.
1. Transit agencies and other mobility service providers should have access to tools that present high-quality mobility data accessibly, equitably, and in real time to assist travelers in meeting their mobility needs.
1. Transit agencies, other mobility service providers, and travellers should be able to select the transportation technology components that best meet their needs.
1. All individuals and the public should be empowered through high-quality, well-distributed mobility data to find, access, and utilize high-quality mobility options that meet their needs as they see fit, while maintaining their privacy.

## The TransitOPS Manifesto

> [!NOTE]
> Copyright © 2023 TransitOPS. All Rights Reserved.

From [https://transitops.co/manifesto.html](https://transitops.co/manifesto.html):

> The transit technology status quo is an obstacle to achieving equity and the standard of service that riders deserve. While locked into the current proprietary monolith vendor marketplace, public transit agencies can not easily achieve parity with other mobility providers. Therefore, TransitOPS was founded to build, promote, expand, and support open-source software solutions at every level of the transit technology stack to drive modernization while reducing cost, improving public transit experience, and making public transit itself sustainable.

### Our 10 Principles

#### Principle 1

Public Transit is an integral part of modern life—providing access to economic opportunity, education, community, civic engagement, healthcare—especially for transit-dependent populations.

#### Principle 2

Public Transit is a critical infrastructure that must remain viable and accessible to all.

#### Principle 3

Public transit riders deserve an experience that is transparent, reliable, safe, and at parity or better with other mobility options in time and cost.

#### Principle 4

Riders' security and privacy in public transit and transit data systems are fundamental and must not get treated as optional.

#### Principle 5

Agencies must have the tools and data to operate and plan an effective and equitable transit system.

#### Principle 6

The sustainability of public transit depends upon interoperability (protocols, data formats, content), innovation, and collaboration between public and private organizations.

#### Principle 7

Free and open-source software guarantees that necessary technology improvements are possible and supports a competitive marketplace for technology services.

#### Principle 8

Transparent and inclusive processes promote participation, accountability, and trust.

#### Principle 9

Commercial involvement in public transit technology brings many benefits; a balance between commercial profit and public benefit is critical.

#### Principle 10

Magnifying the public benefit aspects of public transit is an important goal, worthy of time, attention and commitment.

## MACH Principles

> [!NOTE]
> Copyright © 2025 MACH Alliance. All Rights Reserved.

From [https://machalliance.org/mach-principles](https://machalliance.org/mach-principles):

> The MACH Principles—Composable, Connected, Incremental, Open, and Autonomous—provide a roadmap for organizations to build scalable, flexible, and collaborative digital ecosystems. By aligning technology with these principles, businesses can drive continuous improvement and adapt seamlessly to change.

### Composable

#### What we support

Organizations can future-proof their digital transformation by building cohesive experiences, systems, and teams that transcend individual touchpoints, applications, and skill sets. Modular and flexible composable systems and methodologies allow brands to achieve their digital strategy in real-time, while remaining resilient enough to respond to evolving business challenges and opportunities.

The ability to easily add new capabilities through smooth evaluation, procurement, and integration ensures businesses can reach their full digital potential. SaaS and microservices enable quick deployment and flexible adoption of technologies that fit business needs, while delivering better user experiences and reducing development time and costs.

#### What we oppose

All-in-one software suites that restrict application changes or force unnecessary features can hamper an organization's market readiness and digital strategy. Monolithic software models and on-premises deployments tie an organization's capabilities to the release schedules of their vendors, limiting their ability to adapt to changing market demands.

### Connected

#### What we support

Connected MACH systems and data-driven innovation that fuels a world of automation, analytics, and enhanced user experiences. Utilizing headless APIs, organizations realize significant benefits including enhanced MACH interoperability, efficiency, integrated ecosystems, and overall effectiveness. A connected approach ensures that brands can adapt quickly to changing needs and technologies.

#### What we oppose

Siloed systems and rigid, disconnected technologies limit an organization's digital strategy potential. Top-down reporting and dashboards restrict access to real-time data, forcing teams and applications to rely on manual intervention that is prone to human error and outdated information. This results in a poor user experience, slower decision-making, and an inability to scale operations to meet market demands.

### Incremental

#### What we support

By emphasizing continuous delivery and experimentation, an incremental development approach prioritizes achieving desired outcomes over simply generating output. This approach enables faster value delivery and rapid learning through smaller and more scalable iterative releases.

API-first technologies can integrate with existing systems or run independently, enabling safe iterative innovation and experimentation. Incremental changes means organizations can reduce risk associated with large sweeping deployments, such as system failures and user resistance. The focus becomes continual improvement and higher quality outputs.

#### What we oppose

"Big bang" vendor selection and disruptive migration projects often drag on, suffering from scope creep and an inability to adapt to learnings, ultimately failing to deliver value. Large-scale changes increase risk, disrupt existing systems, and limit testing and user feedback - factors that undermine the success of business-critical "too big to fail" projects, which frequently fall short of expectations.

### Open

#### What we support

Technology, teams, and organizational strategies that are built on a culture of collaboration and transparency, aligned to the sharing of data, functions, and resources to accomplish larger organizational goals.

Open MACH architecture, supported by interoperability that exposes all functions, grants the business access to a wider, more scalable range of applications and capabilities. This includes data from headless APIs and shared standards, as well as more transparent management and observability.

#### What we oppose

Restrictive (or closed) applications limit or lock-in information, reducing transparency and preventing teams' ability to work smarter together. These practices impede interoperability, siloing data and users into disparate and disconnected systems, reducing the ability for organizations to achieve their full potential.

### Autonomous

#### What we support

By adopting an autonomous digital strategy, organizations can quickly and efficiently adapt to both internal and external requirements in real-time. This is enabled by more intelligent and automated processes, delivered through agile and adaptable MACH approaches supported by interoperable frameworks. As a result, teams and the wider organization can focus on continuous improvement and achieving their digital transformation goals.

#### What we oppose

The reliance on manual digital processes and static decision-making leads to a top-down approach limiting an organization's progress. Stifled efficiency, productivity, innovation, and creativity result in organizations spending more time and resources on cumbersome, inflexible systems and processes rather than on achieving their digital goals.
