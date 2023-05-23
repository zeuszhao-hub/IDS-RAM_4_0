### ROLES IN THE INTERNATIONAL DATA SPACES ###

国际数据空间的角色定义

In the following, each role a participant can assume in the
International Data Spaces is described in detail, together with the
tasks assigned to it. The Reference Architecture model distinguishes
four "categories" containing "business roles" that, depending on the
individual business model, can assume one or more of the "basic roles".

以下是国际数据空间中参与者可能扮演的每个角色的详细描述，以及分配给它的任务。参考架构模型区分包含“业务角色”的四个“类别”，这些“业务角色”可以根据个人的商业模式扮演一个或多个“基本角色”。

#### Basic Roles in the International Data Space ###

国际数据空间中的基本角色

The ecosystem of the IDS comprises several basic tasks being carried out
by the various participants. The set of these tasks can be derived from
relevant objects in the IDS and the activities along the respective life
cycle. IDS objects that participants in the IDS have to handle are:

IDS的生态系统由各种参与者执行的几个基本任务组成。这些任务集合可以从IDS中相关的对象以及其所在生命周期的活动中推导出来。在IDS中，参与者必须处理的对象包括：

1.  **Connector**: technical core component required for a participant
    to join the International Data Spaces
2.  **Data**: here synonym to Data Asset, i.e. content exposed for
    exchange by the Data Provider
3.  **Vocabulary**: ontologies, reference data models, or metadata
    elements that can be used to annotate and describe datasets, usage
    policies, apps, services data sources etc.

4.  **Identity**: information of and for participants in the IDS

5.  **App**: applications that can be deployed inside the connector.
    Apps facilitate data processing workflows. They may be certified by
    a Certification Body, following the certification procedures defined
    in the [Certification Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/README.md).

6.  **Transaction**: comprises all activities performed in the course of
    a data exchange

7.  **Service**: software running in a connector and provided as a
    service (algorithm and computing time)

 
 
1. 加入国际数据空间所需的技术核心组成部分。
2. 这里的同义词是“数据资产”，即由数据提供者提供以进行交换的内容。
3. 词汇：本体论、参考数据模型或元数据元素，可用于注释和描述数据集、使用政策、应用程序、服务数据源等。译者：标记特定行业数据的说明字典
4. IDS参与者的身份
5. 应用程序：可以部署在连接器内部的应用程序。应用程序有助于数据处理工作流程。它们可以通过认证机构进行认证，遵循[认证视角]中定义的认证程序。
6. 交易：包括在数据交换过程中执行的所有活动。
7. 服务：在连接器中运行并作为服务提供的软件（算法和计算时间）。

For each of these IDS objects, the Reference Architecture Model defines
activities along the life cycle define. The set of activities, or a
subset of it, that describe the life cycle of the objects are:

对于每个IDS对象，参考架构模型定义了沿着生命周期定义的活动。描述对象生命周期的活动集或其子集包括：

1. **Create**: create an object, e.g. software by programming or data
    from reading a sensor

2. **Own**: own an object or hold the corresponding license or right
    according to local rules and regulations

3. **Certify/verify**: e.g. certify software according to the IDS
    certification scheme or verify authenticity of data

4. **Publish**: share meta data on objects such as data, apps, services
    etc.

5. **Provide**: technically provide the object

6. **Consume**: technically receive the object

7. **Use**: make use of an object in a business model that does not
    consist of an intermediary function (see below)

8. **Delete**: Delete, eliminate or turn object off


Each activity along the life cycle of an IDS object is carried out by a
participant of the IDS. A role that a participant takes to carry out
these activities is called "basic role". As some combinations from an
IDS object and an activity (e.g. "verify data", "delete identity") may
be relevant in other contexts than the IDS RAM or may become relevant in
the future, some potential basic roles are declared as (currently) "out
of IDS RAM scope". The table below shows the basic roles defined in the IDS.

IDS对象生命周期中的每个活动都由IDS的参与者执行。参与者执行这些活动所扮演的角色称为“基本角色”。由于一些IDS对象和活动的组合可能在IDS RAM之外的其他上下文中或将来有用，因此一些潜在的基本角色被声明为（目前）“超出IDS RAM范畴”。下面的表格显示了IDS中定义的基本角色。

|                 |       **Create**      |       **Own**      | **Certify / Verify** |       **Publish**       |       **Provide**      |      **Consume      |         **Use**         |      **Delete**     |  
|-----------------|:---------------------:|:------------------:|:--------------------:|:-----------------------:|:----------------------:|:-------------------:|:-----------------------:|:-------------------:|
| **Connector**   |   Connector Creator   |   Connector Owner  |  Connector Certifier |   Connector Publisher   |   Connector Provider   |  (Out of RAM scope) |      Connector User     |  (Out of RAM scope) |
| **Data**        |      Data Creator     |     Data Owner     |  (Out of RAM scope)  | Connector / Metadata Broker |      Data Provider     |    Data Consumer    |        Data User        |     Data Eraser     |
| **Vocabulary**  |   Vocabulary Creator  |  Vocabulary Owner  |  (Out of RAM scope)  |   Vocabulary Publisher  |   Vocabulary Provider  | Vocabulary Consumer |     Vocabulary User     |  (Out of RAM scope) |
| **Identity**    |    Identity Creator   |   Identity Owner   | Identity Verificator |   Identitiy Publisher   | Identity Authenticator |  (Out of RAM scope) |      Identity User      | Identity Eliminator |
| **App**         |      App Creator      |      App Owner     |     App Certifier    |        App Broker       |      App Provider      |     App Consumer    |         App User        |   App Deleter (?)   |
| **Transaction** | Transaction Initiator | (Out of RAM scope) |  Transaction Clearer |    (Out of RAM scope)   |   (Out of RAM scope)   |  (Out of RAM scope) | Transaction Participant |  (Out of RAM scope) |
| **Service**     |    Service Creator    |    Service Owner   |   Service Certifier  |      Service Broker     |    Service Provider    |   Service Consumer  |       Service User      |  (Out of RAM scope) |

