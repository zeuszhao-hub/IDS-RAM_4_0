### Clearing House ###

The IDS Clearing House consists of an IDS Connector (see section [3.5.2](./3_5_2_IDS_Connector.md#ids-connector)) and bases all its functions on a logging service that records information relevant for clearing and billing as well as usage control. The information sent to the Clearing House is defined in the Process Layer.

IDS清算所由一个IDS连接器（参见第3.5.2节）组成，并基于记录与清算和计费以及使用控制相关的信息的日志记录服务提供其所有功能。发送到清算所的信息在过程层中定义。

![Clearing House Architecture](media/clearing_house_architecture.png)

##### Figure 3.5.5.1: Clearing House Architecture

The Clearing House uses this information to provide a Clearing and Settlement Service on the basis of usage contracts and helps with the automization of payments between Data Provider and Data Consumer. It can also use this information to provide a Billing Service to allow the Data Space Operator the billing of the participants. The UC Claim Validation service uses the logged usage control data to allow the validation of usage claims on resources.

清算所使用这些信息基于使用合同提供清算和结算服务，并协助数据提供方和数据使用方之间的支付自动化。它还可以使用这些信息提供计费服务，以允许数据空间操作员对参与者进行计费。UC Claim Validation服务利用记录的使用控制数据，允许对资源使用的要求进行验证。