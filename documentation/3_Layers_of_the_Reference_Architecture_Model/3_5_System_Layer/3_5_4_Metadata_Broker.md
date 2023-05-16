### Metadata Broker ###

The IDS Metadata Broker is an IDS Connector (see Section [3.5.2](./3_5_2_IDS_Connector.md#ids-connector)), which contains an endpoint for the registration, publication, maintenance, and query of Self-Descriptions. 

IDS Metadata Broker是一个IDS连接器（参见第3.5.2节），其中包含用于注册、发布、维护和查询自描述的端点。

A Self-Description encapsulates information about IDS Connector itself and its capabilities and characteristics. This Self-Description contains information about the offered interfaces, the owner of the component and the metadata of the data offered by the component. A Self-Description is provided by the operator of the Connector. The Self-Description in total can be seen as metadata.

自描述性信息封装了关于IDS连接器本身及其能力和特征的信息。这个自描述包含了关于提供的接口、组件的所有者以及组件所提供的数据的元数据信息。自描述由连接器的操作者提供。整个自描述可以看作是元数据。

An IDS Connector providing a service or data can send its Self-Description to a IDS Metadata Broker so that every participant is able to find it within the dataspace. The IDS Metadata Broker can be understood as a phone book. Within a dataspace, there can be multiple IDS Metadata Brokers allowing to distribute the IDS Metadata Broker functionality. It is up to the dataspace authority to decide if there is a leading IDS Metadata Broker or if the different instances operate independently.

提供服务或数据的IDS连接器可以将其自描述发送到IDS元数据代理，以便每个参与者都能够在数据空间内找到它。IDS元数据代理可以被理解为电话簿。在数据空间中，可以有多个IDS元数据代理，以便分发IDS元数据代理功能。数据空间的权威可以决定是否需要一个领先的IDS元数据代理，或者不同的实例是否都可以独立运作。

A participant can interact with an IDS Metadata Broker by using the processes defined on the Process Layer, the descriptions defined on the Information Layer, and descriptions defined on the System Layer. The Information Layer describes the message types for registration and query as well as their content. An IDS Metadata Broker may provide additional services that in term must be described by using terms from the IDS Information Model in the respective Metadata Broker's Self-Description document.

参与者可以使用在过程层中定义的过程、在信息层中定义的描述以及在系统层中定义的描述与IDS元数据代理进行交互。信息层描述了注册和查询的消息类型及其内容。IDS元数据代理可能提供附加服务，这些服务必须使用IDS信息模型中的术语在相应的元数据代理的自描述性文件中进行描述。

**Note:  Even though the name might indicate a different purpose, an IDS Metadata Broker is *not* a message broker or provides any similar functions to distribute data assets actively by itself.**

注意：即使名称可能表明不同的目的，IDS元数据代理也不是消息代理或提供任何类似的功能来主动分发数据资产。

As a direct consequence of the IDS Connector-nature of the Metadata Broker, each instance must be compliant to the Connector Certification criteria and in particular provide the functionalities and endpoints of general Connectors. For instance, a Metadata Broker must provide a Self-Description that provides further information about itself for other IDS components. A Metadata Broker must also have a valid IDS Identity and use a valid DAT in its communication.

由于IDS元数据代理的IDS连接器性质，每个实例必须符合连接器认证标准，特别是提供通用连接器的功能和端点。例如，元数据代理必须提供一个自描述文件，为其他IDS组件提供有关自身的更多信息。元数据代理还必须具有有效的IDS身份，并在其通信中使用有效的DAT。

In addition to these requirements for each IDS Connector, the Metadata Broker provides further functionalities for a data space. Its main purpose is the persistence and storing of Self-Description documents and offering efficient access and search functions on their content. It therefore requires a reliable and scalable internal database. As the Self-Description documents are encoded in RDF, usually JSON-LD, a graph-oriented database like a triple store or a property graph database might be used. Nevertheless also traditional SQL or NoSQL databases may be applied, which may not have the same native query support but still can be sufficient. In any case, the internal architecture of a Metadata Broker must be flexible enough to cope with extensions of the data scheme. The IDS Information Model can always be enriched with further attributes, so a Metadata Broker must also allow the persistence and querying of information which was not yet known at its deployment time. Furthermore, Metadata Brokers operated for certain domains or dedicated data spaces might also enforce the existence of attributes that are not covered by the core IDS Information Model or part of the IDS namespace. That implies that a certain Metadata Broker instance requires Self-Descriptions containing information content that uses extensions of the IDS Information Model. In such cases, the additional requirements are outlined in the Metadata Broker Self-Description as well as in the content of the return messages, in case a Connector has not set such attributes yet.

除了每个IDS连接器的这些要求之外，元数据代理还提供了数据空间的进一步功能。它的主要目的是持久化和存储自描述文档，并在其内容上提供高效的访问和搜索功能。因此，它需要一个可靠和可扩展的内部数据库。由于自描述性文件编码为RDF，通常采用JSON-LD格式，因此可能使用面向图的数据库，如三元组存储或属性图数据库。尽管如此，也可以应用传统的SQL或NoSQL数据库，这些数据库可能没有相同的本机查询支持，但仍然可能足够。在任何情况下，元数据代理的内部架构必须足够灵活，以处理数据模式的扩展。IDS信息模型可以随时使用更多属性进行丰富，因此元数据代理还必须允许持久化和查询在部署时尚不知道的信息。此外，为某些领域或专用数据空间运行的元数据代理可能还要执行不受核心IDS信息模型或IDS命名空间覆盖的属性的存在。这意味着特定的元数据代理实例需要包含使用IDS信息模型扩展的信息内容的自描述内容。在这种情况下，附加要求也在元数据代理自描述中和返回消息的内容中进行了概述，以防连接器尚未设置这些属性。

Furthermore, a Metadata Broker implementation might add indexing or caching modules to reduce the query evaluation time. It can be generally expected that the amount of READ requests is significantly higher than the overall number of remote WRITE activities so a READ-optimized architecture can lead to better user experiences. Such design decisions however are in the responsibility of the operator.

此外，元数据代理实现可能添加索引或缓存模块以减少查询评估时间。通常可以预期，读取请求的数量显着高于远程写入活动的总数，因此具有读取优化的体系结构可以导致更好的用户体验。然而，这样的设计决策在运营商的责任范围内。

Additionally, most use cases for Metadata Brokers require a human-oriented interface to the Self-Descriptions. A website with fulltext and facet search capabilities is therefore usually provided. The website might further provide the creation and management of the locally stored Self-Descriptions. However, as the registration and updating process at the Metadata Broker is centered around Connectors, the authority of the human website user and the asset-hosting Connector must be ensured.

此外，大多数元数据代理用例需要面向人类的接口来访问自描述性文件。因此，通常提供具有全文和分面搜索功能的网站。该网站可能进一步提供本地存储的自描述文件的创建和管理。然而，由于在元数据代理的注册和更新过程中集中了连接器，因此必须确保人类网站用户的权限和资产托管连接器的权威性。

####  Endpoints ####

Metadata Brokers must provide remote endpoints to their own Self-Description (read-only) as well as to the locally persisted Self-Description graph (read/write for the hosting Connectors, read-only for the others). The server hosting these endpoints translates incoming requests, performs the necessary IDS identity and validity checks, and translates them into operations to the database.

A Metadata Broker might support endpoints for different IDS protocol bindings. In any case, the content of the responses are protocol-independent. That means a successful read operation using one binding must also be successful through any other if targeting the same Self-Description. A Metadata Broker may however discriminate based on the identity of the requester, providing responses to one Connector while rejecting another due to IDS Usage Control configurations.

#### Search and Querying ####

The main purpose of a Metadata Broker is the provisioning of remote search functionalities. This can be done in a resource-oriented manner if the identifiers of the targeted Self-Descriptions are already known in advance. Alternatively, full-text or complex queries might be used. A complex query in this sense is any query that combines filters, aggregations or traverses the Self-Description graph to search for information. Which query language is supported by which Metadata Broker instance is outlined in its own Self-Description.

The IDS Information Model provides the scheme for the searches. The knowledge of the Information Model can be used by querying Connectors to formulate their inquiries. Metadata Brokers may also provide additional templates or preformulated queries to support the Connectors.

#### Self-Description Life Cycle ####

Self-Descriptions go through a life cycle. Created Self-Descriptions are in the `active` state as long as they are not put to `unavailable` by its sovereign. It's important to note that the later state is different to a deletion. It is important to track the usage of Self-Descriptions, in particular their unique identifier, to avoid name clashes or false flag attacks. A Connector therefore can ask to not publicly provide a Self-Description anymore by setting it to `unavailable` but it cannot force the Metadata Broker or any other Connector to completely delete the information from its internal databases.

A Self-Description can be made `active` at any time again by the respective Connector. In addition, it can overwrite already active Self-Descriptions with a new one. The update of a previously `unavailable` Self-Description however will set it back to `active` automatically. Furthermore, new Self-Descriptions must not use the identifier of already existing ones.

#### Data Synchronization ####

The Metadata Broker is an optional component in a data space. That of course means that there can be data spaces that completely operate without any Metadata Broker. There can be however also data spaces where several Metadata Broker instances are provided. In such use cases, the synchronization between these instances becomes a topic, in particular to avoid redundant or conflicting information.

At the current state, the IDS does not specify or recommend any technical synchronization mechanism or process. Data space operators may implement such processes, via peer-to-peer architectures, declaring a leading instance, or relying on Distributed Ledger approaches. As a consequence, a Connector communicating with several Metadata Brokers at the same time must not - without having additional information - assume that the Self-Descriptions of the various Metadata Brokers are aligned.
