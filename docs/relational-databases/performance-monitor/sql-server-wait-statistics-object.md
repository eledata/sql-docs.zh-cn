---
title: "SQL Server - Wait Statistics 对象 | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: performance-monitor
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Wait Statistics object
- SQLServer:Wait Statistics
ms.assetid: cb7f917d-4291-4115-9b78-ee7692ebbb2d
caps.latest.revision: 
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 86fed40dbd12e7124aa837b7e428af711e33ef24
ms.sourcegitcommit: dcac30038f2223990cc21775c84cbd4e7bacdc73
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
---
# <a name="sql-server-wait-statistics-object"></a>SQL Server Wait Statistics 对象
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]“SQLServer:Wait Statistics”性能对象包含报告有关等待状态的性能计数器。  
  
 下表列出了 Wait Statistics 对象包含的计数器。  
  
|SQL Server Wait Statistics 计数器|Description|  
|-----------------------------------------|-----------------|  
|**Lock waits**|等待锁的进程的统计信息。|  
|**Log buffer waits**|等待日志缓冲区可用的进程的统计信息。|  
|**Log write waits**|等待写入日志缓冲区的进程的统计信息。|  
|**Memory grant queue waits**|等待内存授予的进程的统计信息。|  
|**Network IO waits**|与等待网络 I/O 相关的统计信息。|  
|**Non-Page latch waits**|与非页闩锁相关的统计信息。|  
|**Page IO latch waits**|与页 I/O 闩锁相关的统计信息。|  
|**Page latch waits**|与页闩锁（不包括 I/O 闩锁）相关的统计信息。|  
|**Thread-safe memory objects waits**|等待线程安全内存分配器的进程的统计信息。|  
|**Transaction ownership waits**|与同步访问事务的进程相关的统计信息。|  
|**Wait for the worker**|与等待工作线程变得可用的进程相关的统计信息。|  
|**Workspace synchronization waits**|与同步访问工作空间的进程相关的统计信息。|  
  
 对象中的每个计数器均包含以下实例：  
  
|项|Description|  
|----------|-----------------|  
|**平均等待时间(ms)**|所选类型等待的平均等待时间。|  
|**每秒的累积等待时间(ms)**|所选类型等待的每秒累积等待时间。|  
|**正在进行的等待数**|当前正在等待的以下类型的进程数。|  
|**每秒启动的等待数**|每秒启动的所选类型等待的等待数。|  
  
## <a name="see-also"></a>另请参阅  
 [监视资源使用情况（系统监视器）](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  
