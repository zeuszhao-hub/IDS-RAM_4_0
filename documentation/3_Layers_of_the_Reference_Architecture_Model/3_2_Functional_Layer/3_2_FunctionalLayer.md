## Functional Layer ##

The Functional Layer defines -- irrespective of existing technologies
and applications -- the functional requirements of the International
Data Spaces, and the features to be implemented resulting thereof.

功能层定义国际数据空间的功能要求和需要实现的功能特性，而不考虑现有的技术和应用程序。

![ Functional architecture of the International Data
Spaces](./media/image21.png)
##### Figure 3.2: Functional architecture of the International Data Spaces

图3.2：国际数据空间的功能架构

The figure above
shows the functional architecture of the International Data Spaces,
subdividing the requirements into six groups of software functionality
to be provided by the IDS. These six groups comply with the strategic
requirements outlined in Section
[Goals of the International Data Spaces](../../1_Introduction/1_1_Goals_of_the_International_Data_Spaces.md).

上图展示了国际数据空间的功能架构，将要求细分为六个软件功能组，这些组由IDS提供。这六个功能组符合第[Hierarchical Structure Perspective](Hierarchical Structure Perspective)中概述的战略要求。

The following subsections give a brief summary of these functional
requirements.

以下各小节给出这些功能要求的简要概述。

### Trust ##

可信

