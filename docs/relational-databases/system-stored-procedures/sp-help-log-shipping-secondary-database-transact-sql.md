---
title: sp_help_log_shipping_secondary_database (TRANSACT-SQL) |Microsoft 文档
ms.custom: ''
ms.date: 08/02/2016
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- sp_help_log_shipping_secondary_database
- sp_help_log_shipping_secondary_database_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_help_log_shipping_secondary_database
ms.assetid: 11ce42ca-d3f1-44c8-9cac-214ca8896b9a
caps.latest.revision: 28
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 41799f0699fc85e23ea261b8b70593844f89fdbd
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sphelplogshippingsecondarydatabase-transact-sql"></a>sp_help_log_shipping_secondary_database (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  此存储过程可检索一个或多个辅助数据库的设置。  
  

  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_help_log_shipping_secondary_database  
[ @secondary_database = ] 'secondary_database' OR  
[ @secondary_id = ] 'secondary_id'  
```  
  
## <a name="arguments"></a>参数  
 [  **@secondary_database =** ]*secondary_database*  
 辅助数据库的名称。 *secondary_database*是**sysname**，无默认值。  
  
 [ **@secondary_id =** ] '*secondary_id*'  
 日志传送配置中辅助服务器的 ID。 *secondary_id*是**uniqueidentifier**和不能为 NULL。  
  
## <a name="return-code-values"></a>返回代码值  
 0（成功）或 1（失败）  
  
## <a name="result-sets"></a>结果集  
  
|列名|Description|  
|-----------------|-----------------|  
|**secondary_id**|日志传送配置中辅助服务器的 ID。|  
|**primary_server**|主实例的名称[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]日志传送配置中。|  
|**primary_database**|日志传送配置中主数据库的名称。|  
|**backup_source_directory**|存储主服务器的事务日志备份文件的目录。|  
|**backup_destination_directory**|备份文件复制到的辅助服务器上的目录。|  
|**file_retention_period**|备份文件被删除之前在辅助服务器上保留的时间（以分钟为单位）。|  
|**copy_job_id**|与辅助服务器上的复制作业关联的 ID。|  
|**restore_job_id**|与辅助服务器上的还原作业关联的 ID。|  
|**monitor_server**|在日志传送配置中用作监视服务器的 [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] 实例的名称。|  
|**monitor_server_security_mode**|用于连接到监视服务器的安全模式。<br /><br /> 1 = [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows 身份验证。<br /><br /> 0 =[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]身份验证。|  
|**secondary_database**|日志传送配置中辅助数据库的名称。|  
|**restore_delay**|辅助服务器在还原给定备份文件之前等待的时间（分钟）。 默认为 0 分钟。|  
|**restore_all**|如果设置为 1，则在运行还原作业时，辅助服务器将还原所有可用的事务日志备份。 否则，在原还了一个文件之后它将停止。|  
|**restore_mode**|辅助数据库的还原模式。<br /><br /> 0 = with NORECOVERY 还原日志。<br /><br /> 1 = 使用 STANDBY 还原日志。|  
|**disconnect_users**|如果设置为 1，则在执行还原操作时，会断开用户与辅助数据库的连接。 默认值 = 0。|  
|**block_size**|用作备份设备的块大小（字节）。|  
|**buffer_count**|备份或还原操作使用的缓冲区总数。|  
|**max_transfer_size**|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 向备份设备发出的最大输入或输出请求的大小（字节）。|  
|**restore_threshold**|两次还原操作之间允许的间隔时间（分钟），一旦超过此值，就会生成警报。|  
|**threshold_alert**|超过还原阈值时引发的警报。|  
|**threshold_alert_enabled**|确定是否启用了还原阈值警报。<br /><br /> 1 = 已启用。<br /><br /> 0 = 禁用。|  
|**last_copied_file**|上次复制到辅助服务器的备份文件的文件名。|  
|**last_copied_date**|上次复制到辅助服务器的时间和日期。|  
|**last_copied_date_utc**|上次对辅助服务器执行复制操作的时间和日期，以通用协调时间表示。|  
|**last_restored_file**|上次还原到辅助数据库的备份文件的文件名。|  
|**last_restored_date**|上次对辅助数据库执行还原操作的时间和日期。|  
|**last_restored_date_utc**|上次对辅助数据库执行还原操作的时间和日期，以通用协调时间表示。|  
|**history_retention_period**|日志传送历史记录在删除前保留在给定辅助数据库中的时间（分钟）。|  
|**last_restored_latency**|在主数据库上创建日志备份的时间与在辅助数据库上还原日志备份的时间间隔（分钟）。<br /><br /> 初始值为 NULL。|  
  
## <a name="remarks"></a>注释  
 如果包含*secondary_database*参数，如果包含，结果集将包含有关该辅助数据库; 信息*secondary_id*结果集将包含参数，与该辅助 id。 关联的所有辅助数据库的相关信息  
  
 **sp_help_log_shipping_secondary_database**必须从运行**master**辅助服务器上的数据库。  
  
## <a name="permissions"></a>权限  
 只有的成员**sysadmin**固定的服务器角色可以运行此过程。  
  
## <a name="see-also"></a>另请参阅  
 [sp_help_log_shipping_secondary_primary &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-help-log-shipping-secondary-primary-transact-sql.md)   
 [有关日志传送 & #40;SQL server& #41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
