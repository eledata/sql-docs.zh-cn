---
title: sys.service_contracts (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-catalog-views
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- service_contracts_TSQL
- sys.service_contracts_TSQL
- sys.service_contracts
- service_contracts
dev_langs:
- TSQL
helpviewer_keywords:
- sys.service_contracts catalog view
ms.assetid: 787dd47e-4210-439d-9c4a-57a727a0dbd8
caps.latest.revision: 30
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 334c6c1a5fc52ce40604a4f64599899e1f53744e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysservicecontracts-transact-sql"></a>sys.service_contracts (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  在此目录视图中，数据库中的每个约定对应一行。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**名称**|**sysname**|约定名称，在数据库中唯一。 不可为 NULL。|  
|**service_contract_id**|**int**|约定标识符。 不可为 NULL。|  
|**principal_id**|**int**|拥有此约定的数据库主体的标识符。 可以为 NULL。|  
  
## <a name="permissions"></a>权限  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] 有关详细信息，请参阅 [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md)。  
  
  