These basic roles are suitable to define technical tasks in the IDS and
roles of the participants in detail. As this quite large number is,
however, bulky especially for early discussions, grouping basic roles to
business roles is advisable. The basic roles are explained in a suitable
context of the business roles.

这些基本角色适用于在IDS中定义技术任务和参与者的角色。然而，由于这些角色数量较大，尤其是在早期讨论中，将基本角色分组为业务角色是明智的。基本角色在业务角色的适当上下文中得到了解释。

#### Business Roles in the International Data Space ####

在国际数据空间中的业务角色

On the level of the business layer, depending on the use case, it might
not be crucial to distinguish between basic roles. E.g. if an industrial
company intends to provide quality check data to a supply chain partner,
the distinction between data owner and data creator is unnecessary.
Hence, business roles are introduced. Business roles comprise one or
more basic role. Their exact scope of comprised basic roles depends on
the individual business model of the participant as individual business
models (including pricing models) may be applied as deemed appropriate.
E.g. a data intermediary (see details below) operating a data hub may
store data as a trustee, act as a Metadata Broker or do both -- depending on the
business model. Therefore, as the assignment of basic roles to a
business role may vary, the assignment is marked with the following
symbols:

在业务层面上，根据具体用例，区分基本角色可能并不重要。例如，如果一个工业公司打算向供应链合作伙伴提供质量检查数据，则无需区分数据所有者和数据创建者。因此，引入了业务角色。业务角色包括一个或多个基本角色。它们涵盖的基本角色的具体范围取决于参与者的个体业务模型，可以根据自己的判断应用个体业务模型（包括定价模型）。例如，运营数据中介的数据集线器的数据可以作为受托人存储，也可以作为元数据经纪人，或两者兼而有之，具体取决于业务模式。因此，由于分配基本角色到业务角色的方式可能会不同，所以将其分配标记如下：

- **T** (typical): basic role typically taken by a business role

- **M** (mandatory): required role from a technical perspective

 
 
- **T**（典型）：业务角色通常扮演的基本角色
- **M**（强制）：从技术角度来看必须扮演的角色

There are four categories of roles:

列出4中角色类别

* Category 1: Core Participant
* Category 2: Intermediary
* Category 3: Software Developer
* Category 4: Governance Body


* 类别1：核心参与方
* 类别2：中介机构
* 类别3：软件开发者
* 类别4：治理机构

#### CATEGORY 1: CORE PARTICIPANT ####

Core Participants are involved and required every time data is exchanged
in the International Data Spaces. Roles assigned to this category are
Data Supplier and Data Customer. The role of a Core Participant can be
assumed by any organization that owns, wants to provide, and/or wants to
consume or use data.

核心参与方在国际数据空间中交换数据的每个环节都会涉及到，其类别包括数据供应商和数据客户。任何想要拥有、提供、消费或使用数据的组织都可以扮演核心参与方的角色。

Benefit for participants in the International Data Spaces is created by
these roles as they create, potentially own and possibly provide data as
well as receive, process and most likely at some point in time delete
data.

这些角色对于国际数据空间中的参与者来说具有重要意义，因为它们可能创造、拥有和提供数据，也可能接收、处理和删除数据，进而带来利益。

##### DATA SUPPLIER ####

数据供应商

The Data Supplier is a role that induces data into the IDS ecosystem.
Depending on the individual business and technical operation model, the
business role Data Supplier typically assumes the basic roles Data
Creator, Data Owner, and/or Data Provider.

数据供应商是将数据引入国际数据空间生态系统的角色。根据个体的业务和技术运营模型，业务角色数据供应商通常会扮演基本角色数据创建者、数据所有者和/或数据提供者。

The **Data Creator** creates data, e.g. by generating data such as from
a sensor or accessing data in backend IT systems.

数据创建者创建数据，例如通过从传感器生成数据或从后端IT系统访问数据。

As the legal situation regarding data ownership is very complicated (as
discussed in the [Governance Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_3_Governance_Perspective/4_3_Governance_Perspective.md)), the term '**Data Owner'** is not used in a
legal understanding in this document. The Reference Architecture Model
takes an operational data management perspective, defining a Data Owner
as a legal entity or natural person executing control over data. This
enables the Data Owner to define Data Usage Policies and provide access
to its data. Data Ownership includes at least two major concepts:

由于有关数据所有权的法律情况非常复杂（正如在[治理视角](../../4_Perspectives_of_the_Reference_Architecture_Model/4_3_Governance_Perspective/4_3_Governance_Perspective.md)中所讨论的），因此在本文档中，术语“数据所有者”不以法律意义使用。参考架构模型采用运营数据管理视角，将数据所有者定义为执行对数据进行控制的法人或自然人，从而使得数据所有者可以定义数据使用策略并授权他人访问其数据。数据所有权包括至少两个主要概念：

