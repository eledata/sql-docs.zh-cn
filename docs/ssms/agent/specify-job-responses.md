---
title: 指定作业响应 | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: ''
ms.component: ssms-agent
ms.reviewer: ''
ms.suite: sql
ms.technology:
- tools-ssms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- jobs [SQL Server Agent], responses
- SQL Server Agent jobs, responses
- actions [SQL Server Agent jobs]
- responding to jobs
ms.assetid: 050242e1-9b79-4ade-91a9-580707b9d2d9
caps.latest.revision: ''
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a8e643aee82c69eb3acba9e99126229135475baf
ms.sourcegitcommit: 34766933e3832ca36181641db4493a0d2f4d05c6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="specify-job-responses"></a>指定作业响应
[!INCLUDE[appliesto-ss-asdbmi-xxxx-xxx-md](../../includes/appliesto-ss-asdbmi-xxxx-xxx-md.md)]

> [!IMPORTANT]  
> [Azure SQL 数据库托管实例](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance)目前支持大多数但并非所有 SQL Server 代理功能。 有关详细信息，请参阅 [Azure SQL 数据库托管实例与 SQL Server 之间的 T-SQL 差异](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent)。

作业响应指定完成作业后 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 代理服务将执行的操作。 作业响应可确保数据库管理员知道作业完成的时间和作业运行频率。 典型的作业响应包括：  
  
-   使用电子邮件、电子寻呼或 **net send** 消息通知操作员。  
  
    如果操作员必须执行后续操作，应使用其中的某种作业响应。 例如，当一个备份作业成功地完成之后，必须通知操作员取出备份磁带并将其存放在安全处。  
  
-   将事件消息写入 Windows 应用程序日志。  
  
    只能对失败的作业使用这种响应。  
  
-   自动删除作业。  
  
    如果确信不需要再次运行该作业，可以使用这种作业响应。  
  
## <a name="related-tasks"></a>Related Tasks  
  
|||  
|-|-|  
|**Description**|**主题**|  
|描述如何向操作员通知作业状态。|[Notify an Operator of Job Status](../../ssms/agent/notify-an-operator-of-job-status.md)|  
|介绍如何将作业状态写入 Windows 应用程序日志。|[Write the Job Status to the Windows Application Log](../../ssms/agent/write-the-job-status-to-the-windows-application-log.md)|  
  
## <a name="see-also"></a>另请参阅  
[监视事件和响应事件](../../ssms/agent/monitor-and-respond-to-events.md)  
  
