---
title: 'Authorize calls for users in a dial plan: Exchange 2013 Help'
TOCTitle: Authorize calls for users in a dial plan
ms.author: serdars
author: msdmaguire
manager: serdars
ms.topic: article
ms.reviewer:
description: How to enable dialing authorizations on a Unified Messaging dial plan
ms.assetid: 7c7fd0c4-4001-408e-b352-c49bac9f78cc
f1.keywords:
- NOCSH
mtps_version: v=EXCHG.150
---

# Authorize calls for users in a dial plan in Exchange Server

_**Applies to:** Exchange Server 2013, Exchange Server 2016_

You can enable dialing authorizations on a Unified Messaging (UM) dial plan. Dialing authorizations on a dial plan are used to prohibit unauthenticated Outlook Voice Access users from making in-country/region or international telephone calls, or outdialing. Outdialing happens when Unified Messaging places an outgoing call for a user after they've called in to an Outlook Voice Access phone number that is configured on a UM dial plan. When you configure a setting on a UM dial plan, that setting applies to all unauthenticated users that call in to an Outlook Voice Access number.

For additional management tasks related to outdialing, see [Allowing users to make calls procedures](allow-users-to-make-calls-procedures-exchange-2013-help.md).

## What do you need to know before you begin?

- Estimated time to complete: Less than 1 minute.

- You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "UM dial plans" entry in the [Unified Messaging permissions](unified-messaging-permissions-exchange-2013-help.md) topic.

- Before you perform these procedures, confirm that a UM dial plan has been created. For detailed steps, see [Create a UM dial plan](create-um-dial-plan-exchange-2013-help.md).

- Before you perform this procedure, confirm that in-country/region and international dialing rules have been created on a UM dial plan. For detailed steps, see [Create dialing rules for users](create-dialing-rules-exchange-2013-help.md).

- For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange 2013](keyboard-shortcuts-in-the-exchange-admin-center-2013-help.md).

> [!TIP]
> Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://social.technet.microsoft.com/forums/office/home?category=exchangeserver).

## Use the EAC to enable dialing authorizations on a UM dial plan for in-country/region dialing rule groups

1. In the EAC, navigate to **Unified Messaging** \> **UM dial plans**. In the list view, select the UM dial plan you want to change, and then click **Edit** ![Edit icon.](images/ITPro_EAC_EditIcon.gif).

2. On the **UM Dial Plan** page, click **Configure**.

3. On the **UM Dial Plan** page \> **Dialing authorization**, click **Add** ![Add Icon.](images/ITPro_EAC_AddIcon.gif) under **Authorized in-country/region dialing rule groups**.

4. On the **Select Dialing Rule Groups to Allow** page, select the dialing rule group, click **OK**, and then click **Save**.

## Use the EAC to enable dialing authorizations on a UM dial plan for international dialing rule groups

1. In the EAC, navigate to **Unified Messaging** \> **UM dial plans**. In the list view, select the UM dial plan you want to change, and then click **Edit** ![Edit icon.](images/ITPro_EAC_EditIcon.gif).

2. On the **UM Dial Plan** page, click **Configure**.

3. On the **UM Dial Plan** page \> **Dialing authorization**, click **Add** ![Add Icon.](images/ITPro_EAC_AddIcon.gif) under **Authorized international dialing rule groups**.

4. On the **Select Dialing Rule Groups to Allow** page, select the dialing rule group, click **OK**, and then click **Save**.

## Use the Shell to enable in-country/region and international dialing authorizations on a UM dial plan

This example enables the InCountry/RegionGroup1, InCountry/RegionGroup2, InternationalGroup1, and InternationalGroup2 dialing authorizations on a UM dial plan named `MyUMDialPlan`.

```powershell
Set-UMDialPlan -Identity MyUMDialPlan -AllowedInCountryOrRegionGroups InCountry/RegionGroup1,InCountry/RegionGroup2 -AllowedInternationalGroups InternationalGroup1,InternationalGroup2
```