* having the (technical) means and the responsibility to define Usage
Contracts and Usage Policies, and to provide access to data; and

* having the (technical) means and the responsibility to define the
Payment Model, including the model for reuse of data by third parties.


* 具备定义使用合同和使用策略以及提供数据访问的（技术）手段和责任；
* 具备定义支付模型（包括第三方重复使用数据的模型）的（技术）手段和责任。

The **Data Provider** makes data technically available in the IDS for
being transmitted to a Data Customer on behalf of the Data Owner. To
submit metadata to a Metadata Broker, or exchange data with a Data Consumer, the
Data Provider uses software components that are compliant with the
Reference Architecture Model of the International Data Spaces. Compliant
software is available from Software Developers and App Developers.

数据提供商在代表数据所有者的情况下，使数据在IDS中技术上可用于传输给数据客户。为向元数据代理提交元数据或与数据消费方交换数据，数据提供商使用符合国际数据空间参考架构模型的软件组件。符合的软件由软件开发人员和应用程序开发人员提供。

Usually, a participant acting as a Data Creator automatically assumes
the role of the Data Owner. However, if rights or licenses on data are
given to different participant, the same assumes the role of the Data
Owner. In this case, Data Owner and Data Creator would be different
participants.

通常情况下，扮演数据创建者角色的参与方自动扮演数据所有者的角色。但是，如果数据的权利或许可证被授予给不同的参与方，则该参与方将扮演数据所有者的角色。在这种情况下，数据所有者和数据创建者将是不同的参与方。

Initially, a participant acting as a Data Creator automatically assumes
the role of the Data Provider as well. However, there may be cases in
which the Data Provider is not the Data Creator, e.g. if the data is
technically managed by a different entity than the Data Creator. This
can be the case of a company using an external IT service provider for
data management, or if data management activities are handed over to a
Data Intermediary (cf. below) as a data trustee.

最初，扮演数据创建者角色的参与方自动扮演数据提供商的角色。但是，在某些情况下，数据提供商可能不是数据创建者，例如，如果数据由不同于数据创建者的实体技术管理。这可以是公司为数据管理使用外部IT服务提供商的情况，或者将数据管理活动作为数据受托人（见下文）移交给数据中介的情况。

In cases in which the Data Owner does not act as the Data Provider at
the same time, the only activity of the Data Owner is to authorize a
Data Provider to make its data available to be used by a Data Consumer.
Any such authorization should be documented by a contract, which should
include data usage policy information for the data provided (see
[Usage Control in IDS](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_6_Usage_Control.md)). The contract needs not necessarily be a paper
document, but may be an electronic file as well.

在数据所有者不同时兼任数据提供商的情况下，数据所有者唯一的活动是授权数据提供商将其数据提供给数据消费方。任何此类授权都应该由合同进行记录，该合同应该包括所提供数据的数据使用政策信息（详见[IDS中的使用控制](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_6_Usage_Control.md)）。合同可以是电子文件，而不一定是纸质文档。

At the end of a complete or partial data transaction, for example, the
Data Provider may log the details of the successful (or unsuccessful)
completion of the transaction at a Clearing House (see below) to
facilitate billing or resolve a conflict. Furthermore, the Data Provider
can use Apps in the IDS connector to enrich or transform the data in
some way, or to improve its quality. Data Apps are specific applications
that can be loaded into the IDS connector and, thus, linked into the
data exchange workflow.

例如，在完成完整或部分数据交易的最后，数据提供商可以在清算所（见下文）记录成功（或不成功）完成交易的详细信息，以促进结算或解决冲突。此外，数据提供商可以使用IDS连接器中的应用程序以某种方式丰富或转换数据，或提高其质量。数据应用程序是特定的应用程序，可以加载到IDS连接器中，从而链接到数据交换工作流程中。

##### DATA CUSTOMER #####

数据消费方

The **Data Consumer** receives data from a Data Provider. From a
business process modeling perspective, the Data Consumer is the mirror
entity of the Data Provider; the activities performed by the Data
Consumer are therefore similar to the activities performed by the Data
Provider.

**数据消费方**从数据提供商那里接收数据。从业务流程建模的角度来看，数据消费方是数据提供商的镜像实体；因此，数据消费方执行的活动类似于数据提供商执行的活动。

If data is processed by a Service Provider (see below), the Data
Customer takes the role of a **Service Consumer**. This constellation may
occur, e.g. when the Data Owner/Provider attaches usage policies to the
data that require data being processed by a third-party service (i.e.
Service Provider) before being handed to the consumer. Then, the Data
Customer is both Data Consumer and Service Consumer.

如果数据由服务提供商（见下文）处理，则数据客户端扮演**服务消费方**的角色。例如，当数据所有者/提供商将使用政策附加到数据时，要求第三方服务（即服务提供商）处理数据后才将其交付给消费方。因此，数据客户端既是数据消费方也是服务消费方。

Similar to the Data Owner being the legal entity that has the legal
control over its data, the **Data User** is the legal entity that has
the legal right to use the data of a Data Owner as specified by the
usage policy. The Data User can be identical with the Data Consumer.
However, there may be scenarios in which these roles are assumed by
different participants. For example, a patient could use a web-based
software system to manage their personal health data and grant access to
this data to a health coach. The data could be received from a hospital.
In this case, the health coach would be the Data User and the provider
of the web-based software system would be the Data Consumer.

