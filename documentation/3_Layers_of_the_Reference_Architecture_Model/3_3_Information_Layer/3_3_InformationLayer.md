## Information Layer ##
信息层

The Information Layer specifies the Information Model, the
domain-agnostic, common language, i.e., Vocabulary of the International Data Spaces. The
Information Model is an essential agreement shared by the participants
and components of the IDS, facilitating compatibility and
interoperability. The primary purpose of this formal model is to enable
(semi-)automated exchange of digital resources within a trusted
ecosystem of distributed parties, while preserving data sovereignty of
Data Owners. The Information Model therefore supports the description,
publication and identification of data products and reusable data
processing software (both referred to hereinafter as Digital
Resources, or simply Resources). Once the relevant Resources
are identified, they can be exchanged and consumed via 
easily discoverable services. Apart from those core
commodities, the Information Model describes essential constituents of
the International Data Spaces, its participants, its infrastructure
components, and its processes.

信息层规定了信息模型，即国际数据空间的领域不可知、通用语言，也就是词汇表。信息模型是IDS参与者和组件之间分享的重要协议，有助于实现兼容性和互操作性。该正式模型的主要目的是在分布式各方的可信生态系统中，以保留数据所有者的数据主权的方式，实现（半）自动化数字资源交换。因此，信息模型支持数据产品和可重用数据处理软件（以下简称数字资源或资源）的描述、发布和标识。一旦确定了相关资源，它们就可以通过易于发现的服务进行交换和消费。除了这些核心资源外，信息模型还描述了国际数据空间的重要组成部分，包括参与者、基础设施组件和过程。

The Information Model is evolved and maintained by the IDSA Sub-Working
Group 4.[^1]

信息模型由 IDSA 子工作组进行了演进和维护。

### Scope ###

范围

The Information Model is a generic model, with no commitment to any
particular domain. Domain modeling is delegated to shared Vocabularies
and data schemata, as provided, e.g., by domain-specific communities of
the International Data Spaces. The Information Model does not provide a
meta-model for defining custom datatypes comparable to standards such as
OData[^2] or OPC-UA[^3]. Concerns beyond the scope of modeling Digital
Resources and their interchange are considered out of scope. The
Information Model therefore does not deal with the side effects of data
exchange (e.g., in scenarios in which data is used for time-critical
machine operations).

信息模型是一个通用模型，没有承诺任何特定的领域。领域建模委托给共享词汇表和数据模式，例如通过国际数据空间的特定领域社区提供的词汇表和数据模式。信息模型不提供与定义自定义数据类型相当的元模型，例如 OData [^ 2] 或 OPC-UA [^ 3] 这样的标准。超出对数字资源及其交换建模范围之外的问题不在其考虑范围内。因此，信息模型不涉及数据交换的副作用（例如，在数据用于时间关键的机器操作的情况下）。

### Model Representations ###

模型表示

