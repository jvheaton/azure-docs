---
title: We're retiring classic storage accounts on August 31, 2024
titleSuffix: Azure Storage
description: Overview of migration of classic storage accounts to the Azure Resource Manager deployment model. All classic accounts must be migrated by August 31, 2024.
services: storage
author: tamram

ms.service: storage
ms.topic: conceptual
ms.date: 04/10/2023
ms.author: tamram
ms.subservice: common
---

# Migrate your classic storage accounts to Azure Resource Manager by August 31, 2024

The [Azure Resource Manager](../../azure-resource-manager/management/overview.md) deployment model now offers extensive functionality for Azure Storage accounts. For this reason, we deprecated the management of classic storage accounts through Azure Service Manager (ASM) on August 31, 2021. Classic storage accounts will be fully retired on August 31, 2024. All data in classic storage accounts must be migrated to Azure Resource Manager storage accounts by that date.

If you have classic storage accounts, start planning your migration now. Complete it by August 31, 2024, to take advantage of Azure Resource Manager. To learn more about the benefits of Azure Resource Manager, see [The benefits of using Resource Manager](../../azure-resource-manager/management/overview.md#the-benefits-of-using-resource-manager).

Storage accounts created using the classic deployment model will follow the [Modern Lifecycle Policy](https://support.microsoft.com/help/30881/modern-lifecycle-policy) for retirement.

## Why is a migration required?

On August 31, 2024, we'll retire classic Azure storage accounts and they'll no longer be accessible. Before that date, you'll need to migrate them to Azure Resource Manager, which provides the same capabilities as well as new features, including:

- A management layer that simplifies deployment by enabling you to create, update, and delete resources.
- Resource grouping, which allows you to deploy, monitor, manage, and apply access control policies to resources as a group.
- All new features for Azure Storage are implemented for storage account in Azure Resource Manager deployments, so customers that are still using classic resources will no longer have access to new features and updates.

## How does this affect me?

On September 1, 2024, customers will no longer be able to connect to classic storage accounts by using Azure Service Manager. Any data still contained in these accounts will no longer be accessible through Azure Service Manager.

> [!WARNING]
> If you do not migrate your classic storage accounts to Azure Resource Manager by August 31, 2024, you will permanently lose access to the data in those accounts.

Depending on when your subscription was created, you may no longer to be able to create classic storage accounts:

- Subscriptions created after August 31, 2022 can no longer create classic storage accounts.
- Subscriptions created before September 1, 2022 will be able to create classic storage accounts until September 1, 2023

We recommend creating storage accounts only in Azure Resource Manager from this point forward.

## What actions should I take?

To migrate your classic storage accounts, you should:

1. Identify all classic storage accounts in your subscription.
1. Migrate any classic storage accounts to Azure Resource Manager.
1. Check your applications and logs to determine whether you are dynamically creating, updating, or deleting classic storage accounts from your code, scripts, or templates. If you are, then you need to update your applications to use Azure Resource Manager accounts instead.

For step-by-step instructions, see [How to migrate your classic storage accounts to Azure Resource Manager](classic-account-migrate.md). For an in-depth overview of the migration process, see [Understand storage account migration from the classic deployment model to Azure Resource Manager](classic-account-migration-process.md).

## How to get help

- If you have questions, get answers from community experts in [Microsoft Q&A](/answers/tags/98/azure-storage-accounts).
- If your organization or company has partnered with Microsoft or works with Microsoft representatives, such as cloud solution architects (CSAs) or customer success account managers (CSAMs), contact them for additional resources for migration.
- If you have a support plan and you need technical help, create a support request in the Azure portal:

    1. Search for **Help + support** in the [Azure portal](https://portal.azure.com#view/Microsoft_Azure_Support/HelpAndSupportBlade/~/overview).
    1. Select **Create a support request**.
    1. Under **Summary**, type a description of your issue.
    1. Under **Issue type**, select **Technical**.
    1. Under **Subscription**, select your subscription.
    1. Under **Service**, select **My services**.
    1. Under **Service type**, select **Storage Account Management**.
    1. Under **Resource**, select the resource you want to migrate.
    1. Under **Problem type**, select **Data Migration**.
    1. Under **Problem subtype**, select **Migrate account to new resource group/subscription/region/tenant**.
    1. Select **Next**, then follow the instructions to submit your support request.

## FAQ

### How do I migrate my classic storage accounts to Resource Manager?

For step-by-step instructions for migrating your classic storage accounts, see [How to migrate your classic storage accounts to Azure Resource Manager](classic-account-migrate.md). For an in-depth overview of the migration process, see [Understand storage account migration from the classic deployment model to Azure Resource Manager](classic-account-migration-process.md).

### At what point can classic storage accounts no longer be created?

Subscriptions created after August 2022 are no longer be able to create classic storage accounts. Subscriptions created before August 2022 can continue to create and manage classic storage resources until the retirement date of August 31, 2024.

### What happens to existing classic storage accounts after August 31, 2024?

After August 31, 2024, you will no longer be able to access data in your classic storage accounts or manage them. It won't be possible to migrate a classic storage account after August 31, 2024.

### Can Microsoft handle this migration for me?

No, Microsoft cannot migrate a customer's storage account on their behalf. Customers must use the self-serve options listed above.

### Will there be downtime when migrating my storage account from Classic to Resource Manager?

There is no downtime to migrate a classic storage account to Resource Manager. However, there is downtime for other scenarios linked to classic virtual machine (VM) migration.

### What operations are not available during the migration?

Also, during the migration, management operations are not available on the storage account. Data operations can continue to be performed during the migration.

If you are creating or managing container objects with the Azure Storage resource provider, note that those operations will be blocked while the migration is underway. For more information, see [Understand storage account migration from the classic deployment model to Azure Resource Manager](classic-account-migration-process.md).

### Are storage account access keys regenerated as part of the migration?

No, account access keys are not regenerated during the migration. Your access keys and connection strings will continue to work unchanged after the migration is complete.

### Are Azure RBAC role assignments maintained through the migration?

Any RBAC role assignments that are scoped to the classic storage account are maintained after the migration.

### What type of storage account is created by the migration process?

Your storage account will be a general-purpose v1 account after the migration process completes. You can then upgrade it to general-purpose v2. For more information about upgrading your account, see [Upgrade to a general-purpose v2 storage account](storage-account-upgrade.md).

### Will the URL of my storage account remain the same post-migration?

Yes, the migrated storage account will have the same name and address as the classic account.

### Can additional verbose logging be added as part of the migration process?

No, migration is a service that doesn't have capabilities to provide additional logging.

## See also

- [How to migrate your classic storage accounts to Azure Resource Manager](classic-account-migrate.md)
- [Understand storage account migration from the classic deployment model to Azure Resource Manager](classic-account-migration-process.md)
