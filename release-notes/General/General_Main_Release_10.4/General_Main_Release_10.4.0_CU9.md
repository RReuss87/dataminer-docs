---
uid: General_Main_Release_10.4.0_CU9
---

# General Main Release 10.4.0 CU9 - Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For information on how to upgrade DataMiner, see [Upgrading a DataMiner Agent](xref:Upgrading_a_DataMiner_Agent).

### Enhancements

#### OpenSearch: Enhanced performance of alarm queries [ID 40674]

<!-- MR 10.4.0 [CU9] - FR 10.4.12 -->

Alarm filters containing brackets can now be translated to OpenSearch queries. This will considerably improve overall performance of alarm queries against OpenSearch databases.

### Fixes

#### Problem when DataMiner Agent is named DATAMINER [ID 40743]

<!-- MR 10.4.0 [CU9] - FR 10.4.12 -->

From DataMiner 10.4.0 [CU2]/10.4.5 onwards, when the computer name of a DataMiner server was DATAMINER, the server would no longer function correctly.

> [!TIP]
> See also: Known issue [Problem when DMA server is named DATAMINER](xref:KI_Problem_when_server_name_is_DATAMINER)

#### Problem with alarm severity of a service not being updated correctly [ID 40840]

<!-- MR 10.3.0 [CU21]/10.4.0 [CU9] - FR 10.4.12 -->

In some cases, the alarm severity of a service would not be updated correctly when, during a row update, both the display key and the monitored value had been changed.

#### Failover: Problem with SLSNMPManager at startup [ID 40883]

<!-- MR 10.3.0 [CU21]/10.4.0 [CU9] - FR 10.4.12 -->

When a DataMiner Agent that was part of a Failover setup started up, in some cases, SLSNMPManager could stop working.