---
title: sysmail_delete_log_sp (TRANSACT-SQL) |Microsoft 文档
ms.custom: ''
ms.date: 06/10/2016
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
- sysmail_delete_log_sp_TSQL
- sysmail_delete_log_sp
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_delete_log_sp
ms.assetid: e94b37a1-70ad-46a5-86c0-721892156f7c
caps.latest.revision: 15
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b6af0845ec009297b2395276c07b2d6af01a2fda
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sysmaildeletelogsp-transact-sql"></a>sysmail_delete_log_sp (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  从数据库邮件日志中删除事件。 删除日志中的所有事件或删除符合某一日期或类型条件的那些事件。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sysmail_delete_log_sp  [ [ @logged_before = ] 'logged_before' ]  
    [, [ @event_type = ] 'event_type' ]  
  
```  
  
## <a name="arguments"></a>参数  
 [ **@logged_before** =] *****logged_before*****  
 删除条目最多的日期和时间指定*logged_before*自变量。 *logged_before*是**datetime**替换为默认值为 NULL。 NULL 指示所有日期。  
  
 [ **@event_type** = ] **'***event_type***'**  
 删除日志条目指定为的类型的*event_type*。 *event_type*是**varchar(15)**无默认值。 有效值包括**成功**，**警告**，**错误**，和**条信息性**。 NULL 指示所有事件类型。  
  
## <a name="return-code-values"></a>返回代码值  
 **0** （成功） 或**1** （失败）  
  
## <a name="remarks"></a>注释  
 使用**sysmail_delete_log_sp**存储过程来从数据库邮件日志中永久删除条目。 某个可选参数通过提供日期和时间，允许您仅删除较早的记录。 早于该参数的事件将被删除。 可选参数，可删除仅事件的特定类型，指定为**event_type**自变量。  
  
 删除数据库邮件日志中的项不会从数据库邮件表中删除电子邮件项。 使用[sysmail_delete_mailitems_sp](../../relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql.md)从数据库邮件表中删除电子邮件。  
  
## <a name="permissions"></a>权限  
 只有的成员**sysadmin**固定的服务器角色可以访问此过程。  
  
## <a name="examples"></a>示例  
  
### <a name="a-deleting-all-events"></a>A. 删除所有事件  
 以下示例删除数据库邮件日志中的所有事件。  
  
```  
EXECUTE msdb.dbo.sysmail_delete_log_sp ;  
GO  
```  
  
### <a name="b-deleting-the-oldest-events"></a>B. 删除最早的事件  
 以下示例删除数据库邮件日志中 2005 年 10 月 9 日之前的事件。  
  
```  
EXECUTE msdb.dbo.sysmail_delete_log_sp  
    @logged_before = 'October 9, 2005' ;  
GO  
```  
  
### <a name="c-deleting-all-events-of-a-certain-type"></a>C. 删除特定类型的所有事件  
 以下示例删除数据库邮件日志中的成功消息。  
  
```  
EXECUTE msdb.dbo.sysmail_delete_log_sp  
    @event_type = 'success' ;  
GO  
```  
  
## <a name="see-also"></a>另请参阅  
 [sysmail_event_log &#40;Transact SQL&#41;](../../relational-databases/system-catalog-views/sysmail-event-log-transact-sql.md)   
 [sysmail_delete_mailitems_sp &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql.md)   
 [创建 SQL Server 代理作业以存档数据库邮件和事件日志](../../relational-databases/database-mail/create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)  
  
  
