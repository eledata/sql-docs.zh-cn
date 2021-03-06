---
title: log_shipping_monitor_secondary (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
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
- log_shipping_monitor_secondary_TSQL
- log_shipping_monitor_secondary
dev_langs:
- TSQL
helpviewer_keywords:
- log_shipping_monitor_secondary system table
ms.assetid: afbe1bb7-89a7-4020-9408-0af64a043c2e
caps.latest.revision: 22
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 29e91437e94fc4eef4f5f65a96f28bb6b8772333
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="logshippingmonitorsecondary-transact-sql"></a>log_shipping_monitor_secondary (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  在日志传送配置中为每个辅助数据库存储一条监视记录。 此表存储在**msdb**数据库。  
  
 与历史记录和监视相关的表也用于主服务器和辅助服务器。  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**secondary_server**|**sysname**|辅助实例的名称[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]日志传送配置中。|  
|**secondary_database**|**sysname**|日志传送配置中辅助数据库的名称。|  
|**secondary_id**|**uniqueidentifier**|日志传送配置中辅助服务器的 ID。|  
|**primary_server**|**sysname**|日志传送配置中 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]主实例的名称。|  
|**primary_database**|**sysname**|日志传送配置中主数据库的名称。|  
|**restore_threshold**|**int**|两次还原操作之间允许的间隔时间（分钟），一旦超过此值，就会生成警报。|  
|**threshold_alert**|**int**|超过还原阈值时引发的警报。|  
|**threshold_alert_enabled**|**bit**|确定是否启用了还原阈值警报。 1 = 已启用。<br /><br /> 0 = 禁用。|  
|**last_copied_file**|**nvarchar(500)**|上次复制到辅助服务器的备份文件的文件名。|  
|**last_copied_date**|**datetime**|上次复制到辅助服务器的时间和日期。|  
|**last_copied_date_utc**|**datetime**|上次对辅助服务器执行复制操作的时间和日期，以通用协调时间表示。|  
|**last_restored_file**|**nvarchar(500)**|上次还原到辅助数据库的备份文件的文件名。|  
|**last_restored_date**|**datetime**|上次对辅助数据库执行还原操作的时间和日期。|  
|**last_restored_date_utc**|**datetime**|上次对辅助数据库执行还原操作的时间和日期，以通用协调时间表示。|  
|**last_restored_latency**|**int**|在主数据库上创建日志备份的时间与在辅助数据库上还原日志备份的时间间隔（分钟）。<br /><br /> 初始值为 NULL。|  
|**history_retention_period**|**int**|日志传送历史记录在删除前保留在给定辅助数据库中的时间（分钟）。|  
  
## <a name="remarks"></a>注释  
 除了存储上远程监视服务器上，并与辅助服务器相关的信息也存储在中的辅助服务器上其**log_shipping_monitor_secondary**表。  
  
## <a name="see-also"></a>另请参阅  
 [有关日志传送 & #40;SQL server& #41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [sp_refresh_log_shipping_monitor &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql.md)   
 [sp_add_log_shipping_secondary_database &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-add-log-shipping-secondary-database-transact-sql.md)   
 [sp_change_log_shipping_secondary_database &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-change-log-shipping-secondary-database-transact-sql.md)   
 [sp_delete_log_shipping_secondary_database &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql.md)   
 [sp_help_log_shipping_secondary_database &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-log-shipping-secondary-database-transact-sql.md)   
 [sp_help_log_shipping_monitor_secondary &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-log-shipping-monitor-secondary-transact-sql.md)   
 [sp_refresh_log_shipping_monitor &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-refresh-log-shipping-monitor-transact-sql.md)   
 [系统表 (Transact-SQL)](../../relational-databases/system-tables/system-tables-transact-sql.md)  
  
  
