---
title: "迁移触发器 | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: in-memory-oltp
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine-imoltp
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad5385c5-5a50-40ca-a319-97d5606b8511
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a2f151fa00c2e92ef1509ea2c6d7d93e8c8d2c69
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="migrating-triggers"></a>迁移触发器
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]

  本主题论述 DDL 触发器以及内存优化表。  
  
 DML 触发器在内存优化表中受支持，但仅适用于 FOR | AFTER 触发器事件。 有关示例，请参阅 [执行包含 FROM 或子查询的 UPDATE](../../relational-databases/in-memory-oltp/implementing-update-with-from-or-subqueries.md)。 
  
 LOGON 触发器是定义为对 LOGON 事件触发的触发器。 LOGON 触发器不会影响内存优化表。  
  
## <a name="ddl-triggers"></a>DDL 触发器  
 DDL 触发器定义为在对其定义的数据库或服务器上执行 CREATE、ALTER、DROP、GRANT、DENY、REVOKE 或 UPDATE STATISTICS 语句时触发的触发器。  
  
 如果数据库或服务器具有对 CREATE_TABLE 或者包含它的任何事件组定义的一个或多个 DDL 触发器，则不能创建内存优化表。 如果数据库或服务器具有对 DROP_TABLE 或者包含它的任何事件组定义的一个或多个 DDL 触发器，则不能删除内存优化表。  
  
 如果对 CREATE_PROCEDURE、DROP_PROCEDURE 或包含这些事件的任何事件组有一个或多个 DDL 触发器，则不能创建本机编译的存储过程。  
  
## <a name="see-also"></a>另请参阅  
 [迁移到内存中 OLTP](../../relational-databases/in-memory-oltp/migrating-to-in-memory-oltp.md)  
  
  