类似于数据所有者是具有其数据的法律控制权的法律实体一样，**数据用户**是具有根据使用政策规定使用数据所有者的数据的法律权利的法律实体。数据用户可以与数据消费方相同。但是，在某些情况下，这些角色可能由不同的参与者扮演。例如，患者可以使用基于Web的软件系统来管理其个人健康数据，并授权健康教练访问这些数据。数据可以从医院接收。在这种情况下，健康教练将是数据用户，而提供基于Web的软件系统的服务商将成为数据消费方。

In existing, mostly quite static relations, the Data Customer and Data
Supplier already know each other and intend to exchange specific data
sets (e.g. capacity information for a particular part to be produced).
In these cases, the Data Consumer directly requests data (and the
corresponding metadata) from the Data Provider or the Data Provider
pushes data directly to the Data Consumer.

在现有的、大多数情况下相当静态的关系中，数据客户端和数据供应商已经相互了解，打算交换特定的数据集（例如，用于生产特定零件的容量信息）。在这些情况下，数据消费方直接从数据提供商请求数据（以及相应的元数据），或者数据提供商直接将数据推送给数据消费方。

If the Data Customer searches for a type of data that is provided by
many suppliers, .e.g. weather data, the Data Consumer can search for
existing datasets by making an inquiry at a Data Intermediary that
assumes the basic role of a Metadata Broker (cf. according section below).
The Data Intermediary (Metadata Broker) then provides the required metadata
for the Data Consumer to connect to a Data Provider.

如果数据客户端正在搜索由许多供应商提供的某个类型的数据（例如，天气数据），则数据消费方可以通过向数据中介发出查询来搜索现有的数据集。该数据中介具有元数据代理的基本作用（参见下文）。然后，数据中介（元数据代理）提供所需的元数据以便数据消费方连接到数据提供商。

Like a Data Provider, the Data Consumer may log the details of a
successful (or unsuccessful) data exchange transaction at a Clearing
House, use Apps to enrich, transform, etc. the data received, or use a
Metadata Broker to retrieve data sources.

与数据提供商类似，数据消费方可以在清算中心记录成功或失败的数据交换事务的详细信息，使用应用程序来丰富、转换等接收到的数据，或使用元数据代理来检索数据源。

#### CATEGORY 2: INTERMEDIARY #####

中介

Intermediaries act as trusted entities and are commonly considered as
"platforms". They assume a rather central role compared to the great
number of data suppliers and customers, though multiple, especially
competitive platforms of the same role may and shall exist. Business
Roles assigned to this category are Data Intermediary, Services
Intermediary, App Store, Vocabulary Intermediary, Clearing House, and
Identity Authority. Most likely, the business models of intermediaries
will lead to a combination of some of the business roles, e.g. act as
both Data and Service Intermediary.

中介机构是可信实体，通常被视为“平台”。与大量的数据供应商和消费者相比，它们扮演相对中心的角色，尽管可能会存在多个具有相同职责的、尤其是竞争性的平台。此类别分配的业务角色包括数据中介、服务中介、应用商店、词汇中介、清算中心和身份认证机构。最可能，中介机构的商业模式将导致一些业务角色的组合，例如同时充当数据和服务中介。

The Intermediary roles may be assumed only by trusted organizations.
They create benefit for participants in the IDS by establishing trust,
providing metadata, and creating a business model around their services.

只有受信任的组织才能承担中介机构的角色。它们通过建立信任、提供元数据和围绕其服务创建商业模式，为 IDS 中的参与者创造了好处。

##### Data Intermediary #####

数据中介

The Data Intermediary is a platform operator that assumes mainly the
data-related basic roles Data Provider/Data Consumer and Metadata Broker.

数据中介是一个平台运营者，主要扮演与数据相关的基本角色，即数据提供者/数据消费方和元数据代理。

Assuming the basic role of a **Data Provider** or **Data Consumer**, the
Data Intermediary is responsible for the execution of the data exchange
on behalf of the Data Owner or User respectively. Providing a Data
Consumer with data is, hence, the main activity of the Data Provider.

作为数据提供者或数据消费方的基本角色，数据中介机构代表数据所有者或用户执行数据交换，并对此负责。因此，向数据消费方提供数据是数据提供者的主要活动。

To facilitate a data request from a Data Consumer, the Data Intermediary
would provide a **Data Broker** with proper metadata about the data.
Acting as a Metadata Broker, the Data Intermediary stores and manages
information about the data sources available in the International Data
Spaces. An organization offering metadata brokering in the International
Data Spaces may assume other intermediary basic roles at the same time
(e.g. Service Broker, Clearing House or Identity Authority, see below).
Assuming further basic roles consequently means additional tasks a
participant has to execute.

为了促进数据消费方的数据请求，数据中介机构会向数据经纪人提供有关数据的适当元数据。作为元数据代理，数据中介机构存储和管理有关国际数据空间中可用的数据源的信息。在国际数据空间中提供元数据代理服务的组织可能同时承担其他中介机构的基本角色（例如服务代理、清算中心或身份认证机构，见下文）。连续承担其他基本角色意味着参与者需要执行额外的任务。

