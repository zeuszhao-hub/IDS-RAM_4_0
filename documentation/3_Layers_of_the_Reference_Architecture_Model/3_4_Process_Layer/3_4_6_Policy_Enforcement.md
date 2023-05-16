### Policy Enforcement ###

Enforcement of data usage restrictions (Policy Enforcement) can be characterized and implemented in different forms. Organizational rules or legal contracts can be substituted, or at least accompanied, by technical solutions, which introduce a new level of security. Vice versa, technical solutions can be accompanied by organizational rules or legal contracts (e.g., to compensate missing capabilities of the technical solution).

数据使用限制（策略执行）的执行可以以不同的形式进行描述和实现。组织规则或法律合同可以被替换或至少与技术解决方案一起使用，这引入了新的安全级别。反之，技术解决方案可以与组织规则或法律合同一起使用（例如，为了弥补技术解决方案缺失的功能）。

Although it is a commonly used solution to address data usage control restrictions by organizational rules, the IDS focuses on technical enforcement.
To enforce data usage restrictions, a system’s actions need to be monitored and potentially intercepted by control points (i.e., Policy Enforcement Points). These actions must be judged by a decision engine (i.e., a Policy Decision Point) for requesting permission or denial. In addition to just allowing or denying an action, the decision engine may also require modification of the action. A PEP component encapsulates the enforcement.

尽管组织规则是解决数据使用控制限制的常见解决方案，但IDS侧重于技术执行。要执行数据使用限制，必须监视系统的操作，并由控制点（即策略执行点）进行潜在的拦截。这些操作必须由决策引擎（即策略决策点）进行审核，请求获得许可或拒绝。除了允许或拒绝操作外，决策引擎可能还要求修改操作。PEP组件封装了执行过程。

#### Policy Enforcement Point (PEP) ####

**The Policy Enforcement Point (PEP)** has two main tasks. First, it is the entry point for enforcement, meaning it is the point where data or metadata is stopped and transferred to the PDP, the PDP makes a decision and returns it to the PEP. Secondly, the PEP will subsequently manipulate or lock the data according to the decision.

策略执行点（PEP）有两个主要任务。首先，它是执行的入口点，这意味着数据或元数据在这里被拦截并传输到策略决策点（PDP），PDP做出决策并将其返回给PEP。其次，PEP随后会根据PDP的决策操作或锁定数据，以确保PDP执行的数据使用限制被正确应用。

![Communication Policy Enforcement Point and Policy Decision Point](media/Communication-PEP-and-PDP.drawio.png)

##### Figure 3.4.6.1: Communication Policy Enforcement Point and Policy Decision Point

#### Policy Decision Point (PDP) ####