The Information Model has been specified at three levels of
formalization. Each level corresponds to a digital representation,
ranging from this high-level, conceptual document down to the level of
operational code, as depicted in Figure
[3.3.1](#figure-331-representations-of-the-information-model_). Every
representation depicts the complete Information Model in its particular
way. Among the different representations, the Declarative Representation
(IDS Vocabulary) is the only normative specification of the Information
Model. As such, it is accompanied by a set of auxiliary resources (e.g.,
guidance documents, reference examples, validation tools, and editing
tools intended to support a competent, appropriate, and consistent usage
of the IDS Vocabulary).

信息模型已经在三个形式化级别上进行了详细说明。每个级别都对应着数字表示，从这份高级概念文档一直到运行代码的级别，如图[3.3.1]所示。每个表示都以其特定方式描述了完整的信息模型。在不同的表示中，声明性表示（IDS词汇表）是信息模型的唯一规范规定。因此，它配备了一组辅助资源（例如指导文件、参考示例、验证工具和编辑工具），旨在支持正确、适当和一致地使用IDS词汇表。

#### Conceptual Representation ####

概念上的标记

The Conceptual Representation of the Information Model presents a
high-level overview of the main, largely invariant concepts, with no
commitment to a particular technology or domain. It targets a general
audience, management boards, and media, as it provides basic information
and promotes a shared understanding of the concepts by means of a
textual document and a plausible visual notation. Where available,
references to related elements of the Declarative Representation and a
Programmatic Representation are provided, encouraging the reader to take
a look at these alternative implementations.

信息模型的概念表示呈现了主要、在很大程度上不变的概念的高级概述，没有承诺任何特定的技术或领域。它的目标是针对广泛的观众、管理层和媒体，因为它提供了基本信息，并通过文字文档和合理的可视化符号促进共同理解。在可以的情况下，提供了与声明性表示和程序表示相关元素的参考，鼓励读者查看这些替代实现。

#### Declarative Representation ####

声明表示

The Declarative Representation (IDS Vocabulary) provides a normative
view of the Information Model of the International Data Spaces.[^4] It
has been developed along the analysis, findings, and requirements of the
Conceptual Representation. Based on a stack of W3C Semantic Web
technology standards[^5] and standard modeling Vocabularies (the Data Catalog Vocabulary DCAT[^6],
the Open Digital Rights Language ODRL[^7], the Simple Knowledge Organization System SKOS[^8], etc.), it provides a formal, machine-interpretable
specification of concepts envisaged by the Conceptual Representation,
residing at the persistent namespace URI <https://w3id.org/idsa/core/> according to best practices for publishing linked data[^bp-ld].
Furthermore, it details and formally defines entities of the
International Data Spaces in order to be able to share, search for, and
reason upon the structured metadata describing these entities. The IDS Vocabulary is defined using RDF Schema[^rdfs] and the OWL Web Ontology Language[^owl]; additionally, descriptions of Digital Resources can be validated against SHACL shapes[^shacl] that express syntactic and semantic conditions. Queries against, e.g., Data Resources listed in the Data Catalogue of a Connector or Metadata Broker, or against Software Resources available from an App Store, can be formulated in query languages such as SPARQL[^sparql].  Thus, the
Declarative Representation comprises a complete referential model allowing the derivation of a
number of Programmatic Representations. The IDS Vocabulary is typically
used and instantiated by knowledge engineers, ontology experts, or
information architects. It defines a fairly minimal, domain-agnostic
core model and relies on third-party standard and custom
Vocabularies in order to express domain-specific facts. According to the
common practice, existing domain Vocabularies and standards are reused
where possible, fostering acceptance and interoperability.

声明性表示（IDS词汇表）提供了国际数据空间信息模型的规范视图。它是沿着概念表示的分析、发现和要求进行开发的。基于一组 W3C 语义网络技术标准和标准建模词汇表（数据目录词汇表 DCAT、开放数字权利语言 ODRL、简单知识组织系统 SKOS 等），它提供了概念表示所设想的概念的形式化、机器可解释的规范，并遵循了发布链接数据的最佳实践，在持久的命名空间URI <https://w3id.org/idsa/core/> 中。此外，它详细描述并形式定义国际数据空间的实体，以便能够共享、搜索和推理这些实体描述的结构化元数据。IDS词汇表使用RDF模式和OWL Web本体语言进行定义；此外，数字资源的描述可以根据表达语法和语义条件的SHACL形状进行验证。例如，可以使用SPARQL等查询语言在数据目录或元数据代理的数据资源列表中查询数据资源或在应用商店中可用的软件资源。因此，声明性表示包括一个完整的引用模型，允许推导出多种编程表示。IDS词汇表通常由知识工程师、本体学专家或信息架构师使用和实例化。它定义了一个相当最小化、与领域无关的核心模型，并依赖于第三方标准和自定义词汇表来表达领域特定的事实。根据共同实践，尽可能重用现有的领域词汇表和标准，促进接受和互操作性。

#### Programmatic Representation ####

可编程显示

The Programmatic Representation of the Information Model targets
Software Providers by supporting seamless integration of the Information
Model with a development infrastructure software developers are familiar
with. It comprises a programming language data model (e.g., Java,
Python, C++) shipped as a set of documented software libraries (e.g.,
JAR files).[^9] The Programmatic Representation provides a best-effort
mapping of the IDS Vocabulary onto native structures of a target
programming language. This approach supports type-safe development,
well-established unit testing, and quality assurance processes. It
allows developers to easily create instances of the Information Model
that are compliant with the IDS Vocabulary, relieving them from the
intricacies of ontology processing.

信息模型的程序表示针对软件提供商，支持将信息模型与开发基础设施软件无缝集成，开发人员熟悉的编程语言数据模型（例如Java、Python、C++）组成一套已记录文档的软件库（例如JAR文件）。程序表示提供了IDS词汇表与目标编程语言的本地结构之间的最佳努力映射。这种方法支持类型安全开发、成熟的单元测试和质量保证过程。它使开发人员能够轻松创建符合IDS词汇表的信息模型实例，使他们免受本体处理的复杂性的困扰。

![Representations of the Information Model](./media/image31.png)

##### Figure. 3.3.1: Representations of the Information Model

第3.3.1图: 信息模型的表示形式。

### Relation to Domain-specific Vocabularies ###

与特定领域词汇表的关系。

In specific IDS-based ecosystems, domain-specific adaptations – also known as Application Profiles – of the Information Model may be used to describe Resources, Participants, infrastructure and other constituents of an International Data Space.
The definition of such domain-specific Vocabularies should follow best practices established, e.g., by the DCAT Application Profile for data portals in Europe (DCAT-AP), which tailors the specification of DCAT “to the specific application needs of data portals in Europe while providing semantic interoperability with other applications on the basis of reuse of established Controlled Vocabularies […] and mappings to existing metadata Vocabularies”[^dcat-ap].

在特定的基于IDS的生态系统中，可以使用信息模型的特定领域适应（也称为应用程序配置文件）来描述国际数据空间的资源、参与者、基础设施和其他组成部分。定义这样的特定领域词汇表应遵循已建立的最佳实践，例如欧洲数据门户的DCAT应用程序配置文件(DCAT-AP)，该配置文件将DCAT的规范“根据数据门户在欧洲的具体应用需求进行了定制，同时基于已建立的控制词汇表的再利用和对现有元数据词汇表的映射 提供了与其他应用程序的语义互操作性”。

_Further_, independent domain-specific Vocabularies, which are not necessarily derived from the IDS Information Model, may be used to describe the Content of a Resource and the Concepts addressed by a Resource, as detailed in the respective sections below.

此外，也可以使用独立于IDS信息模型的特定领域词汇表来描述资源的内容和资源所涉及的概念，具体内容在下面的各自部分进行详细说明。

### Conceptual Representation of a Digital Resource in the IDS ###

ids中数字资源的概念表示

In the following, the pivotal concept of a Digital Resource is
introduced, segregated into modules in accordance with the
separation of concerns principle (SoC principle). To do so, a
set of six broad concerns (“concern hexagon”) is provided.

接下来，根据关注点分离原则（SoC原则），将数字资源的核心概念分为多个模块进行介绍。为此，提供了一组包含六个广泛关注点的“关注点六边形”（“concern hexagon”）。

#### Version Note ####

Since version 3.0 of the IDS-RAM, this section of the document has
been reduced to the same high level of abstraction as the other sections.
Full versioning
information is available from the repository that hosts the source code of the
normative Declarative Representation as well as documentation covering further details on the Conceptual Representation.[^10]
The remaining text has been edited to better present the Information Layer in the context of the other layers, and to provide up-to-date pointers to external standards reused.

自IDS-RAM的版本3.0起，该文档的此部分已被减少到与其他部分相同的高度抽象水平。全版本信息可从托管正式声明的表示形式和涵盖概念表示进一步详细信息的文档的存储库中获得。其余文本已进行编辑，以更好地展示信息层在其他层的上下文中，并提供指向重用外部标准的最新指针。

#### (Digital) Resource ####

数字资源

A (Digital) Resource in the context of the International Data Spaces is
a uniquely identifiable, valuable, digital (i.e., non-physical) commodity
that can be traded and exchanged between remote participants using the
IDS infrastructure. Following the web resource paradigm[^11], the
abstract content of a Resource may be provided in a variety of
representations. Examples of Resources include documents, time series of
sensor values, messages, image file archives, or media streams.
Resources are subject to forwarding, processing, and/or consumption,
with a particular demand for modeling related, complementary aspects
(i.e., content, provenance, provisioning etc.). These are analyzed and
specified here by applying the separation of concerns (SoC)
paradigm[^12].

在国际数据空间的上下文中，一个（数字）资源是一种有价值且可以在IDS基础设施上进行交易和交换的独特可识别的数字（即非物理）商品。遵循Web资源范例的方式[^11]，一个Resource的抽象内容可以用多种表现方式提供。Resource的示例包括文档、时间序列的传感器值、消息、图像文件存档或媒体流。资源可以被转发、处理和/或消耗，对于建模相关的互补方面（即内容、来源、提供等）有特定的需求。这些通过应用关注点分离（SoC）范例[^12]来进行分析和确定。

#### Separation of Concerns (SoC) ####

Following the separation of concerns design principle, only one
dimension of a subject matter is considered at a time, for the sake of
clarity and consistency. Similar to the principle a microscope works,
each concern follows a particular, analytical point of view, while other
concerns can temporarily be disregarded. This principle can be applied
to information modeling, aiming at a thorough understanding of the
domain and fostering modularity and re-usability of the resulting (sub-)models. Accordingly designed, these models may evolve independently of
each other and can be updated by different agents at different times. As
any modification of a single element of the overall model does not
require a change in other, logically unrelated parts, the development
and maintenance of models can be substantially simplified.

遵循关注点分离设计原则，必须逐一考虑一个主题的每个维度，以便保持清晰和一致性。类似于显微镜的原理，每个关注点都遵循特定的分析视角，而其他关注点可以暂时被忽略。这个原则可以应用于信息建模，旨在彻底了解领域，促进（子）模型的模块化和可重用性。设计得当的模型可以独立于彼此发展，并且可以由不同的代理在不同的时间更新。由于整体模型的任何单个元素的修改不需要改变其他逻辑无关的部分，因此模型的开发和维护可以大大简化。

![Outline of the Concern-Basic concern hexagon](./media/image32.png)

##### Figure 3.3.2: Outline of the Concern-Basic concern hexagon

图3.3.2：Concern-Basic关注点六边形的大纲概述

#### Concern Hexagon ####

To illustrate the main modeling [c]{.underline}oncerns of Digital
Resources in a way easy to memorize, the mnemonic hexagonal arrangement
of [c]{.underline}arbon atoms can be used (“C-Hexagon”), as shown in
Figure [3.3.2](#figure-332-outline-of-the-concern-basic-concern-hexagon_).

为了简单地说明数字资源的主要建模问题并易于记忆，可以使用类似碳原子的助记六边形排列方式（称为“C-Hexagon”），如图3.3.2所示。

As a Resource's content is its most essential aspect, *C*ontent is located at
the top of the hexagon. The *Content* concern deals with

由于Resource的内容是其最基本的方面，因此*Content*位于六边形的顶部。*Content*关注点处理以下内容：

1. the description of a Resource's abstract substance,
2. its serialization as a representation in a machine-interpretable format, making use of Vocabularies as appropriate, and 
3. the materializations of these representations at certain points in time as one or more instances (e.g., values or artifacts).

 
1. 资源抽象实体的描述；
2. 将其序列化为机器可解释的格式的表示形式，并根据需要使用词汇表；
3. 这些表示形式在某些时间点上的具体实例化（例如，值或实体）等。

Content is interpretable by references to a
shared, formally defined *C*oncept, which may cover the meaning, annotation and interpretation of entities by, e.g., 

*Content*可以通过引用共享的、形式定义的概念来进行解释，这些概念可以覆盖实体的含义、注释和解释，例如：

1. natural language keywords,
2. terms defined in curated sources such as Controlled Vocabularies, concept schemes, taxonomies, thesauri, etc., or
3. types defined in type systems or ontologies, i.e., Vocabularies.


1. 自然语言关键词；
2. 在受控词汇表、概念方案、分类法、词表等经过筛选的来源中定义的术语；或者
3. 在类型系统或本体论中定义的类型，即词汇表。（Vocabularies）

On the other hand, links to a particular
*C*ontext (in terms of, e.g.,

另一方面，链接到特定的*C*ontext（例如：）

* time,
* place, or
* real-world entities)
 

* 时间（time），
* 地点（place），或者
* 真实世界实体（real-world entities））

make the
Content potentially relevant for certain Data Consumers.

使*Content*对某些数据消费者可能相关。

Thus, the upper
part of the C-Hexagon deals with the “what” aspects, independently of
Data Exchange, Data Sharing or Data Utilization. The lower part relates
to the “how” aspects; i.e., how the content is exchanged
(*C*ommunication) and under which conditions (*C*ommodity).

因此，C-Hexagon的上半部分涉及“what”方面，与数据交换、数据分享或数据利用无关。下半部分涉及“how”方面；即内容如何交换（C*ommunication*），以及在哪些条件下进行交换（C*ommodity*）。

The *Communication* concern deals with means to communicate a Resource's Content in one of the Representations
available, e.g.,

*Communication*关注处理如何以可用的表示法之一来传输资源的内容，例如：

* by sending messages in some communication protocol
* to a resource or service endpoint or to an IDS Connector
* in order to perform an operation.


* 通过使用某些通信协议发送消息
* 发送到资源或服务端点，或者发送到IDS连接器
* 以执行操作。

The *Commodity* concern helps to address the value and utility of a Resource in terms of, e.g.,

Commodity关注于如何衡量资源的价值和效用，例如：

* its provenance,
* its quality, and
* the (usage) policies attached to it, e.g., the obligation to pay a certain price for its consumption.

Commodity关注于资源的来源、质量，以及与其相关的使用政策，例如消费该资源需要支付一定价格的义务。

The *C*ommunity of Trust concern refers to the distinctive feature of the
International Data Spaces being an ecosystem of certified participants
operating certified components, such as Connectors. Using such components, Participants exchange and share Digital Resources in a secure and trusted way in accordance
with contracts composed of usage policies, thus ensuring data sovereignty.

*Community of Trust*是国际数据空间(IDS)的独特特征，指的是由认证参与者操作认证组件（例如Connector）组成的生态系统。通过使用这些组件，参与者按照由使用政策组成的合同，以安全可信的方式交换和共享数字资源，从而确保数据的主权。

![Detailed Concern Hexagon](./media/image53.png)

##### Figure 3.3.3: Detailed Concern Hexagon

The level of detail differs across the individual concerns. The
selection of their constituting aspects may change in light of new
requirements and insights; Fig. [3.3.3](#figure-333-detailed-concern-hexagon_) suggests one such expansion of the C-Hexagon to one more level of detail.

不同关注点的详细级别不同。随着新的需求和见解的出现，它们的组成方面的选择可能会改变。图[3.3.3](#figure-333-detailed-concern-hexagon_)提出了一种对C-Hexagon的扩展，以更加详细地描述关注点。

Modeling concerns may inform, but do not
necessarily correspond to any physical organization of the model (e.g.,
modules or directories).

建模关注点可能提供信息，但不一定对应于模型的任何物理组织（例如，模块或目录）。

[^1]: IDSA members may find further information at
    [GitHub Repository](https://github.com/International-Data-Spaces-Association/InformationModel).

[^2]: https://www.odata.org/

[^3]: https://opcfoundation.org/

[^4]: https://github.com/International-Data-Spaces-Association/InformationModel

[^5]: https://www.w3.org/standards/semanticweb/

[^6]: Data Catalog Vocabulary (DCAT) - Version 2. W3C Recommendation 04 February 2020. https://www.w3.org/TR/vocab-dcat-2/

[^7]: ODRL Information Model 2.2. W3C Recommendation 15 February 2018. https://www.w3.org/TR/odrl-model/

[^8]: SKOS Simple Knowledge Organization System Reference. W3C Recommendation 18 August 2009. https://www.w3.org/TR/skos-reference/

[^rdfs]: RDF Schema 1.1. W3C Recommendation 25 February 2014. https://www.w3.org/TR/rdf-schema/

[^owl]: OWL 2 Web Ontology Language Document Overview (Second Edition). W3C Recommendation 11 December 2012. https://www.w3.org/TR/owl2-overview/

[^shacl]: Shapes Constraint Language (SHACL). W3C Recommendation 20 July 2017. https://www.w3.org/TR/shacl/

[^sparql]: SPARQL 1.1 Query Language. W3C Recommendation 21 March 2013. https://www.w3.org/TR/sparql11-query/

[^bp-ld]: Best Practices for Publishing Linked Data. W3C Working Group Note 09 January 2014. http://www.w3.org/TR/ld-bp/

[^9]: Known implementations are listed at https://github.com/International-Data-Spaces-Association/InformationModel/.

[^10]: In the repository referenced in section 3.4.2.2, see the
    top-level file *CHANGELOG.md*.

[^11]: R. Fielding. \"Architectural Styles and the Design of
    Network-based Software Architectures,\" 2000. PhD thesis. Table 5-1
    "REST Data Elements". Available: https://www.ics.uci.edu/fielding/pubs/dissertation/rest_arch_style.htm$ tab_5

[^12]: E. W. Dijkstra. \"On the role of scientific thought,\" EWD 447,
    2000. Available:
    http://www.cs.utexas.edu/users/EWD/ewd04xx/EWD447.PDF

[^dcat-ap]: DCAT Application Profile for data protals in Europe.
https://joinup.ec.europa.eu/collection/semantic-interoperability-community-semic/solution/dcat-application-profile-data-portals-europe