The activities of the Metadata Broker mainly focus on receiving and
providing metadata. The Metadata Broker must provide an interface for Data
Creators to send their metadata. The metadata should be stored in an
internal repository for being queried by Data Consumers in a structured
manner. While the core of the metadata model must be specified by the
International Data Spaces (i.e. by the Information Model, see
[Information Layer](../3_3_Information_Layer/3_3_InformationLayer.md)), a Metadata Broker may extend the metadata model to manage additional
metadata elements.

元数据代理的活动主要集中在接收和提供元数据。元数据代理必须为数据创建者提供接口，以便发送它们的元数据。元数据应该以结构化的方式存储在内部存储库中，以供数据消费方查询。虽然元数据模型的核心必须由国际数据空间指定（即由信息模型指定，参见[信息层](../3_3_Information_Layer/3_3_InformationLayer.md)），但元数据代理可以扩展元数据模型以管理其他元数据元素。

After the Metadata Broker has provided the Data Consumer with the metadata
about a certain Data Provider, it is not involved in the subsequent data
exchange process.

在元数据代理将有关某个数据提供者的元数据提供给数据消费方之后，它不参与后续的数据交换过程。

##### Service Intermediary #####

服务中介

A service offers e.g. data analysis, data integration, data cleansing,
or semantic enrichment to improve the quality of the data exchanged in
the International Data Spaces. Analogously to the Data Intermediary, the
Service Intermediary is a platform operator providing metadata on
services, the services itself (i.e. app including computing time as a
trustee), or both. Hence, the Service Intermediary typically assumes
mainly the service-related basic roles of the Service Provider and/or
Service Broker.

服务提供例如数据分析、数据集成、数据清洗或语义增强等服务，以提高在国际数据空间中交换的数据的质量。类似于数据中介机构，服务中介机构是一个平台运营商，提供有关服务的元数据、服务本身（即包括计算时间的应用程序）或两者。因此，服务中介机构通常主要承担服务提供者和/或服务经纪人相关的基本角色。

A **Service Provider** receives data from a Data Provider (or another
Service Provider) and either returns the calculation result to the same
or directs it to an indicated Data Consumer (which then is a Service
Consumer at the same time). The participant who receives processed data
from a Service Intermediary could be again a Service Intermediary as
data can be routed through an arbitrary number of instances of services
in the IDS.

服务提供者从数据提供者（或另一个服务提供者）接收数据，然后将计算结果返回给同一方或将其指向指定的数据消费方（此时它也是服务消费方）。从服务中介机构接收处理后的数据的参与者可以再次是服务中介机构，因为数据可以通过 IDS 中任意数量的服务实例进行路由。

In order to provide the service, the Service Provider installs apps in
its IDS connector that can be developed by the participant himself or
from a third-party App Provider. The Service Intermediary is then an App
Consumer. Just like in the case of data, the Service Owner might be a
different organization than the Service Provider. The Service Provider
then operates the service on behalf of the owner.

为了提供服务，服务提供者在其 IDS 连接器中安装应用程序，这些应用程序可以由参与者自己或第三方应用程序提供者开发。服务中介机构随后成为应用程序消费方。就像数据一样，在这种情况下，服务所有者可能是与服务提供者不同的组织。因此，服务提供者代表所有者操作服务。

To allow other participants in the IDS to retrieve available services,
Service Intermediaries may also assume the role of the **Service
Broker**. The Service Broker provides metadata on present services in
the IDS analogously to the Metadata Broker.

为了使 IDS 中的其他参与者检索到可用服务，服务中介机构也可以担任服务经纪人的角色。服务经纪人类似于元数据经纪人提供 IDS 中现有服务的元数据。

##### APP STORE #####

应用市场

The business role of the App Store is responsible to distribute data
apps. In contrary to the Service Provider, the algorithm is not executed
in the platform of the App Store, but provided for download to the IDS
connector of the App Consumer. App Consumer and App Owner may be
different, if the owner acquires (purchases) an app, but lets it be
distributed to Service Provider. The App Store role typically comprises
the basic roles of the App Broker and App Provider. Apps are programmed
by the App Creator that can, but does not have to be identical to the
App Owner (cf. Data Owner/Creator above).

应用商店的商业角色负责分发数据应用程序。与服务提供者相反，算法不在应用商店的平台上执行，而是提供为应用程序消费方的 IDS 连接器下载。如果所有者购买应用程序但让服务提供者分发，则应用程序消费方和应用程序所有者可能是不同的。应用商店角色通常包括应用程序经纪人和应用程序提供者的基本角色。应用程序由应用程序创建者编写，但不一定需要与应用程序所有者相同（参见上述数据所有者/创建者）。

The App Store is first responsible for managing information about apps.
This is the **Metadata Broker** role. The App Store should provide
interfaces for publishing and retrieving apps plus corresponding
metadata. In most cases, the App Store will, secondly, also assume the
basic role of the **App Provider** as it is common for mobile phone app
stores. The App Store then technically provides the app on behalf of the
App Owner. However, not only data, but also apps may be sensitive and,
therefore, shall be stored in the sphere of the App Owner. In this case,
the App Broker and App Provider roles would be taken be different
participants.

应用商店首先负责管理应用程序信息，这是元数据经纪人的角色。应用商店应该提供发布和检索应用程序以及相应元数据的接口。在大多数情况下，应用商店还将担任应用程序提供者的基本角色，这在手机应用商店中很常见。应用商店然后在技术上代表应用程序所有者提供应用程序。但是，不仅数据，还有应用程序可能是敏感的，因此应存储在应用程序所有者的领域中。在这种情况下，应用程序经纪人和应用程序提供者角色将由不同的参与者扮演。

