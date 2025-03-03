---
uid: RemoteLogCollection
---

# Remote Log Collection

The Remote Log Collection feature allows our experts to collect DataMiner log and memory dump files independently, increasing efficiency of investigations.

The packages generated by the [Log Collector tool](xref:SLLogCollector) are automatically transferred to secure storage in the cloud, so that the experts at Skyline Communications have immediate access to them.

To increase transparency, a detailed audit log will be created each time remote log collection is requested (see [Auditing](xref:DCP_Auditing)).

## Requirements

To use this feature, your system needs to meet the following requirements:

- Your system must be connected to dataminer.services. For information on how to connect, see [Connecting your DataMiner System to dataminer.services](xref:Connecting_your_DataMiner_System_to_the_cloud).

- Cloud Pack version 2.8.1 or later must be installed **on all DataMiner Agents** from which logs need to be collected. You can always find the latest Cloud Pack on [DataMiner Dojo](https://community.dataminer.services/downloads/).

   > [!NOTE]
   > If you install the Cloud Pack on additional DataMiner Agents that **do not allow network traffic** towards `*.dataminer.services`, after the installation, **uninstall DataMiner CloudGateway** on those Agents. See [uninstalling a program in Windows](https://support.microsoft.com/en-us/windows/uninstall-or-remove-apps-and-programs-in-windows-4b55f974-2cc6-2d2b-d092-5905080eaf98).

- Port **5100** must be open for traffic on the **internal network** for the remote log collection to work. For more information on this endpoint, see [Customizing the dataminer.services endpoint configuration](xref:Custom_cloud_endpoint_configuration).
