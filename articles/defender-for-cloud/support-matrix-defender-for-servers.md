---
title: Support for the Defender for Servers plan in Microsoft Defender for Cloud
description: Review support requirements for the "Defender for Servers" plan in Microsoft Defender for Cloud.
ms.topic: limits-and-quotas
ms.custom: linux-related-content
author: dcurwin
ms.author: dacurwin
ms.date: 09/08/2024
---

# Defender for Servers support

This article summarizes support information for the Defender for Servers plan in Microsoft Defender for Cloud.

## Network requirements

Validate the following endpoints are configured for outbound access so that Azure Arc extension can connect to Microsoft Defender for Cloud to send security data and events:

- For Defender for Server multicloud deployments, make sure that the [addresses and ports required by Azure Arc](/azure/azure-arc/data/connectivity#details-on-internet-addresses-ports-encryption-and-proxy-server-support) are open.

- For deployments with GCP connectors, open port 443 to these URLs:

  - `osconfig.googleapis.com`
  - `compute.googleapis.com`
  - `containeranalysis.googleapis.com`
  - `agentonboarding.defenderforservers.security.azure.com`
  - `gbl.his.arc.azure.com`

- For deployments with AWS connectors, open port 443 to these URLs:

  - `ssm.<region>.amazonaws.com`
  - `ssmmessages.<region>.amazonaws.com`
  - `ec2messages.<region>.amazonaws.com`
  - `gbl.his.arc.azure.com`

## Azure cloud support

This table summarizes Azure cloud support for Defender for Servers features.

| **Feature/Plan** | **Azure** | **Azure Government** | **Microsoft Azure operated by 21Vianet**<br/>**21Vianet** |
|--- | --- | --- | --- |
| [Microsoft Defender for Endpoint integration](./integration-defender-for-endpoint.md) | GA | GA | NA |
| [Compliance standards](./regulatory-compliance-dashboard.md)<br/>Compliance standards might differ depending on the cloud type.| GA | GA | GA |
| [Microsoft Cloud Security Benchmark recommendations for OS hardening](apply-security-baseline.md) | GA | GA | GA |
| [VM vulnerability scanning-agentless](concept-agentless-data-collection.md) | GA | NA | NA |
| [VM vulnerability scanning - Microsoft Defender for Endpoint sensor](deploy-vulnerability-assessment-defender-vulnerability-management.md) | GA | NA | NA |
| [Just-in-time VM access](./just-in-time-access-usage.yml) | GA | GA | GA |
| [File integrity monitoring](./file-integrity-monitoring-overview.md)  | GA | GA | GA |
| [Docker host hardening](./harden-docker-hosts.md)  | GA | GA | GA |
| [Agentless secret scanning](secrets-scanning.md) | GA | NA | NA |
| [Agentless malware scanning](agentless-malware-scanning.md) | GA | NA | NA |
| [Agentless assessment checks for endpoint detection and response solutions](endpoint-detection-response.md) | GA | NA | NA |
| [System updates and patches](enable-periodic-system-updates.md) | GA | GA | GA |
| [Kubernetes node protection](kubernetes-nodes-overview.md) | GA | NA | NA |

## Windows machine support

The following table shows feature support for Windows machines in Azure, Azure Arc, and other clouds.

| **Feature** | **Azure VMs*<br/> **[VM Scale Sets (Flexible orchestration](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-orchestration-modes#scale-sets-with-flexible-orchestration)** | **Azure Arc-enabled machines** | **Defender for Servers required** |
|--|:-:|:-:|:-:|
| [Microsoft Defender for Endpoint integration](integration-defender-for-endpoint.md) | ✔</br> Available on: Windows Server 2022, 2019, 2016, 2012 R2, 2008 R2 SP1, [Windows 10/11 Enterprise multi-session](/azure/virtual-desktop/windows-10-multisession-faq) (formerly Enterprise for Virtual Desktops)<br>Not available on: Azure VMs running Windows 10 or Windows 11 (except if running Windows 10/11 Enterprise multi-session) | ✔ | Yes |
| [Virtual machine behavioral analytics (and security alerts)](alerts-reference.md) | ✔ | ✔ | Yes |
| [Fileless security alerts](alerts-windows-machines.md) | ✔ | ✔ | Yes |
| [Network-based security alerts](other-threat-protections.md#network-layer) | ✔ | - | Yes |
| [Just-in-time VM access](just-in-time-access-usage.yml) | ✔ | - | Yes |
| [File Integrity Monitoring](file-integrity-monitoring-overview.md) | ✔ | ✔ | Yes |
| [Network map](protect-network-resources.md#network-map) | ✔ | - | Yes |
| [Regulatory compliance dashboard & reports](regulatory-compliance-dashboard.md) | ✔ | ✔ | Yes |
| [Docker host hardening](./harden-docker-hosts.md) | - | - | Yes |
| [Missing OS patches assessment](apply-security-baseline.md) | ✔ | ✔ | Azure: Yes<br><br>Azure Arc-enabled: Yes |
| Security misconfigurations assessment | ✔ | ✔ | Azure: No<br><br>Azure Arc-enabled: Yes |
| [Endpoint protection assessment](supported-machines-endpoint-solutions-clouds-servers.md#supported-endpoint-protection-solutions) | ✔ | ✔ | Azure: No<br><br>Azure Arc-enabled: Yes |
| Disk encryption assessment | ✔</br>([supported scenarios](/azure/virtual-machines/windows/disk-encryption-windows)) | - | No |
| Third-party vulnerability assessment (BYOL) | ✔ | - | No |
| [Network security assessment](protect-network-resources.md) | ✔ | - | No |
| [System updates and patches](enable-periodic-system-updates.md) | ✔ | ✔ | Yes (Plan 2)|

## Linux machine support

The following table shows feature support for Linux machines in Azure, Azure Arc, and other clouds.

| **Feature** | **Azure VMs**<br/> **[VM Scale Sets (Flexible orchestration](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-orchestration-modes#scale-sets-with-flexible-orchestration)** | **Azure Arc-enabled machines** | **Defender for Servers required** |
|--|:-:|:-:|:-:|
| [Microsoft Defender for Endpoint integration](integration-defender-for-endpoint.md) | ✔ <br> ([supported versions](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-linux)) | ✔ | Yes |
| [Virtual machine behavioral analytics (and security alerts)](./azure-defender.md) | ✔</br> Supported versions | ✔ | Yes |
| [Fileless security alerts](alerts-windows-machines.md) | - | - | Yes |
| [Network-based security alerts](other-threat-protections.md#network-layer) | ✔ | - | Yes |
| [Just-in-time VM access](just-in-time-access-usage.yml) | ✔ | - | Yes |
| [File Integrity Monitoring](file-integrity-monitoring-overview.md) | ✔ | ✔ | Yes |
| [Network map](protect-network-resources.md#network-map) | ✔ | - | Yes |
| [Regulatory compliance dashboard & reports](regulatory-compliance-dashboard.md) | ✔ | ✔ | Yes |
| [Docker host hardening](./harden-docker-hosts.md) | ✔ | ✔ | Yes |
| [Missing OS patches assessment](apply-security-baseline.md) | ✔ | ✔ | Azure: Yes<br><br>Azure Arc-enabled: Yes |
| Security misconfigurations assessment | ✔ | ✔ | Azure: No<br><br>Azure Arc-enabled: Yes |
| [Endpoint protection assessment](supported-machines-endpoint-solutions-clouds-servers.md#supported-endpoint-protection-solutions) | - | - | No |
| Disk encryption assessment | ✔</br> [supported scenarios](/azure/virtual-machines/windows/disk-encryption-windows)) | - | No |
| Third-party vulnerability assessment (BYOL) | ✔ | - | No |
| [Network security assessment](protect-network-resources.md) | ✔ | - | No |
| [System updates and patches](enable-periodic-system-updates.md) | ✔ | ✔ | Yes (Plan 2)|

## Multicloud machines

The following table shows feature support for AWS and GCP machines.

| **Feature** | **Availability in AWS** | **Availability in GCP** |
|--|:-:|
| [Microsoft Defender for Endpoint integration](integration-defender-for-endpoint.md) | ✔ | ✔ |
| [Virtual machine behavioral analytics (and security alerts)](alerts-reference.md) | ✔ | ✔ |
| [Fileless security alerts](alerts-windows-machines.md) | ✔ | ✔ |
| [Network-based security alerts](other-threat-protections.md#network-layer) | - | - |
| [Just-in-time VM access](just-in-time-access-usage.yml) | ✔ | - |
| [File Integrity Monitoring](file-integrity-monitoring-overview.md) | ✔ | ✔ |
| [Network map](protect-network-resources.md#network-map) | - | - |
| [Regulatory compliance dashboard & reports](regulatory-compliance-dashboard.md) | ✔ | ✔ |
| [Docker host hardening](harden-docker-hosts.md) | ✔ | ✔ |
| [Missing OS patches assessment](apply-security-baseline.md)| ✔ | ✔ |
| Security misconfigurations assessment | ✔ | ✔ |
| [Endpoint protection assessment](supported-machines-endpoint-solutions-clouds-servers.md#supported-endpoint-protection-solutions) | ✔ | ✔ |
| Disk encryption assessment | ✔</br>(for [supported scenarios](/azure/virtual-machines/windows/disk-encryption-windows)) | ✔</br>(for [supported scenarios](/azure/virtual-machines/windows/disk-encryption-windows)) |
| Third-party vulnerability assessment | - | - |
| [Network security assessment](protect-network-resources.md) | - | - |
| [Cloud security explorer](how-to-manage-cloud-security-explorer.md) | ✔ | - |
| [Agentless secret scanning](secrets-scanning.md) | ✔ | ✔ |
| [Agentless malware scanning](agentless-malware-scanning.md) | ✔ | ✔ |
| [Endpoint detection and response](endpoint-detection-response.md) | ✔ | ✔ |
| [System updates and patches](enable-periodic-system-updates.md) | ✔ <br> (With Azure Arc) | ✔ (With Azure Arc) |

## Next steps

Start planning your [Defender for Servers deployment](plan-defender-for-servers.md).