Depending on the business model, an App Store could also comprise the
**App Owner** role as the store may own the license for particular apps.
As the App Store might take responsibility for the validity and
functionality of the apps provided, the App Store could also act as an
**App Certifier**.

根据不同的商业模式，应用商店也可以包括应用程序所有者的角色，因为商店可能拥有特定应用程序的许可证。由于应用商店可能对提供的应用程序的有效性和功能性负责，因此应用商店也可以作为应用程序认证机构发挥作用。

##### VOCABULARY Intermediary #####

The Vocabulary Intermediary technically manages and offers vocabularies
(i.e. ontologies, reference data models, or metadata elements). The
Vocabulary Intermediary typically assumes the basis roles of the
Vocabulary Publisher and Vocabulary Provider. Vocabularies are owned and
governed by the according Standardization Organization (cf. category 4).

词汇中介机构技术上管理和提供词汇（即本体、参考数据模型或元数据元素）。词汇中介机构通常承担词汇发布者和词汇提供者的基本角色。词汇由相应的标准化组织拥有和管理（参见类别4）。

Vocabularies can be used to annotate and describe data assets. These
data assets may comprise at least:

词汇可以用于注释和描述数据资产。这些数据资产可能至少包括以下内容：

- **Information Model** of the International Data Spaces, which is the
    basis for the description of data sources (see [Information Layer](../3_3_Information_Layer/README.md)). There
    is only one information model in the IDS governed by the IDSA.

- **Domain-specific vocabularies**: They are essential for the
    scalability and success of the IDS. Domains are e.g. represented in
    the very common set of linked open data (LOD). For example, "gene
    ontology" is a unified vocabulary for parts of life sciences, "GAO"
    for the automotive industry, etc.

- **Legal terms**: To describe usage policies and to enable smart
    contracting, legal terms must be coded in a machine-readable and
    -understandable manner. The IDS Information Model defines the Open
    Digital Rights Language (ODRL) to describe usage policies. Still,
    IDS communities such as a (closed) supply chain network or a
    domain-specific IDS initiative could define additional
    (complementary or alternative) vocabularies, e.g. depict the
    International Commercial Terms (Incoterms) as an ontology or
    reference to the iShare Scheme.


- 国际数据空间（IDS）的信息模型，它是描述数据源的基础（请参见[信息层](../3_3_Information_Layer/README.md)）。在IDS中只有一个由IDSA管理的信息模型。
- 领域专用词汇：它们对IDS的可扩展性和成功至关重要。领域通常在联接开放数据（LOD）的非常普遍的集合中表示。例如，“基因本体论”是生命科学的部分所使用的统一词汇，“GAO”用于汽车工业等。
- 法律条款：为了描述使用政策并使智能合同成为可能，法律条款必须以机器可读且可理解的方式进行编码。IDS信息模型定义了开放数字权利语言（ODRL）来描述使用政策。然而，IDS社区，如（关闭的）供应链网络或领域专用的IDS倡议，可以定义附加的（补充或备选的）词汇，例如以本体论形式描述国际商业条款（Incoterms），或参考iShare计划。

There is no dedicated or exclusive role that creates vocabularies.
Usually, standardization organizations such as ISO, EN, IEEE etc., but
also industrial associations define standards that can be formulated as
a vocabulary (Vocabulary Creators and Owners). Except the IDS
information model, there can be multiple vocabularies describing the
same context (e.g. different types of smart contracts or usage policy
descriptions). A single vocabulary for the same context support
standardization and, thus, compatibility efforts. Multiple vocabularies
provide flexibility and competitiveness.

没有专门或独立的角色来创建词汇。通常，标准化组织例如ISO、EN、IEEE等以及行业协会定义标准，可以将其制定为词汇（词汇创建者和所有者）。除了IDS信息模型外，可能存在多个描述相同上下文的词汇（例如不同类型的智能合同或使用政策描述）。为相同上下文提供单一词汇支持标准化和兼容性工作。多个词汇提供了灵活性和竞争力。

To find the right and latest vocabulary, they must be retrievable with
the help of a **Vocabulary Publisher**. This is a repository of
vocabulary metadata. In most cases, as vocabularies are usually (for the
sake of their purpose) open, the Vocabulary Intermediary will also act
as a **Vocabulary Provider**, i.e. providing the vocabulary technically
for download.

为了找到正确和最新的词汇，必须借助于**词汇发布者**来检索。它是词汇元数据的存储库。在大多数情况下，由于词汇通常（出于其目的）是开放的，因此词汇中介将充当**词汇提供者**，即在技术上提供词汇供下载。

Vocabulary Users are all instances using vocabularies, e.g. Data
Suppliers, Data Customers, Service Intermediaries, Data Intermediaries,
App Stores, etc. Also the Vocabulary Intermediary possibly may use a
vocabulary to describe the vocabulary repository.

使用词汇的所有实例都是词汇使用者，例如数据供应商、数据客户、服务中介、数据中介、应用商店等。词汇中介可能还可以使用词汇来描述词汇存储库。

##### CLEARING HOUSE #####

The Clearing House is an intermediary that provides clearing and
settlement services for all financial and data exchange transactions. In
the International Data Spaces, clearing activities are separated from
any broker services, since these activities are technically different from
maintaining a metadata repository. As already stated above, it might
still be possible that the role Clearing House and other intermediary
roles are assumed by the same organization, as both roles require acting
as a trusted intermediary between the Data Supplier and the Data
Customer.

