---
title: dbo.sysnotifications (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-tables
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- dbo.sysnotifications_TSQL
- sysnotifications
- sysnotifications_TSQL
- dbo.sysnotifications
dev_langs:
- TSQL
helpviewer_keywords:
- sysnotifications system table
ms.assetid: c5150d18-e8b7-48a7-ada7-77c583af6e41
caps.latest.revision: 25
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 41b60c77633d96d109d0c9cecb33b5b19b53e0b0
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="dbosysnotifications-transact-sql"></a>dbo.sysnotifications (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  对每个通知包含一行。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**alert_id**|**int**|警报 ID。|  
|**operator_id**|**int**|应向其发送此通知的操作员 ID。|  
|**notification_method**|**tinyint**|通知方法：<br /><br /> **1** = 电子邮件<br /><br /> **2** = 页导航<br /><br /> **4** = **netsend**<br /><br /> **7** = all|  
  
  
