### App Store and IDS Apps ####

An IDS App is an independent, functional, and re-usable software asset that is deployable, executable, and manageable on an IDS Connector.

IDS应用程序是一种独立的、功能性的和可重用的软件资产，可部署、执行和管理在IDS连接器上。

As described in [Section 3.5.2](./3_5_2_IDS_Connector.md#ids-connector) IDS Connectors can make use of IDS Apps for several purposes. Three types of IDS Apps can be distinguished, namely Data App, Adapter App, and Control App, each performing different tasks in the IDS ecosystem. Applications of all types can be downloaded and fully managed by the IDS Connector:

正如3.5.2节所述，IDS连接器可以利用IDS应用程序实现多种目的。可以区分出三种类型的IDS应用程序，即数据应用程序、适配器应用程序和控制应用程序，分别在IDS生态系统中执行不同的任务。所有类型的应用程序都可以通过下载并由IDS连接器进行完全管理：

* _Data App:_ Applications of type Data App are re-usable, interchangeable, and connector-independent and perform small processing tasks, e.g., transform, clean, or analyse data. In other words, applications of this type manipulate the available data in some way. To define a data flow, the inputs and outputs of the components involved (Data App and IDS Connector) as well as of the backend system must be joined. To summarize multiple processing steps on the same data, Data Apps can be chained on the same data route.
* _Adapter App:_ Applications of type Adapter App are re-usable, interchangeable, and connector-independent and provide access to enterprise information systems, making them available to the underlying Connector. As the Data App type, the data flow of Adapter Apps is defined by joining matching inputs and outputs of the involved components (Adapter App, IDS Connector, and data sink/source or external service). Accordingly, Adapter Apps are used especially when the routing framework is not inherently capable of supporting the endpoints or protocols provided by external services.
* _Control App:_ Applications of type Control App allow to control the Connector from external systems and are used to connect backend systems, which may consist of a single or a cluster of applications and services, to an IDS ecoystem. Therefore, in contrast to the types introduced before, the Control App works on the administrative control flow and is connector-specific as it requires programming against the respective API of a Connector in a specific version for its implementation.


* 数据应用程序：数据应用程序是可重用、可交换和独立于连接器的应用程序类型，执行小型处理任务，例如转换、清理或分析数据。换句话说，此类应用程序以某种方式操作可用数据。为了定义数据流，必须将涉及的组件（数据应用程序和IDS连接器）以及后端系统的输入和输出连接在一起。为了汇总对同一数据的多个处理步骤，可以在同一数据路由上链接数据应用程序。
* 适配器应用程序：适配器应用程序是可重用、可交换和独立于连接器的应用程序类型，提供对企业信息系统的访问，使它们可用于底层连接器。与数据应用程序类型一样，适配器应用程序的数据流由涉及的组件的匹配输入和输出连接来定义（适配器应用程序、IDS连接器和数据汇/源或外部服务）。因此，适配器应用程序尤其在路由框架本身无法支持外部服务提供的端点或协议时使用。
* 控制应用程序：控制应用程序类型的应用程序允许从外部系统控制连接器，并用于连接后端系统（可能由单个或一组应用程序和服务组成）到IDS生态系统。因此，与之前介绍的类型相比，控制应用程序工作在管理控制流上，并且是特定于连接器的，因为它要求针对特定版本的连接器的相应API进行编程以实现其实现。

Furthermore, the different IDS App types can be bundled, which allows building a data processing chain with several apps from all types chained together.

此外，不同的IDS应用程序类型可以被捆绑在一起，从而可以构建一个数据处理链，其中多个来自各种类型的应用程序被链接在一起。

To integrate IDS Apps in an IDS ecosystem or to join them with other components as described above, an IDS App can be equipped with various endpoints. The endpoints for exchanging data between apps and between apps and connectors are mainly divided into those that consume data and those that provide data. A distinction is also made between endpoints that communicate exclusively internally and those that communicate with external components:

* _INPUT:_ The input endpoint is considered mandatory for all IDS App types that work with data or data streams. The data input endpoint describes an interface through which data can be transported to an app within the connector's environment.
* _INPUT EXTERNAL:_ The input external endpoint serves as an interface to connect to external data sources or data streams outside the actual connector environment. This endpoint is particularly relevant for IDS Apps of type Adapter App.
* _OUTPUT:_ The output endpoint is also considered mandatory for IDS App types that transmit data or data streams to other apps or connectors. The output endpoint describes an interface through which data can be consumed within the connector environment by apps or the connector itself.
* _OUTPUT EXTERNAL:_ At this endpoint, communication is established beyond the boundaries of the Connector. This special form of output endpoint is primarily relevant for Adapter Apps that establish a connection to an external data source. Reading data from external data sources is made possible by this endpoint. 

Further endpoints, besides the ones listed above, are the config endpoint and the status endpoint. The config endpoint can be used to actively set or change configuration parameters during the runtime of an IDS App. Optional is the so-called status endpoint, which can be used to retrieve status information from an IDS App during runtime.

The IDS App Store is a secure platform for distributing IDS Apps. An IDS App Store consists of a registry for available IDS Apps in this App Store. It also features the capabilty to search for IDS Apps using different search options (e.g. by functional or non-functional properties, pricing model, certification status, community ratings, etc.). Therefore, an App Store must support operations for App registration, publication, maintenance, and query, as well as operations for the provisioning of an App to a connector to App Users as depicted in Figure [3.5.3.1](#figure-3531-app-store-architecture). These basic operations can be optionally complemented by additional services, e.g. billing or support activities. The processes of publishing, finding and using IDS Apps are documented in detail in Section [3.4.5](../3_4_Process_Layer/3_4_5_Publishing_and_using_Data_Apps.md#publishing-and-using-ids-apps).

![AppStoreArchitecture](./media/app-store-architecture.png)
##### Figure 3.5.3.1: App Store Architecture

An IDS App Store also consists of an IDS Connector in order to communicate with the Connectors of App Providers and App Users within the Data Space. As a consequence, each instance of an App Store must be compliant to the Connector Certification criteria an provide the functionalities and endpoints of general Connectors together with the above-mentioned operations (e.g. provide a Self-Description, have a valid IDS Identity and use a valid DAT in its communication).