清算所是为所有金融和数据交换交易提供结算和清算服务的中介机构。在国际数据空间中，清算活动与任何经纪服务分开，因为这些活动在技术上与维护元数据存储库不同。如上所述，仍然可能存在清算所角色和其他中介角色由同一组织承担的情况，因为这两个角色都需要在数据供应商和数据客户之间充当可信赖的中介机构。

The Clearing House logs all activities performed in the course of a data
exchange, thus, assuming the role of the **Transaction Clearer**. After
a data exchange, or parts of it, has been completed, both the Data
Supplier and the Data Customer confirm the data transfer by logging the
details of the transaction at the Clearing House, e.g. by means of
distributed ledger technologies. Based on this logging information, the
transaction can then be billed. The logging information can also be used
to resolve conflicts (e.g., to clarify whether a data package has been
received by the Data Customer or not). The Clearing House also provides
reports on the performed (logged) transactions for billing, conflict
resolution, etc.

清算所记录了数据交换过程中执行的所有活动，从而承担了**事务清算者**的角色。在数据交换或其部分完成后，数据供应商和数据客户通过记录交易细节来确认数据传输，例如通过分布式账本技术。基于此记录信息，可以对交易进行结算。记录信息还可以用于解决冲突（例如，澄清数据包是否已被数据客户接收）。清算所还提供执行（记录）交易的报告，用于结算、冲突解决等。

##### Identity Authority #####

The Identity Authority should offer a service to create, maintain,
manage, monitor, and validate identity information of and for
participants in the International Data Spaces. This is imperative for
secure operation of the International Data Spaces and to avoid
unauthorized access to data. Hence, every participant in the IDS
inevitably owns an identity (describing the respective participant) and
uses an identity for authentication.

身份认证机构应该提供一项服务，用于创建、维护、管理、监控和验证国际数据空间参与者的身份信息。这对于国际数据空间的安全运营和避免未经授权的数据访问是必不可少的。因此，在IDS中，每个参与者都必然拥有一个身份（描述其各自的身份），并使用身份进行身份验证。

