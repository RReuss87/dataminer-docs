---
uid: General_Main_Release_10.3.0_CU5
---

# General Main Release 10.3.0 CU5 – Preview

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!TIP]
> For information on how to upgrade DataMiner, see [Upgrading a DataMiner Agent](xref:Upgrading_a_DataMiner_Agent).

### Enhancements

#### Security enhancements [ID_36294]

<!-- 36294: MR 10.3.0 [CU5] - FR 10.3.8 -->

A number of security enhancements have been made.

#### Service & Resource Management: Enhanced performance of GetEligibleResources call [ID_36430]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

Because of a number of enhancements, overall performance of the *GetEligibleResources* call has increased.

#### DataMiner Agents joining a cluster will now synchronize their ProtocolScripts\DllImport folder [ID_36494]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

When a DataMiner Agent joins a cluster, it will now synchronize its `ProtocolScripts\DllImport` folder.

Also, when processing a protocol, a DataMiner Agent will now synchronize

- the files in the `ProtocolScripts/DllImport` folder, and
- the files in the folders mentioned in the *QAction@dllImport* attribute.

#### Cassandra & Amazon Keyspaces: 'analytics_changepointalarmentries_v2' table renamed to 'ai_cpalarms' [ID_36503]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

In a *Cassandra Cluster* and an *Amazon Keyspaces* database, the `analytics_changepointalarmentries_v2` table has now been renamed to `ai_cpalarms`.

As this new table name is quite a bit shorter, for both types of databases, keyspace prefixes can now have a maximum length of 20 characters instead of 11 characters.

#### Stream Viewer will now display parameter IDs in decimal format instead of octal format [ID_36525]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

Stream Viewer will display an error message when an SNMP poll group contained either an invalid parameter or a parameter that did not have its SNMP setting enabled.

Up to now, that error message would contain the ID of the parameter in octal format. From now on, it will contain the ID of the parameter in decimal format instead.

#### Factory reset tool will no longer try to delete non-existing folders [ID_36550]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

Up to now, the factory reset tool *SLReset.exe* would log an exception each time it had tried to delete a non-existing folder. From now on, when it has to delete a folder, it will first check whether that folder exists. If not, it will not try to delete it.

#### SNMP tables: Columns of type 'retrieved' can now be placed in between columns of type 'snmp' [ID_36559]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

Up to now, when an SNMP table had columns of type "retrieved" in between columns of type "snmp", problems could occur. All columns of type "retrieved" had to be grouped and placed at the right of the columns of type "snmp".

From now on, in an SNMP table, columns of type "retrieved" can be placed in between columns of type "snmp", providing the primary key column is a column of type "snmp" and not a column of type "retrieved".

#### Service & Resource Management: Enhanced performance [ID_36568]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

Because of a number of enhancements with regard to fetching LinkerTableEntries of function resources, overall performance has increased.

### Fixes

#### SLAnalytics: Incorrect trend predictions in case of incorrect data ranges set in the protocol [ID_36521]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

If, in the protocol, a data range is specified for a parameters for which trend data prediction is required, the trend prediction algorithm will cap the prediction values to the data range. For example, if a parameter has a rangeLow value equal to 0 and a rangeHigh value equal to 100, the prediction will not contain values lower than 0 or higher than 100.

From now on, if the trend data contains values outside of the specified data range, the trend prediction algorithm will no longer consider the data range values to be valid or reliable, and will not limit the prediction to this range.

#### Problem with protocol.SendToDisplay API call [ID_36528]

<!-- MR 10.2.0 [CU17]/10.3.0 [CU5] - FR 10.3.8 -->

When the following protocol API call was used to update specific matrix crosspoints, in some cases, the API call could ignore the physical size of the matrix. Also, the API call could change the dimensions of future `ParameterChangeEventMessages`.

```csharp
protocol.SendToDisplay(matrixReadParameterId, changedInputs, changedOutputs);
```

#### Problem with SLElement due to timeout actions of an element being overwritten [ID_36591]

<!-- MR 10.3.0 [CU5] - FR 10.3.8 -->

In some rare cases, an error could occur in SLElement when a timeout action of an element with multiple connections would overwrite another timeout action of the same element.
