---
title: Ole Automation Procedures 服务器配置选项 | Microsoft Docs
ms.custom: ''
ms.date: 03/02/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: ''
ms.component: configure-windows
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Ole Automation Procedures option
ms.assetid: e8982e05-4984-4406-9760-285e8c028ddf
caps.latest.revision: 20
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 9c07b72afe8e30cb1241f1b4ece8cccd82a2924b
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
---
# <a name="ole-automation-procedures-server-configuration-option"></a>Ole Automation Procedures 服务器配置选项
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

  使用 **Ole Automation Procedures** 选项可指定是否可以在 [!INCLUDE[tsql](../../includes/tsql-md.md)] 批处理中实例化 OLE Automation 对象。 还可以使用基于策略的管理或者 **sp_configure** 存储过程来配置这一选项。 有关详细信息，请参阅 [Surface Area Configuration](../../relational-databases/security/surface-area-configuration.md)。  
  
 可以将 **Ole Automation Procedures** 选项设置为以下值。  
  
 0  
 禁用 OLE Automation Procedures。 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]新实例的默认值。  
  
 @shouldalert  
 启用 OLE Automation Procedures。  
  
 当启用 OLE Automation Procedures 时，对 **sp_OACreate** 的调用将会启动 OLE 共享执行环境。  
  
 可以使用 **sp_configure** 系统存储过程来查看和更改 **Ole Automation Procedures** 选项的当前值。  
  
## <a name="examples"></a>示例  
 以下示例显示了如何查看 OLE Automation Procedures 的当前设置。  
  
```  
EXEC sp_configure 'Ole Automation Procedures';  
GO  
```  
  
 以下示例显示了如何启用 OLE Automation Procedures。  
  
```  
sp_configure 'show advanced options', 1;  
GO  
RECONFIGURE;  
GO  
sp_configure 'Ole Automation Procedures', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [sp_configure &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md)   
 [RECONFIGURE (Transact-SQL)](../../t-sql/language-elements/reconfigure-transact-sql.md)   
 [外围应用配置器](../../relational-databases/security/surface-area-configuration.md)   
 [服务器配置选项 (SQL Server)](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
  