As mentioned before, the **Policy Decision Point (PDP)** makes the decision based on the data sent by the PEP and the deposited policies. The policies specifies the conditions and obligations. The result of the evaluation is send to the PEP for enforcement (see [Figure 3.4.6.1](#figure-3461-communication-policy-enforcement-point-and-policy-decision-point)). The PDP also interprets the policies in terms of context information and instructions. This means the policy decision may also depend on additional information that is not present in the intercepted system action itself. This includes information about the context, such as data flows or the geographical location of an entity. It is also possible to specify pre- or post-conditions that have to hold before (e.g., integrity check of the environment) and after (e.g., data item is deleted after usage) decision-making. In addition, it is possible to define on-conditions that have to hold during usage (e.g., only during business hours). These conditions usually specify constraints and permissions that have to be fulfilled before, during, and after using data (see [Figure 3.4.6.2](#figure-3462-usage-control-pre--on--and-post-conditions)). This is linked to the other components presented in this section.

正如之前提到的，策略决策点（PDP）根据PEP发送的数据和明确规定的策略做出决策。这些策略规定了条件和义务。决策的结果将发送给PEP进行执行（参见图3.4.6.1）。PDP还根据上下文信息和指令解释策略。这意味着策略决策还可能取决于拦截的系统动作本身中不存在的其他信息。这包括关于上下文的信息，例如数据流或实体的地理位置。还可以指定在进行决策之前（例如，环境完整性检查）和之后（例如，使用后删除数据项）必须满足的先决条件和后置条件。此外，还可以定义在使用过程中必须满足的条件（例如，仅在营业时间内）。这些条件通常规定了在使用数据之前、期间和之后必须满足的限制和权限（参见图3.4.6.2）。这与本节中介绍的其他组件相关联。

![image](media/usage-control-conditions.drawio.png)

##### Figure 3.4.6.2: Usage Control Pre-, On-, and Post-Conditions

#### Policy Information Point (PIP) ####

**The Policy Information Point (PIP)** is the component to determine information such as context information during policy evaluation. This information can then be used in the PDP for decision making. (More about context information in [Section 4.1.6](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_6_Usage_Control.md#context-information-and-obligation-fulfillment))

#### Policy Execution Point (PXP) ####

**The Policy Execution Point (PXP)** is the components for implementing instructions or requirements these can be before a decision and their successful execution can be included as a condition, or they can be executed after a decision has been made. (More about the execution of instructions in [Section 4.1.6](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_6_Usage_Control.md#usage-control-in-a-connector))

#### Policy Management Point (PMP) and Policy Administration Point (PAP) ####

**The Policy Management Point (PMP)** and **the Policy Administration Point (PAP)** are not components that are directly needed for enforcement, but should be briefly mentioned here. These components are important for specification and management of usage policies. The PMP, as the name implies, is responsible for the management or handling of the policies. It makes the policies available to the PDP, activates, deactivates and deletes them. The PAP is used to support the creation and specification of usage policies often via a user-friendly graphical interface.

#### Interaction in the IDS Connector ####

**An example process** in the IDS Connector. Let's assume there is a policy describing that data can only be used when the connector is in the EU (Locale) and the usage is sent to the Clearing House after the data has been used (Log). We assume that such a policy is deposited (negotiated) for the PDP and the components to implement it are available. Now a process may exist to enforce Access Control, on the Data Provider side. It basically does not matter if it is a send or fetch of the data. To implement Data Usage Control, there must also be a process on the Data Consumer side. We want to focus here on the case of Usage Control on the Data Consumer side, which can be used very similarly also for Access Control, since the Data Provider, has a high interest to enforce this as early as possible. [Figure 3.4.6.3](#figure-3463-usage-control-components-inside-an-ids-connector) is a component diagram of an IDS Connector that receives data and Components for Usage Contral with an standalone Usage Control Container.The IDS Components (IDS PEP, IDS PIP, IDS PXP) are more generic and standardized components, these are connected to a specific implmentations (PXP, PIP, PXP) of a policy engine or framework to be able to enforce it. The core component - IDS Connector Core - of the IDS Connector (see [Section 3.5.2](../3_5_System_Layer/3_5_2_IDS_Connector.md#ids-connector)) is of central importance. It knows the routes of the data and can thus integrate the PEPs at appropriate points. This can be done when the data leaves the IDS Connector Core or e.g. via Interceptor Pattern for completely controlled data flows. If data is to flow to a data sink (app, storage), the IDS Connector Core knows the destination and it knows the identifications of the data, which are transferred in the form of metadata. Before the data flows directly, the PEP acts in front of it and sends all the required information to the PDP. The implementation of the solution can be implemented in the IDS Connector Core or as a standalone application (runs as an IDS Connector App), but the principle remains the same. The PDP analyzes the policy and must be connected via the IDS Connector Core to a system that can provide a statement about the IDS Connector location. For example the IDS ParIS is used to resolve the location information. If the IDS Connector is located in the EU, the data is released and the PEP does not have to change anything. The PDP informs the PEP about this decision. Now there is the instruction to log the data usage information in the Clearing House. A PXP which is connected to the Clearing House is responsible for logging the usage information via the IDS Connector Core. Using this PXP, the PDP can log important information and parameters provided by the PEP and PIP. More details about different types of context information and the execution of instructions can be found in [Section 4.1.6](../../4_Perspectives_of_the_Reference_Architecture_Model/4_1_Security_Perspective/4_1_6_Usage_Control.md#usage-control-in-a-connector). [Figure 3.4.6.4](#figure-3464-usage-control-example-sequence-with-context-information-pip-and-execution-pxp-call) shows a sequence like discribed in the example within the procedure calls between the Components.

在IDS连接器中的一个示例过程。假设存在一个策略，描述只有当连接器在欧盟（位置）并且在数据使用后使用的数据被发送到清算所时，数据才能被使用（日志记录）。我们假设这样的策略已经被制定（协商），以PDP和其它实施此策略的组件。现在可以存在一个执行访问控制的过程，在数据提供方的一边。这基本上不重要，无论是发送还是获取数据。要实现数据使用控制，数据使用方也必须存在一个过程。我们要在此重点介绍数据使用方上的控制场景，它与访问控制非常相似，因为数据提供方非常希望尽早实施这项控制。图3.4.6.3是一个IDS连接器的组件图，它接收数据和用于使用控制的组件，并具有独立的使用控制容器。IDS组件（IDS PEP、IDS PIP、IDS PXP）是更通用和标准化的组件，这些组件连接到特定的策略引擎或框架的实现（PXP、PIP、PXP），以便可以对其进行强制执行。IDS连接器（参见3.4.5.2节）的核心组件，即IDS连接器核心，非常重要。它知道数据的路由，因此可以在适当的点集成PEP。当数据离开IDS连接器核心时或通过完全控制的数据流的拦截器模式时，可以这样做。如果数据要流向数据汇（应用程序、存储），IDS连接器核心知道目的地，并且知道以元数据的形式传递的数据标识。在数据直接流动之前，PEP在其前面起作用并将所有所需信息发送给PDP。解决方案的实现可以在IDS连接器核心中实现，也可以作为一个独立的应用程序来实现（作为IDS连接器应用程序运行），但原理仍然相同。PDP分析策略，并必须通过IDS连接器核心连接到可以提供有关IDS连接器位置的系统。例如，使用IDS ParIS来解析位置信息。如果IDS连接器位于欧盟，数据将被释放，PEP无需更改任何内容。PDP通知PEP有关此决策的信息。现在有指示在清算所中记录数据使用信息。连接到清算所的PXP负责通过IDS连接器核心记录使用信息。使用此PXP，PDP可以记录PEP和PIP提供的重要信息和参数。有关不同类型的上下文信息和指令执行的更多细节，请参见4.1.6节。图3.4.6.4显示了组件之间的过程调用中描述的示例的序列。

![Usage Control Components inside an IDS Connector](media/uc-example-Components.drawio.png)

##### Figure 3.4.6.3: Usage Control Components inside an IDS Connector

![Usage Control Example Sequence with Context Information (PIP) and Execution (PXP) call](media/uc-example-Sequence.drawio.png)

##### Figure 3.4.6.4: Usage Control Example Sequence with Context Information (PIP) and Execution (PXP) call
