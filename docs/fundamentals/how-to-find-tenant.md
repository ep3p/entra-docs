---
title: How to find your tenant ID
description: Instructions about how to find and Microsoft Entra tenant ID to an existing Azure subscription.
author: barclayn
manager: amycolannino

ms.service: entra
ms.subservice: fundamentals
ms.topic: how-to
ms.date: 09/12/2023
ms.author: barclayn
ms.reviewer: jeffsta
ms.custom: it-pro
---
# How to find your Microsoft Entra tenant ID

Azure subscriptions have a trust relationship with Microsoft Entra ID. Microsoft Entra ID is trusted to authenticate the subscription's users, services, and devices. Each subscription has a tenant ID associated with it, and there are a few ways you can find the tenant ID for your subscription.

## Find tenant ID through the Microsoft Entra admin center

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com) as at least a [Global Reader](~/identity/role-based-access-control/permissions-reference.md#global-reader).
1. Browse to **Identity** > **Overview** > **Properties**.

   :::image type="content" source="media/how-to-find-tenant/identity-overview-properties.png" alt-text="Microsoft Entra ID - Identity Properties overview":::

1. Scroll down to the **Tenant ID** section and you can find your tenant ID in the box.

<!-- docutune:disable -->
## Find tenant ID through the Azure portal
 
1. Sign in to the [Azure portal](https://portal.azure.com).
1. Browse to **Microsoft Entra ID** > **Properties**.
1. Scroll down to the **Tenant ID** section and you can find your tenant ID in the box.

   :::image type="content" source="media/how-to-find-tenant/portal-tenant-id.png" alt-text="Microsoft Entra ID - Properties - Tenant ID - Tenant ID field":::
<!-- docutune:enable -->

## Find tenant ID with PowerShell

To find the tenant ID with Azure PowerShell, use the cmdlet `Get-AzTenant`.

```azurepowershell-interactive
Connect-AzAccount
Get-AzTenant
```
   
For more information, see the [Get-AzTenant](/powershell/module/az.accounts/get-aztenant) cmdlet reference.


## Find tenant ID with CLI

The [Azure CLI](/cli/azure/install-azure-cli) or [Microsoft 365 CLI](https://github.com/pnp/cli-microsoft365) can be used to find the tenant ID.

For Azure CLI, use one of the commands **az login**, **az account list**, or **az account tenant list**. All of command's included below return the **tenantId** property for each of your subscriptions.

```azurecli-interactive
az login
az account list
az account tenant list
```

For more information, see [az login](/cli/azure/reference-index#az-login) command reference, [az account](/cli/azure/account) command reference, or [az account tenant](/cli/azure/account/tenant) command reference.


For Microsoft 365 CLI, use the cmdlet **tenant id** as shown in the following example:
 
```cli
m365 tenant id get
```

## Next steps

- To create a new Microsoft Entra tenant, see [Quickstart: Create a new tenant in Microsoft Entra ID](./create-new-tenant.md).

- To learn how to associate or add a subscription to a tenant, see [Associate or add an Azure subscription to your Microsoft Entra tenant](./how-subscriptions-associated-directory.md).

- To learn how to find the object ID, see [Find the user object ID](/partner-center/find-ids-and-domain-names#find-the-user-object-id).
