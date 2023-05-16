### SECURITY ASPECTS ADDRESSED BY THE DIFFERENT LAYERS OF THE IDS-RAM ###

Since security generally covers non-functional aspects, security and trust serve as an enabler for functionalities such as data exchange. This results in security being a cross-cutting concern for the layers discussed in the core chapters of the RAM.

确实，由于安全通常涵盖非功能性方面，因此安全和信任在使功能成为可能的方面起着推动作用，例如数据交换。这导致安全成为RAM核心章节中讨论的各层次中的横切关注点。

#### BUSINESS LAYER ####

Security delivers the means to establish trust in the ecosystem which is the basis for the sovereign data exchange and processing targeted. The roles that are established in [Section 3.1](../../3_Layers_of_the_Reference_Architecture_Model/3_1_Business_Layer/3-1-Business-layer.md) are either responsible for setting up this trustworthy ecosystem as described in the trust model in [Section 4.1.2](./4_1_2_Identity_and_Trust_Management.md) or for adding services in the IDS that support the establishment of data value chains.

安全提供了建立在其基础上的生态系统中的信任机制，这是目标主权数据交换和处理的基础。在[第3.1节](../../3_Layers_of_the_Reference_Architecture_Model/3_1_Business_Layer/3-1-Business-layer.md)中设立的角色，其中一个职责是在[第4.1.2节](./4_1_2_Identity_and_Trust_Management.md)中描述的信任模型中建立这种可信的生态系统，或者是在IDS中添加支持建立数据价值链的服务。

#### FUNCTIONAL LAYER ####

The IDS is intended as a trustworthy ecosystem for sovereign data exchange. This leads to various functional requirements regarding data exchange and data processing which are defined in [Section 3.2](../../3_Layers_of_the_Reference_Architecture_Model/3_2_Functional_Layer/3_2_FunctionalLayer.md). Security aspects and the trust model used in the IDS [Section 4.1.2](./4_1_2_Identity_and_Trust_Management.md) shape these requirements by enabling or restricting some transactions or operations in the International Data Spaces. Without security, many use cases would not be possible (e.g., offering sensitive data to trusted business partners). The concept of
data usage control described in [Section 4.1.6](./4_1_6_Usage_Control.md) allows Data Providers to attach data usage policy information to their data in order to define how a Data Consumer may use the data.

IDS旨在成为一个可信赖的生态系统，用于主权数据交换。这导致在[第3.2节](../../3_Layers_of_the_Reference_Architecture_Model/3_2_Functional_Layer/3_2_FunctionalLayer.md)中定义了与数据交换和数据处理有关的各种功能要求。IDS中使用的安全性方面和信任模型在[第4.1.2节](./4_1_2_Identity_and_Trust_Management.md)中对这些要求进行了塑造，通过启用或限制国际数据空间中的某些事务或操作来实现。如果没有安全性，许多用例将无法实现（例如向可信商业伙伴提供敏感数据）。在[第4.1.6节](./4_1_6_Usage_Control.md)中描述的数据使用控制的概念允许数据提供者将数据使用策略信息附加到其数据中，以定义数据消费者可以如何使用数据。

#### INFORMATION LAYER ####

The Information Layer ([Section 3.3](../../3_Layers_of_the_Reference_Architecture_Model/3_3_Information_Layer/3_3_InformationLayer.md)) provides the means for participants to use a common vocabulary and common semantics to express concepts and relationships between them. In doing so, it is possible to, e.g., describe a connector setup or specify access and usage control policies in a way that these are understood by all participants.

信息层（[第3.3节](../../3_Layers_of_the_Reference_Architecture_Model/3_3_Information_Layer/3_3_InformationLayer.md)）提供参与方使用共同的词汇和共同的语义来表达概念和它们之间的关系。这样做的话，就可以以一种所有参与者都能理解的方式描述连接器设置或指定访问和使用控制策略，举个例子。

#### PROCESS LAYER ####

To take security aspects into account on the Process Layer([Section 3.4](../../3_Layers_of_the_Reference_Architecture_Model/3_4_Process_Layer/3_4_Process_Layer.md)), it is important that existing processes reflect the defined Trust Model ([Section 4.1.2](./4_1_2_Identity_and_Trust_Management.md)) and are permanently monitored, validated, and redesigned, if need be. For example, to allow trustworthy identification and authentication of components using a public key infrastructure (PKI), the operator of this component must generate a key pair on the component, apply for a public key certificate from the Certificate Authority (CA) and provision this certificate onto the component. For dynamic attribute support, the provider of the Dynamic Attribute Provisioning Service (DAPS) needs to verify the attributes which it will confirm with the Dynamic Attribute Tokens (DATs). The same is true for trustworthy operations of an App Store, for which data must be verified and signed by a trusted entity before it can be uploaded.

为了考虑到流程层（[第3.4节](../../3_Layers_of_the_Reference_Architecture_Model/3_4_Process_Layer/3_4_Process_Layer.md)）中的安全方面，在现有流程中反映定义的信任模型（[第4.1.2节](./4_1_2_Identity_and_Trust_Management.md))并在需要时进行持续监控、验证和重新设计非常重要。例如，为了允许组件的可信身份验证和认证使用公共密钥基础结构（PKI），该组件的运营商必须在组件上生成一对密钥，向证书颁发机构（CA）申请公钥证书，并将该证书分配到组件上。对于动态属性支持，动态属性提供服务（DAPS）的提供者需要验证它将与动态属性令牌（DAT）确认的属性。对于应用商店的可信操作，也是如此，在将数据上传之前必须由可信实体验证和签名数据。

#### SYSTEM LAYER ####

The IDS components described in the System Layer ([Section 3.5](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_0_System_Layer.md)) form the IDS ecosystems. While the System Layer focuses on the general setup and functionality of these components, the security requirements and concepts for these components are mostly equivalent for the different components which are in essence either IDS connectors or specific types of connectors. The security perspective adds the overall view on the concepts used to ensure trust and security for all these components.

在系统层（[第3.5节](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_0_System_Layer.md)）中描述的IDS组件构成了IDS生态系统。虽然系统层关注这些组件的一般设置和功能，但是这些组件的安全要求和概念在本质上是等效的，因为它们基本上只能作为IDS连接器或特定类型的连接器。安全性方面的观点增加了对用于确保所有这些组件的信任和安全性的概念的整体视图。