The Identity Authority consist of a Certification Authority (managing
digital certificates for the participants of the International Data
Spaces), a Dynamic Attribute Provisioning Service (DAPS, managing the
dynamic attributes of the participants), and a service named Dynamic
Trust Monitoring (DTM, for continuous monitoring of the security and
behavior of the network. More details about identity management can be
found in the [security perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

身份认证机构由认证机构（管理国际数据空间参与者的数字证书）、动态属性提供服务（DAPS，管理参与者的动态属性）以及名为动态信任监控（DTM）的服务组成，用于持续监测网络的安全和行为。有关身份管理的更多详细信息，请参阅[安全视角](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md)。

Typically, identities are created by the Identity Authority, then acting
as an **Identity Creator**. In the sense of a directory, the authority
would also publish the identity if desired by the owner and especially
provide certificates, DAPS etc. for authentication purposes. These are
the basic roles **Identity Publisher** and **Identity Authenticator**.

通常，身份由身份认证机构创建，然后充当**身份创建者**。在目录的意义下，如果所有者需要，该机构还会发布身份，特别是提供证书、DAPS等进行身份验证。这就是**身份发布者**和**身份验证者**的基本角色。

#### CATEGORY 3: SOFTWARE DEVELOPER ####

This category comprises IT companies providing software to the
participants of the International Data Spaces. Roles subsumed under this
category are the business roles App Developer and Connector Developer.

该类别包括为国际数据空间的参与者提供软件的IT公司。包括业务角色应用程序开发人员和连接器开发人员。

Benefit is created by these roles by providing software to the
participants of the International Data Spaces. Please note that the
process of providing software to be used for establishing the endpoints
of a data exchange transaction (e.g. Enterprise Systems like ERP or MES,
or other platforms) is not part of the International Data Spaces, as it
takes place before an organization joins the IDS.

这些角色通过向国际数据空间的参与者提供软件创造价值。需要注意的是，为建立数据交互事务的端点提供软件的过程（例如，企业系统如ERP或MES或其他平台）不是国际数据空间的一部分，因为它是在组织加入IDS之前进行的。

##### App Developer #####

App Developers develop data apps to be used in an IDS Connector. Thus,
the App Developer typically covers the basic roles **App Creator** and,
as long as the data app is not created on behalf, **App Owner**.

应用程序开发者开发数据应用程序，用于在IDS连接器中使用。因此，应用程序开发者通常包括基本角色**应用程序创建者**，并且只要数据应用程序不是代表他人创建的，还包括**应用程序所有者**。

To be deployable, a data app has to be compliant with the system
architecture of the International Data Spaces (see [system layer](../3_5_System_Layer/3_5_0_System_Layer.md)). In
addition, data Apps can be certified by a Certification Body in order to
increase trust in these applications (especially with regard to Data
Apps processing sensitive information).

要能够部署，数据应用程序必须符合国际数据空间的系统架构（请参阅[系统层](../3_5_System_Layer/3_5_0_System_Layer.md)）。此外，数据应用程序可以通过认证机构进行认证，以增加对这些应用程序的信任（特别是涉及敏感信息处理的数据应用程序）。

Data apps are published and most likely provided in the App Store to
Data Customers, Data Suppliers, or Intermediaries. App Developers should
describe each Data App using metadata (in compliance with a metadata
model) with regard to its semantics, functionality, interfaces, etc.

数据应用程序会被发布，并且很可能在应用商店中提供给数据客户、数据供应商或中介机构。应用程序开发者应该描述每个数据应用程序，包括其语义、功能、接口等元数据（符合元数据模型）。

##### Connector Developer #####

A Connector Developer provides software for implementing the
functionality required by the International Data Spaces (i.e., through
software components, as described in the [system layer](../3_5_System_Layer/3_5_0_System_Layer.md)). Unlike Data Apps,
software is not provided by the App Store, but delivered over the
Connector Developer's usual distribution channels, and used on the basis
of individual agreements between the Connector Developer and the user
(e.g., a Data Customer, a Data Supplier, or an Intermediary). This
procedure implies that the agreements (e.g. licenses) for deployment and
software usage remain outside the scope of the International Data
Spaces.

连接器开发者提供软件以实现国际数据空间所需的功能（即通过软件组件，如[系统层](../3_5_System_Layer/3_5_0_System_Layer.md)中描述的）。与数据应用程序不同，软件不是通过应用商店提供的，而是通过连接器开发者的常规分发渠道提供，并且根据连接器开发者与用户（例如数据客户、数据供应商或中介机构）之间的个别协议使用。这个过程意味着部署和软件使用的协议（例如，许可证）不属于国际数据空间的范围。

The Connector Developer typically assumes the basic roles **Connector
Creator**, **Connector Owner**, and -- considering the way of software
distribution described above -- **Connector Provider**.

连接器开发者通常承担基本角色**连接器创建者**、**连接器所有者**，并考虑到上述软件分发方式，还有**连接器提供者**的角色。

#### CATEGORY 4: GOVERNANCE BODY #####

Governance Bodies in the IDS have the authority and task to set and
enforce guidelines to standardize data exchange, to create trust and, in
the end, to enable sustainable operation of the IDS. The Certification
Body, Evaluation Facilities, Standardization Organizations, and the
International Data Spaces Association are the business roles in the
category of Governance Bodies.

在国际数据空间中，治理机构拥有权威并有任务制定和执行指导方针，以标准化数据交换、建立信任，并最终实现IDS的可持续运营。认证机构、评估机构、标准化组织和国际数据空间协会是治理机构类别中的业务角色。

##### CERTIFICATION BODY AND EVALUATION FACILITIES #####

The participants in the International Data Spaces benefit from the
Certification Body and the Evaluation Facilities as these roles take
care of the certification process and issue certificates (both with
regard to organizations that want to participate and with regard to
software components that are to be used).

国际数据空间中的参与者从认证机构和评估机构中受益，因为这些角色负责认证过程并发放证书（包括想要参与的组织以及将要使用的软件组件）。

The Certification Body, together with selected Evaluation Facilities, is
in charge of the certification of the participants and the core
technical components in the International Data Spaces. These Governance
Bodies make sure that only compliant organizations are granted access to
the trusted business ecosystem. In this process, the Certification Body
supervises the actions and decisions of the Evaluation Facilities.

认证机构与选定的评估机构一起负责国际数据空间中参与者和核心技术组件的认证。这些治理机构确保只有符合条件的组织才能获得进入可信商业生态系统的权限。在此过程中，认证机构监督评估机构的行动和决策。

Thus, from the technical perspective, the basic roles **Connector
Certifier**, **App Certifier** and **Service Certifier**.

因此，从技术角度来看，基本角色包括**连接器认证者**、**应用程序认证者**和**服务认证者**。

The Certification Scheme applied in the process is described in the [Certification Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_Certification_Perspective.md).

##### Standardization Organization #####

Standardization Organizations govern standards that are typically
describe as an ontology or vocabulary. In general, there is neither a
claim for exclusiveness of a standard nor an obligation apply it. One
example could be the International Commercial Terms (Incoterms) that are
a common legal foundation in logistics, but does have to be applied. A
domain-specific Standardization Organization is, e.g., Odette, a
European organization setting data standards for the automotive
industry.

标准化组织管理通常被描述为本体论或词汇表的标准。通常情况下，没有对标准的排他性要求或应用标准的义务。例如，国际商务术语解释通则（Incoterms）是物流中的通用法律基础，但不必应用。一个领域特定的标准化组织是欧洲的Odette，该组织为汽车工业制定数据标准。

The business role Standardization Organization, therefore, comprises the
basic roles **Vocabulary Creator** and **Vocabulary Owner**.

Among the standardization organizations, the IDSA assumes a special
role, as it is exclusively entitled to govern the IDS Reference
Architecture Model and the Information Model.

##### INTERNATIONAL DATA SPACES ASSOCIATION (IDSA) #####

The International Data Spaces Association (IDSA) is a non-profit
organization promoting the continuous development of the International
Data Spaces. More specifically, it supports and governs the continuous
development of the Reference Architecture Model and the participant
certification process. The International Data Spaces Association is
currently organized across several working groups, each one addressing a
specific topic (e.g., architecture, use cases and requirements, or
certification). Members of the Association are primarily large
industrial enterprises, IT companies, SMEs, research institutions, and
industry associations.

As the International Data Spaces Association is not directly involved in
the data exchange activities of the International Data Spaces, its role
will not be further addressed in the sections on the other Layers.
