### Identity and Trust Management ###

The International Data Spaces allow participants a cross-company data exchange. In many cases, the participants intending to exchange data have no prior knowledge about the other company and its utilized components to properly assess the consequences of such a data exchange. Thus, the IDS offers mechanisms to gain reliable information which help to establish trust and enable participants to make sovereign and informed decisions.
Identity and trust management is rooted in the components described in ([Section 3.5.1](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_1_Identity_Provider.md#identity-provider)).

国际数据空间允许参与者进行跨公司数据交换。在许多情况下，意图交换数据的参与者没有关于其他公司及其所使用的组件的先前知识，以便正确评估此类数据交换的后果。因此，IDS提供了机制来获取可靠的信息，以帮助建立信任并使参与者做出独立和知情的决策。身份和信任管理源于[第3.5.1节](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_1_Identity_Provider.md#identity-provider)中描述的组件。

#### Identities for Devices ####

The IDS Connector is the central device to establish trust on a technical level and to ensure a secure data exchange across domain boundaries.
In the IDS, each connector instance possesses it's own identity. Each connector instance is made up of several aspects:

IDS连接器是在技术层面建立信任和确保跨域边界进行安全数据交换的核心设备。在IDS中，每个连接器实例都拥有自己的身份。每个连接器实例由多个方面组成：

* The platform the IDS Connector instance depends on. A platform consists of hardware, firmware, operating system and (container) run-time environment.
* The Connector Core Services software artifacts that provide management functionality and IDS interoperability.
* The configuration of an IDS Connector (defined data routes, configured Usage Control framework).
* The IDS Apps or other services (e.g., Clearing House services) that are bound to this connector instance.
[Section 3.5.2](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_2_IDS_Connector.md#ids-connector) provides more details for the different parts of a connector.


* IDS Connector实例所依赖的平台，包括硬件、固件、操作系统和（容器）运行时环境。
* 提供管理功能和IDS互操作性的连接器核心服务软件构件。
* IDS连接器的配置（定义的数据路由、配置的使用控制框架）。
* 绑定到此连接器实例的IDS应用程序或其他服务（例如清算所服务）。

[第3.5.2节](../../3_Layers_of_the_Reference_Architecture_Model/3_5_System_Layer/3_5_2_IDS_Connector.md#ids-connector)提供了有关连接器不同部分的更多详细信息。

The IDS Certification is explained in [Section 4.2](../4_2_Certification_Perspective/4_2_Certification_Perspective.md#certification-perspective). It is always conducted for a blueprint of the entire stack consisting of platform and Connector Core Services. Each such certified blueprint can be instantiated multiple times.

IDS认证在[第4.2节](../4_2_Certification_Perspective/4_2_Certification_Perspective.md#certification-perspective)中进行解释。它始终针对由平台和连接器核心服务组成的整个堆栈的蓝图进行。每个这样经过认证的蓝图都可以实例化多次。

The IDS Connector identity serves to uniquely identify one such instance of the Connector Core Services with their IDS Apps on qualified platforms. The identity concept is equally used for other technical components such as Broker Services, DAPS, ... in the IDS which have their own Core Services (represented by one or multiple containers) running on a comparable platform.

IDS Connector的身份用于唯一标识具有其IDS应用程序的Connector Core Services的一个实例，并在合格平台上运行。身份概念同样用于IDS中的其他技术组件，例如Broker服务、DAPS等，在此类组件中，它们有自己的Core Services（由一个或多个容器表示）在可比平台上运行。

One component always is characterized by the combination of platform and service instances. As an example, this Connector instance is running several data apps. The identity is comprised of the platform, the Connector Core Services and the deployed Data Apps.

一个组件始终由平台和服务实例的组合来进行特征化。以此Connector实例为例，它正在运行多个数据应用程序。身份包括平台、连接器核心服务和部署的数据应用程序。

![Components SW Stack](./media/SW_Stack_Components_connector_blueprint.png)
##### Figure 4.1.2.1: Components of the Software Stack of an IDS Connector

##### Component Identifier #####

The identity of a combination of platform and service instance is bound to an identifier for the service instance.

平台和服务实例的组合身份与服务实例的标识符绑定在一起。

* Each component gets a unique identified (C_UID) bound to the service instance.
* The uniqueness of this identifier is ensured by the Identity Provider.
* Each C_UID is mapped to a Connector Instance Key (CIK) pair which is typically used for TLS but possibly also data signing and other identity proofs.

Each Service Instance needs to be mapped to one platform it utilizes:

* Each platform blueprint gets a unique identifier during the component certification.
* For a component with Trust level 1, the concrete platform instantiation (running version of this blueprint) does NOT get a specific platform UID (P_UID) as well as key and certificate for this platform instance. Instead, the connector description solely references the (unique) identifier of the certified blueprint (and the operator needs to be trusted to ensure its correct instantiation).
* For components with Trust Level 2 or 3, each platform instantiation needs to be uniquely identified with a UID (P_UID). This UID is required to provide a mapping from service instance to platform.
* Each P_UID is subject of a certificate for the utilized platform key(s) (e.g. AK of a TPM) which enable verification of the platform integrity.
* One P_UID can map to Platform Instance Keys (PIK) for 1-n physical devices/protected VMs:
  * If 1 physical device serves as the component platform: 1 P_UID is mapped to 1 PIK.
  * For distributed platform setups (e.g. with kubernetes): 1 P_UID for the setup maps to n PIKs for the servers in this distributed platform.
  * If connector is run in one protected VM (e.g. SEV SNP): 1 P_UID is mapped to 1 PIK for this SEV-SNP VM.
  * If multiple protected VMs (e.g. SEV SNP) form a distributed platform setup: 1 UID for the setup maps to n PIKs for the VMs which comprise this setup.
  * Valid P_UIDs are mapped to a C_UID in the DAPS. The platform information is verified by another IDS Connector using remote attestation.

![Identity mapping for different scenarios](./media/identity_mapping.png)
##### Figure 4.1.2.2: Identities for IDS Connector Services and Platforms

*(Remark: The platforms in the image may always be either physical devices or protected VMs)*

##### Describing Metadata #####

The IDS targets sovereign data exchange, which does not only comprise a secure exchange of data but also a trustworthy environment for data processing honoring the defined usage control policies. To achieve this goal, it is not sufficient to only know the identity of another IDS component, but additional information about the company operating the component and the utilized software stack is required.
This information is provided in form of the following describing artifacts:

* A **Company Description** for each company operating an IDS component which contains verified information about the company as well as information about its Operational Environment Certification (explained in [Chapter 4.2.3](../4_2_Certification_Perspective/4_2_3_Operational_Environment_Certification.md#operational-environment-certification)).
* **Software Manifests** for the utilized software components which have been evaluated in the Component Certification explained in [Chapter 4.2.4](../4_2_Certification_Perspective/4_2_4_Component_Certification.md#component-certification)). In addition to the awarded certification levels, the manifests for components with Trust Level 2 and 3 contain verified measurements which can be used to validate that the described software is truly running on the device. To support re-usability of components, the description of each software stack consists of three types of Software Manifests used for describing different layers:
  * A **Root of Trust for Measurement (RTM) Manifest** for components of the boot stage,
  * an **Operating System (OS) Manifest** for utilized kernel and user space components, including the container run time enabling the execution of different isolated containers/apps, and
  * an arbitrary number of **App Manifests** per component identifying the utilized containers/apps.
Signatures are utilized to represent the passed stages of the certification process (described in [Chapter 4.2.5](../4_2_Certification_Perspective/4_2_5_Processes.md)) and allow a validation of the correctness of the describing artifacts.
In addition to these static artifacts, the connector operator may add additional attributes to the component's description or have them validated and registered at the DAPS.

All this metadata is provided in machine-readable form. Manifest information for each artifact, such as manifests for all software components, operating system or apps are attached to the artifact itself and will be provided by the IDS Connector that hosts the artifact. Verified Company Descriptions are also provided by IDS Connectors itself, since the ParIS only provides unverified information. Dynamic attributes for each IDS Connector as well as revocation information for Software Manifests are provided by the DAPS.

所有这些元数据都以机器可读的形式提供。针对每个文件的清单信息，例如所有软件组件、操作系统或应用程序的清单，都将附加到文件本身，并由托管文件的IDS Connector提供。由于ParIS仅提供未经验证的信息，因此验证的公司描述也由IDS Connectors本身提供。DAPS提供每个IDS Connector的动态属性以及软件清单的吊销信息。

##### Interactions between IDS Connectors and Identity Components #####

To establish a trusted connection, each connector needs the identity information of the corresponding connector to perform access and usage control decisions. The interactions can be depicted as follows:

为建立可信连接，每个连接器需要相应连接器的身份信息，以执行访问和使用控制决策。交互可以描述如下：

![Interaction between IDS Connectors and Identity Components](./media/IdM_Interactions.png)
##### Figure 4.1.2.3: Interaction between IDS Connectors and Identity Components

1. Each IDS Connector acquires a valid identity certificate from the IDS Device CA.
2. Each IDS Connector requests a current Dynamic Attibute Token from DAPS.
3. When establishing communication, the DAT of both IDS Connector instances is exchanged. This is also matched with the used TLS certificate.


1. 每个IDS Connector从IDS设备CA获取有效的身份证书。
2. 每个IDS Connector从DAPS请求当前的动态属性令牌。
3. 在建立通信时，交换两个IDS Connector实例的动态属性令牌。这也与使用的TLS证书匹配。

To reduce the risk of an attacker abusing a DAT, these DATs should only be disclosed to other communication partnes at will.
To further protect from attacks performed with leaked DATs, each Connector has to validate the certificate used for the TLS connection against the DAT in one of the following two ways:

为减少攻击者滥用DAT的风险，这些DAT应仅按需披露给其他通信方。
为进一步防止滥用泄露的DAT进行攻击，每个Connector必须通过以下两种方法之一，验证用于TLS连接的证书是否与DAT匹配：

* Option 1. The connector uses its identity certificate for TLS connections. In this case, the corresponding IDS connector must assure the identifier in the DAT matches the presented certificate.
* Option 2. The connector uses a separate certificate for TLS connections (e.g., issued by a CA such as Let's Encrypt). In this case, the corresponding IDS Connector must assure the certificate fingerprint matches the one that is embedded in the DAT.


* 选项1。连接器使用其身份证书进行TLS连接。在这种情况下，相应的IDS Connector必须确保DAT中的标识符与所呈现的证书匹配。
* 选项2。连接器使用单独的证书进行TLS连接（例如由Let's Encrypt等CA颁发的）。在这种情况下，相应的IDS Connector必须确保证书指纹与嵌入在DAT中的指纹匹配。

The ParIS only serves untrusted information and thus is not part of this interaction. The DAT will be refreshed on a regular basis, since the token lifetime is limited to a short timeframe. The device identity will be provisioned and refreshed only after expiration (with a long time frame) or in case of revocation. 

ParIS仅提供不受信任的信息，因此不是此交互的一部分。DAT将定期刷新，因为令牌的生命周期仅限于短时间范围内。设备身份将仅在过期（具有长时间范围）或吊销的情况下进行配置和刷新。

##### Component (Identity) Lifecycle #####

| Phase | When does it happen | How is the component identity affected | What about the data? |
| --- | --- | --- | --- |
| **Provisioning** | New components become available when an operator provisions a new instance of the blueprint (on a new device, a new service-instance in the cluster, ...). Provisioning of a new component may consist of a new platform AND service instance or only a new service instance on an already provisioned platform. | A component identity is issued by the Identity Provider: One C_UID for each new Core Connector Services and a P_UID for the platform instances if necessary | No data is available on a newly provisioned component, but arbitrary data can be added afterwards. |
| **Maintaining** | New versions of utilized software are distributed, configuration of the component changes | As long as the trust level of the SW stack AND the operator remain unchanged, the overall connector identity does NOT need to change. In case significant attributes of the component (e.g. trust level) change, the identity as the sum of all attributes changes but the unique identifiers may be used further. | Data already stored on the connector MUST adhere to the defined Usage Control policies so update or migration strategies need to ensure their fulfillment by deleting/removing/making data inaccessible. |
| **Out of service (Decommissioning)** | Component is sold/transferred to another operator, component is not offered/available any longer | The component identity needs to be decommissioned (either only the C_UID or C_UID and P_UID), certificate(s) of the component(s) is(are) revoked. | All data currently on/in the connector needs to be removed (if necessary transfer them to other connectors beforehand). |

#### Identities for Participants ####

The IDS can have many participants interacting ranging from large enterprises and organizations to individuals.
Means for identifying those participants are required, since they are responsible for (at least) operating (or using) an IDS component (e.g., a connector) and thus the actions taken by this component and managing provided data (quality, content, updates, decision on usage policies). Thus, each participants gets a unique identifier (O_UID).

IDS可以有许多参与者进行交互，涉及从大型企业和组织到个人。需要一种识别这些参与者的方法，因为他们负责（至少）操作（或使用）IDS组件（例如连接器），因此该组件所采取的行动和管理所提供的数据（质量，内容，更新，使用政策决策）。因此，每个参与者都获得一个唯一标识符（O_UID）。

Based on this, an identity management for participants can either be based on identities for the organizations themselves or for the human users working for this organizations. Identities are typically bound to private-public key pairs generated for each identity and confirmed by the Identity Provider. Respective processes are required to ensure correct mapping of the key pairs and the identities to be utilized in the IDS. This, however, requires a CA that provides identity certificates for employees of Participants. This is yet to be defined in detail. 

基于此，参与者的身份管理可以基于组织自身或该组织的工作人员的身份。身份通常绑定到为每个身份生成的私钥-公钥对，并由身份提供者确认。必须采取相应的流程来确保正确映射密钥对和要在IDS中使用的身份。但是，这需要提供用于参与者员工的身份证书的CA。需要进一步详细说明这点。

#### Trust Bootstrapping and Trust Chains ####

Identifying and authenticating an IDS connector requires an evaluation of many complementary aspects. The following table provides an overview of these aspects and the entities responsible for them.

| High-Level Aspect | Detailed Aspect | Trust Level | Entity Responsible | Validation necessary for issuing proof | Proof the IDS connector needs to validate |
| --- | --- | --- | --- | --- | --- |
| Connector ID (C_UID) belongs to communication partner | C_UID is unique | all | CA | Before issuing Connector Identity Certificate, process depends on implementation of C_UID | Connector Identity Certificate |
| | Mapping of C_UID to Connector Instance Key (CIK) | all | CA | - | Connector Identity Certificate, usage of key material by communication partner |
| | Only the connector has access to CIK | 1 | Operator | - | - |
| | | 2, 3 | CA and Hardware Manufacturer | CA verifies hardware protection for CIK (Trust chain to HW Manufacturer) | Connector Identity Certificate |
| C_UID is used by certified connector stack | - | 1 | Operator | **No validation**, operator must only request certificates for instances of certified SW stacks | - |
| | Platform ID (P_UID) is unique | 2, 3 | CA | Before issuing connector identity certificate, process depends on implementation of P_UID | Platform Identity Certificate |
| | Mapping of P_UID to Platform Instance Key (PIK) | 2, 3 | CA | - | Platform Identity Certificate |
| | Only the identified platform has access to PIK | 2, 3 | CA and Hardware Manufacturer | CA verifies hardware protection for PIK (Trust chain to HW Manufacturer) | Platform Identity Certificate |
| | Mapping C_UID to P_UID | 2, 3 | CA | Before issuing Connector Identity Certificate, CA ensures that the CIK is protected by the PIK | Mapping to P_UID in Connector Identity Certificate |
| | Measurements for currently running software stack | 2, 3 | HW Trust Anchor, Certified Software | - | Measurements signed by PIK for platform and optionally service instance (in case of 1:1 mapping), Measurements signed by CIK for service instance (in case of multiple services on one platform) |
| | Measurements belong to certified software stack | 2, 3 | Evaluation Facility and Certification Body | Part of Certification Process | Signed SW Manifests, Provided Measurements |
| Connector with C_UID is operated by certified organization | C_UID belongs to component managed by a certified organization | all | CA | Before issuing Connector Identity Certificate, the CA validated that requesting organization has IDS Operational Environment Certification. | Connector Identity Certificate |
| | Organization ID (O_UID) is unique | all | CA, Support Organization | Before issuing Connector Identity Certificate including O_UID, CA checks uniqueness with Support Organization | - |
| | Mapping from C_UID to O_UID | all | CA | Before issuing Connector Identity Certificate, CA ensures that request for it was issued by respective organization | Connector Identity Certificate |
| | O_UID belongs to certified organization | all | Evaluation Facility and Certification Body | Part of Certification Process | Signed Company Description, O_UID in Connector Identity Certificate |
| Up-to-Date(ness of) Information | The provided certificates are still valid (not revoked). | all | CA | In case of revocation, the CA updates its revocation services (e.g. OCSP server). | Revocation status, e.g. from OCSP Server. |
| | The certification for the software stack is still valid (not revoked). | 2, 3 | DAPS | In case of revocation or update of the certification, the DAPS updates the status stored for the respective metadata. | Dynamic Attribute Token (DAT) including revocation status of SW Manifests |
| | The certification for the organization is still valid (not revoked). | all | DAPS | In case of revocation or update of the certification, the DAPS updates the status stored for the respective metadata. | Validate Dynamic Attribute Token (DAT) and check contained revocation status of Company Description |
| | Additional dynamic attributed for the IDS Connector | all | DAPS | Before adding or changing attributes for a connector in the DAPS, the DAPS provider validates the correctness of the provided information (details depend on type of attribute). | Dynamic Attribute Token (DAT) |