Although requirements related to trust are usually non-functional, they
are addressed by the Functional Layer, since they represent fundamental
features of the International Data Spaces. The Trust group
comprises three main aspects (roles, identity management, and user
certification), which are complemented by governance aspects (see
Section on [Data Governance](../../4_Perspectives_of_the_Reference_Architecture_Model/4_3_Governance_Perspective/4_3_1_Layers.md).

尽管与信任相关的要求通常是非功能性的，但它们由功能层来处理，因为它们代表了国际数据空间的基本特征。信任组包括三个主要方面（角色、身份管理和用户认证），这些方面还有治理方面的补充（请参见[数据治理]一节）。

#### Roles ###

角色

Each role in the International Data Spaces has certain rights and
duties. For example, the Identity Provider is responsible for offering
services to create, maintain, manage, monitor, and validate identity
information of and for participants in the International Data Spaces.
More information about the roles is given in the [Business Layer](../3_1_Business_Layer/3_1_1_Roles_in_the_IDS.md).

国际数据空间中的每个角色都有一定的权利和责任。例如，身份提供者负责提供服务来创建、维护、管理、监控和验证国际数据空间参与者的身份信息。有关这些角色的更多信息可以在[业务层]中找到。

#### Identity Management ###

身份认证

Every Connector participating in the International Data Spaces must have
a unique identifier and a valid certificate. In addition, each Connector
must be able to verify the identity of other Connectors (with special
conditions being applied here; e.g., security profiles).

参与国际数据空间的每个连接器都必须具有唯一的标识符和有效的证书。此外，每个连接器必须能够验证其他连接器的身份（这里应用了特殊条件；例如，安全配置文件）。

#### User Certification ####

用户认证

Each participant in the International Data Spaces must undergo
certification in order to establish trust among all participants. More
information about the certification process is given in the [Certification Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_Certification_Perspective.md).

为了在所有参与者之间建立信任，国际数据空间中的每个参与者都必须进行认证。有关认证过程的更多信息可以在[认证视角]中找到。

### Security and Data Sovereignty ###

安全和数据主权

Like requirements related to trust, requirements related to security and
data sovereignty are also usually non-functional, but are still
addressed by the Functional Layer, since they represent fundamental
features of the International Data Spaces. The Security and data
sovereignty group contains four major aspects: authentication
authorization; usage policies  usage enforcement; trustworthy
communication  security by design; and technical certification.

与信任相关的要求一样，与安全和数据主权相关的要求通常也是非功能性的，但仍由功能层处理，因为它们代表国际数据空间的基本特征。安全和数据主权组包括四个主要方面：身份验证授权；使用政策和使用执行；值得信赖的通信和安全设计；以及技术认证。

#### Authentication & Authorization ####

身份认证与授权

Each Connector must have a valid X.509 certificate (or equivalent). With the help of
this certificate, each participant in the International Data Spaces that
operates an endpoint is able to verify the identity of any other
participant. Certain conditions (e.g. security profiles) may also apply
here. More information about authentication is given in the [Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

每个连接器都必须拥有有效的X.509证书（或等效证书）。借助此证书，国际数据空间中运行端点的每个参与者都能够验证任何其他参与者的身份。某些条件（例如安全配置文件）也可能适用于此处。有关身份验证的更多信息可以在[安全视角]中找到。

The Connector serving as the data source must be able to verify the
receiving Connector's capabilities and security features as well as its
identity. More information about authorization is given in the [Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

作为数据源的连接器必须能够验证接收连接器的功能和安全特性以及其身份。有关授权的更多信息可以在[安全视角]中找到。

#### Usage Policies & Usage Enforcement ####

使用政策和使用执行

In the IDS, Data Owners and Data Providers can always be sure their data
is handled by a Data Consumer according to the usage policies specified.
Each participant can define usage policies and attach them to outbound
data. Policies might include restrictions, such as disallowing
persistence of data, or disallowing transfer of data to other parties,
for example. More information about usage policies and usage enforcement
is given in the [Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

在IDS中，数据所有者和数据提供者始终可以确信他们的数据按照指定的使用政策由数据使用方处理。每个参与者都可以定义使用政策并将其附加到出站数据上。这些策略可能包括限制，例如禁止持久化数据或禁止将数据传输给其他方。有关使用政策和使用执行的更多信息可以在[安全视角]中找到。

#### Trustworthy Communication & Security by Design ####

可靠的通讯和安全设计

Connectors, App Stores, and any Metadata Broker can check if the Connector of the
connecting party is running a trusted (i.e. certified) software stack.
Any communication between (external) Connectors can be encrypted and
integrity protected. Each Data Owner and Data Provider must be able to
ensure that their data is handled by the Connector of the Data Consumer
according to the usage policies specified: otherwise the data will not
be sent. To reduce the impact of compromised applications, appropriate
technical measures must be applied (e.g. isolating Data Apps from each
other and from the Connector). Data Providers and Data Consumers can
decide about the level of security to be applied for their respective
Connectors by deploying Connectors supporting the selected security
profile. More information about trustworthy communication and security
by design is given in the [Security Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_Security_Perspective.md).

连接器、应用商店和任何元数据经纪人都可以检查连接方的连接器是否运行了可信的（即经过认证的）软件堆栈。任何（外部）连接器之间的通信都可以进行加密和完整性保护。每个数据所有者和数据提供者必须能够确保其数据按照指定的使用政策由数据使用者的连接器进行处理，否则数据将不会被发送。为减少受损应用程序的影响，必须采取适当的技术措施（例如将数据应用程序相互隔离和与连接器隔离）。数据提供者和数据消费者可以通过部署支持所选安全配置文件的连接器来决定为其各自的连接器应用的安全级别。有关可信通信和安全设计的更多信息可以在[安全视角]中找到。

#### Technical Certification ####

The core components of the International Data Spaces, and especially the
Connectors, require certification from the Certification Body in order
to establish trust among all participants. More information about
technical certification is given in the [Certification Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_2_Certification_Perspective/4_2_Certification_Perspective.md).

### Ecosystem of Data ###

Being able to describe, find and correctly interpret data is another key
aspect of the International Data Spaces. Therefore, every data source in
the International Data Spaces is described on the Information Layer (see
[section 3.3](../3_3_Information_Layer/3_3_InformationLayer.md)).

The Ecosystem of Data group comprises three major aspects: data
source description, metadata brokering, and vocabularies.

#### Data Source Description ####

Participants must have the opportunity to describe, publish, maintain
and manage different versions of metadata. Metadata should describe the
syntax and serialization as well as the semantics of data sources.
Furthermore, metadata should describe the application domain of the data
source. The operator of a Connector must be able to define the price,
the pricing model, and the usage policies regarding certain data. More
information about data source description is given in the
[Information Layer](../3_3_Information_Layer/3_3_InformationLayer.md).

#### Metadata Brokering ####

The operator of a Connector must be able to provide an interface for
data and metadata access. Each Connector must be able to transmit
metadata of its data sources to one or more Metadata Brokers. Each participant
must be able to browse and search metadata in the metadata repository,
provided the participant has the right to access the metadata.
Furthermore, each participant must be able to browse the list of
participants registered at a Metadata Broker. More information about metadata brokering is
given in the [Process Layer](../3_4_Process_Layer/3_4_Process_Layer.md).

#### Vocabularies ####

To create and structure metadata, the data provider can use vocabularies to define the semantics of the various elements in the data assets.
The vocabulary in turn can be stored in a Vocabulary Hub that is accessible to all users of a data space in an agreed format.
With vocabularies the data consumer has possibility to easily understand of the semantics of the various data elements in an offered data asset and verify the data asset afterwards.
This universal location (Vocabulary Hub) is an IDS component (centralized server or decentralized network), that stores vocabularies and enables collaboration between participants to harmonise single vocabularies and create common set of harmonised vocabulary standards for the given data space.
A set of functional requirements for this component is defined further:

* The technical interface between the Vocabulary Hub and the data space infrastructure shall be based on the IDS Connector.
* The Vocabulary Hub shall have a browser-based user interface and API, which allows to visualize and to browsed vocabularies in a human user-friendly way.
* The Vocabulary Hub shall provide creating, selection, editing (inserting, updating, changing, deleting, matching, version management), read- and search functionalities and support queries with appropriate means, e.g. SPARQL.
* Vocabularies expressed in RDF shall by syntactically compatible with OWL in order to enable processing with more expressive semantics
* User management is required for vocabulary hubs to avoid abuse by editing.
* Language can be specified for a vocabulary, and multi-lingual specification of classes is possible. Language becomes part of the metadata and can be used as a filter.
* The Vocabulary Hub can provide an API that returns ontology mappings for a given ontology. Mappings can be used for connectors to automatically convert domain specific data into data standard formats.
* The Vocabulary Hub can enable collaborative development of domain specific standard and support for mapping differing positions into a new meta concept as common standard.

### Standardized Interoperability ###

Standardized data exchange between participants is the fundamental
aspect of the International Data Spaces. The IDS Connector is the main
technical component for this purpose.

#### Operation ####

Participants should be able to run the Connector software in their own
IT environment. Alternatively, they can run a Connector on mobile or
embedded devices. The operator of the Connector must be able to define
the data workflow inside the Connector. Users of the Connector must be
identifiable and manageable. Passwords and key storage must be
protected. Every action, data access, data transmission, incident, etc.
should be logged. Using this logging data, it should be possible to draw
up statistical evaluations on data usage etc. Notifications about
incidents should be sent automatically.

#### Data Exchange ####

The Connector must receive data from an enterprise backend system,
either through a push-mechanism or a pull-mechanism. The data can be
provided via an interface or pushed directly to other participants. To
do so, each Connector must be uniquely identifiable. Other Connectors
can subscribe to data sources or pull data from these sources. Data can
be written into the backend system of other participants.

### Value Adding Apps ###

Before or after the actual data exchange, data may need to be processed
or transformed. For this purpose, the International Data Spaces offers
Data Apps. Each Data App has a lifecycle, spanning its implementation,
provision in the App Store, installation, and support. The App Store
should therefore be clearly visible and recognizable to every
participant.

#### Data Processing and Transformation ####

A data processing app (which is a subtype of a Data App) should provide
a single, clearly defined processing function to be applied on input
data for producing an expected output. A data transformation app (also a
subtype of a Data App) should be able to transform data from an input
format into a different output format in order to comply with the
requirements of the Data Consumer (without any substantial change made
to the information contained in the data; i.e., loss-less
transformation).

#### Data App Implementation ####

The developers of Data Apps should be able to annotate the software with
metadata (about functions and interfaces, pricing models, licenses,
etc.). Data Apps must explicitly define their interfaces, dependencies,
and access requirements.

#### Providing Data Apps ####

Any authorized Data App developer can initiate a software provision
process (App Store publication). Prior to publication in the App Store,
Data Apps must pass an optional evaluation and certification process
controlled by the Certification Body. The App Store should support
authorized users in their search for a suitable application in an
adequate fashion. Access of privileged users (e.g., administrators or
operators) should require strong authentication (e.g., 2-factor
authentication).

#### Installing and Supporting Data Apps ####

A dedicated Connector service should support authorized users in
(un-)installing Data Apps not originating from an official App Store. In
addition, it should support authorized users in searching, installing,
and managing (e.g., removal or automated updates) Data Apps retrieved
from an App Store.

### Data Markets ###

Data to be exchanged in the International Data Spaces may have monetary
value. Therefore, the International Data Spaces has to integrate data
market concepts, like clearing and billing, but also governance.

#### Clearing & Billing ####

The Data Owner can define the pricing model (e.g. pay per transfer, pay
per access, pay per day/month/year), and the price of data. Any
transaction of any participant can be logged. The clearing and billing
process must be simple and standardized.

#### Usage restrictions and governance ####
 
Governance in the International Data Spaces comprises five aspects: data
as an economic good, data ownership, data sovereignty, data quality, and
data provenance. More information about governance is given in [Governance Perspective](../../4_Perspectives_of_the_Reference_Architecture_Model/4_3_Governance_Perspective/4_3_Governance_Perspective.md).

#### Legal aspects ####

Trading data on a data marketplace requires legal contracts and
conditions that can be negotiated in an automated way. Therefore,
standard contracts for typical data exchange transactions are necessary.
