---
title: "配置实用工具控制点数据仓库（SQL Server 实用工具）| Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: maintenance-plans
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2c6f050-8cdb-4b8e-ad38-4aae0a949847
caps.latest.revision: 
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f4be33b398d7225125c68fadcdca5e334a309788
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
---
# <a name="configure-your-utility-control-point-data-warehouse-sql-server-utility"></a>配置您的实用工具控制点数据仓库（SQL Server 实用工具）
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的托管实例收集的数据存储在实用工具管理数据仓库 (UMDW) 中；UMDW 文件名为 sysutility_mdw。  
  
 您可以配置 UMDW 数据保持期。 有关详细信息，请参阅[实用工具管理（SQL Server 实用工具）](http://msdn.microsoft.com/library/3e5a00c3-8905-40f0-9ddc-d924df9c2f0d)。  
  
 以下配置设置在此版本的 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 中不可配置：  
  
-   UMDW 名称：Sysutility_mdw。  
  
-   收集组上载频率：每隔 15 分钟。  
  
 UMDW 目录是可配置的：\<System drive>:\Program Files\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\，其中，\<System drive> 通常为 C:\ 驱动器。 日志文件 Sysutility_mdw_\<GUID>_LOG 位于同一目录中。  
  
> [!NOTE]  
>  可以使用 detach/attach 或 ALTER DATABASE 更改该 UMDW (sysutility_mdw) 文件位置。 我们建议使用 ALTER DATABASE。 有关详细信息，请参阅 [ALTER DATABASE (Transact-SQL)](../../t-sql/statements/alter-database-transact-sql.md)。  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server 实用工具的功能和任务](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)  
  
  
