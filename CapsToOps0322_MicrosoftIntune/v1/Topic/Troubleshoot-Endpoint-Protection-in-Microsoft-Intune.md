---
title: Troubleshoot Endpoint Protection in Microsoft Intune
ms.custom: na
ms.reviewer: na
ms.service: microsoft-intune
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
author: Nbigman
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - hu-hu
  - it-it
  - ja-jp
  - ko-kr
  - nl-nl
  - pl-pl
  - pt-br
  - pt-pt
  - ru-ru
  - sv-se
  - tr-tr
  - zh-cn
  - zh-tw
---
# Troubleshoot Endpoint Protection in Microsoft Intune

## <a name="BKMK_EP"></a>Resources to help you solve Endpoint Protection problems
Use the information in this section to help you solve problems while using [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)].

### Endpoint Protection error messages
This section describes potential causes and solutions for the following errors and warnings, which appear in the **Endpoint Protection Status** pane in the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)].

|Status item|Potential causes|Potential solutions|
|---------------|--------------------|-----------------------|
|**Endpoint Protection engine unavailable**|The [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] engine was corrupted or deleted.|If the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] engine is corrupted, you can try updating or reinstalling the software.<br /><br />To force an immediate update, click **Update** in the [!INCLUDE[epshort](../Token/epshort_md.md)] client software (found in the taskbar on managed computers.<br /><br />If the engine cannot be updated, you must reinstall the [!INCLUDE[epshort](../Token/epshort_md.md)] engine.<br /><br />In the list of installed programs in Control Panel on the managed computer, locate **Microsoft Intune Endpoint Protection Agent**, and then uninstall the application.<br /><br />During the next update synchronization, the Microsoft Online Management Update Manager detects the missing program and reinstalls it at the scheduled installation time.|
|**Endpoint Protection disabled**|[!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] was disabled by an administrator using a policy or by a user on a managed computer.|If [!INCLUDE[epshort](../Token/epshort_md.md)] is disabled, you can enable it from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from a managed computer. Do one of the following:<br /><br />To enable [!INCLUDE[epshort](../Token/epshort_md.md)] from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], open the **Policy** workspace, and then change the **Enable Endpoint Protection** setting in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable [!INCLUDE[epshort](../Token/epshort_md.md)] from a managed computer, start the [!INCLUDE[wit_firstref](../Token/wit_firstref_md.md)][!INCLUDE[epshort](../Token/epshort_md.md)] client from the notification area and you will be prompted to enable [!INCLUDE[epshort](../Token/epshort_md.md)].|
|**Real-time protection disabled**|Real-time protection was disabled by an administrator who used Policy or by a user on a managed computer.|If real-time protection is disabled, you can enable it from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from a managed computer. Do one of the following:<br /><br />To enable real-time protection from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], open the **Policy** workspace, and then change the **Enable real-time protection** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable real-time protection from a managed computer, start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the notification area. You are prompted to enable real-time protection at that time.|
|**Download scanning disabled**|Download scanning was disabled by an administrator by using policy or by a user on a managed computer.|If download scanning is disabled, you can enable it from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from a managed computer. Do one of the following:<br /><br />To enable download scanning from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], open the **Policy** workspace, and then change the **Scan all Downloads** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable download scanning from a managed computer, start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the notification area. Click the **Settings** tab, click **Real-time protection**, select the **Scan all downloads** check box, and then click **Save changes**.|
|**File and program activity monitoring disabled**|File and program activity monitoring was disabled by an administrator who used Policy or by a user on a managed computer.|If file and program activity monitoring is disabled, you can enable it from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from a managed computer. Do one of the following:<br /><br />To enable file and program activity monitoring from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], open the **Policy** workspace, and then change the **Monitor file and program activity on computers** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable file and program activity monitoring from a managed computer, start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the notification area. Click the **Settings** tab, click **Real-time protection**, select the **Monitor file and program activity on your computer** check box, and then click **Save changes**.|
|**Behavior monitoring disabled**|Behavior monitoring was disabled by an administrator who used Policy or by a user on a managed computer.|If behavior monitoring is disabled, you can enable it from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from a managed computer. Do one of the following:<br /><br />To enable behavior monitoring from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], open the **Policy** workspace, change the **Enable behavior monitoring** setting to **Yes** in the policies that apply to the computer, and then restart the managed computer.<br /><br />Or,<br /><br />to enable behavior monitoring from a managed computer, start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the notification area. Click the **Settings** tab, click **Real-time protection**, select the **Enable behavior monitoring** check box, and then click **Save changes**. Then, restart the computer.|
|**Script scanning disabled**|Script scanning was disabled by an administrator who used Policy or by a user on a managed computer.|If script scanning is disabled, you can enable it from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from a managed computer. Do one of the following:<br /><br />To enable script scanning from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], open the **Policy** workspace and change the **Enable script scanning** setting to **Yes** in the policies that apply to the computer.<br /><br />Or,<br /><br />to enable script scanning from a managed computer, start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the notification area. Click the **Settings** tab, click **Real-time protection**, select the **Enable script scanning** check box, and then click **Save changes**.|
|**Network Inspection System disabled**|The Network Inspection System was disabled by an administrator using policy or by a user on a managed computer.|If Network Inspection System is disabled, you can enable it from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from a managed computer. Do one of the following:<br /><br />To enable Network Inspection System from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)], open the **Policy** workspace, change the **Enable Network Inspection System** setting to **Yes** in the policies that apply to the computer, and then restart the managed computer.<br /><br />Or,<br /><br />to enable Network Inspection System from a managed computer, start the [!INCLUDE[epshort](../Token/epshort_md.md)] client software from the notification area. Click the **Settings** tab, click **Real-time protection**, select the **Enable Network Inspection System** check box, and then click **Save changes**. Restart the computer.|
|**Malware definitions out-of-date**|The computer might have been disconnected from the Internet for an extended period of time, and its malware definitions might not yet have been updated. This status appears when the malware definitions on the computer are out-of-date by 14 days or more.|If malware definitions are out-of-date, you can update the definitions from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] or from the managed computer.<br /><br />For more information, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md) topic.|
|**Full scan overdue**|A full scan has not been completed for 14 days. This can be caused by a computer restart during a full scan.|If a full scan is overdue, you can run a one-time full scan or schedule recurring full scans from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] by using the information in the topic [Common Windows PC management tasks with the Microsoft Intune computer client](../Topic/Common-Windows-PC-management-tasks-with-the-Microsoft-Intune-computer-client.md).|
|**Quick scan overdue**|A quick scan has not been completed for 14 days. This can be caused by a restart during a quick scan.|If a quick scan is overdue, you can run a one-time quick scan or schedule recurring quick scans from the [!INCLUDE[wit_adminconsole](../Token/wit_adminconsole_md.md)] by using the information in the topic [Common Windows PC management tasks with the Microsoft Intune computer client](../Topic/Common-Windows-PC-management-tasks-with-the-Microsoft-Intune-computer-client.md).|
|**Another endpoint protection application running**|Another endpoint protection application is running, and the computer is healthy.|By default, if another endpoint protection application is installed and [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] detects that application, [!INCLUDE[epshort](../Token/epshort_md.md)] automatically disables itself. If [!INCLUDE[wit_nextref](../Token/wit_nextref_md.md)] does not detect the other endpoint application, [!INCLUDE[epshort](../Token/epshort_md.md)] will remain enabled. For more information, see [Help secure Windows PCs with Endpoint Protection for Microsoft Intune](../Topic/Help-secure-Windows-PCs-with-Endpoint-Protection-for-Microsoft-Intune.md).|

## See Also
[Troubleshoot Microsoft Intune](../Topic/Troubleshoot-Microsoft-Intune.md)
[Manage Windows PCs with Microsoft Intune](../Topic/Manage-Windows-PCs-with-Microsoft-Intune.md)
