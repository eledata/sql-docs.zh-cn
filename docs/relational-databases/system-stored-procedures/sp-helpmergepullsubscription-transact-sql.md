---
title: sp_helpmergepullsubscription (Transact SQL) |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.service: ''
ms.component: system-stored-procedures
ms.reviewer: ''
ms.suite: sql
ms.technology:
- replication
ms.tgt_pltfrm: ''
ms.topic: language-reference
applies_to:
- SQL Server
f1_keywords:
- sp_helpmergepullsubscription
- sp_helpmergepullsubscription_TSQL
helpviewer_keywords:
- sp_helpmergepullsubscription
ms.assetid: 6f3125f3-0dfa-40bd-b725-8aa1591234f6
caps.latest.revision: 30
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2c2a84992bdc1cce94bdc997ce017825c0a2fb8e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sphelpmergepullsubscription-transact-sql"></a>sp_helpmergepullsubscription (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回有关订阅服务器中存在的请求订阅的信息。 此存储过程在订阅服务器的订阅数据库中执行。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
sp_helpmergepullsubscription [ [ @publication=] 'publication']  
    [ , [ @publisher=] 'publisher']  
    [ , [ @publisher_db=] 'publisher_db']  
    [ , [ @subscription_type=] 'subscription_type']  
```  
  
## <a name="argument"></a>参数  
 [ **@publication=**] **'***publication***'**  
 发布的名称。 *发布*是**sysname**，默认值为**%**。 如果*发布*是**%**，返回有关所有合并发布和订阅当前数据库中的信息。  
  
 [ **@publisher=**] **'***publisher***'**  
 发布服务器的名称。 *发布服务器*是**sysname**，默认值为**%**。  
  
 [ **@publisher_db=**] **'***publisher_db***'**  
 发布服务器数据库的名称。 *publisher_db*是**sysname**，默认值为**%**。  
  
 [  **@subscription_type=**] *****subscription_type*****  
 指示是否显示请求订阅。 *subscription_type*是**nvarchar(10)**，默认值为**'pull'**。 有效值为**'push'**， **'pull'**，或**'both'**。  
  
## <a name="result-sets"></a>结果集  
  
|列名|数据类型|Description|  
|-----------------|---------------|-----------------|  
|**subscription_name**|**nvarchar(1000)**|订阅的名称。|  
|**发布**|**sysname**|发布的名称。|  
|**publisher**|**sysname**|发布服务器的名称。|  
|**publisher_db**|**sysname**|发布服务器数据库名。|  
|**订阅服务器**|**sysname**|订阅服务器的名称。|  
|**subscription_db**|**sysname**|订阅数据库的名称。|  
|**status**|**int**|订阅状态：<br /><br /> **0** = 不活动的订阅<br /><br /> **1** = 有效的订阅<br /><br /> **2** = 已删除订阅<br /><br /> **3** = 分离的订阅<br /><br /> **4** = 附加订阅<br /><br /> **5** = 订阅已标记为要重新初始化与上载<br /><br /> **6** = 的附加订阅失败<br /><br /> **7** = 从备份中还原的订阅|  
|**subscriber_type**|**int**|订阅服务器的类型：<br /><br /> **1** = 全局<br /><br /> **2** = 本地<br /><br /> **3** = 匿名|  
|**subscription_type**|**int**|订阅的类型：<br /><br /> **0** = 推送<br /><br /> **1** = 请求<br /><br /> **2** = 匿名|  
|**priority**|**float(8)**|订阅优先级。 值必须小于**100.00**。|  
|**sync_type**|**tinyint**|订阅同步类型：<br /><br /> **1** = automatic<br /><br /> **2** = 不使用快照。|  
|**说明**|**nvarchar(255)**|对请求订阅的简短说明。|  
|**merge_jobid**|**binary(16)**|合并代理的作业 ID。|  
|**enabled_for_syncmgr**|**int**|指示是否可以通过 [!INCLUDE[msCoName](../../includes/msconame-md.md)] 同步管理器同步订阅。|  
|**last_updated**|**nvarchar(26)**|合并代理上次成功同步订阅的时间。|  
|**publisher_login**|**sysname**|发布服务器登录名。|  
|**publisher_password**|**sysname**|发布服务器的密码。|  
|**publisher_security_mode**|**int**|指定发布服务器的安全模式：<br /><br /> **0**  =  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]身份验证<br /><br /> **1** = Windows 身份验证|  
|**分发服务器**|**sysname**|分发服务器的名称。|  
|**distributor_login**|**sysname**|分发服务器登录名。|  
|**distributor_password**|**sysname**|分发服务器密码。|  
|**distributor_security_mode**|**int**|指定分发服务器的安全模式：<br /><br /> **0**  =  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]身份验证<br /><br /> **1** = Windows 身份验证|  
|**ftp_address**|**sysname**|仅为向后兼容而提供。 是分发服务器的文件传输协议 (FTP) 服务的网络地址。|  
|**ftp_port**|**int**|仅为向后兼容而提供。 分发服务器 FTP 服务的端口号。|  
|**ftp_login**|**sysname**|仅为向后兼容而提供。 用于连接到 FTP 服务用户名。|  
|**ftp_password**|**sysname**|仅为向后兼容而提供。 用于连接到 FTP 服务的用户密码。|  
|**alt_snapshot_folder**|**nvarchar(255)**|存储快照文件夹的位置（如果该位置是默认位置以外的位置）。|  
|**working_directory**|**nvarchar(255)**|如果指定了使用 FTP 的选项，则是使用 FTP 将快照文件传输到的目录的完全限定路径。|  
|**use_ftp**|**bit**|订阅正通过 Internet 订阅发布，且已配置 FTP 寻址属性。 如果**0**，订阅未使用 FTP。 如果**1**，订阅使用的 FTP。|  
|**offload_agent**|**bit**|指定是否可以远程激活和运行代理。 如果**0**，代理不能远程激活。|  
|**offload_server**|**sysname**|用于远程激活的服务器的名称。|  
|**use_interactive_resolver**|**int**|返回在调节过程中是否使用交互式冲突解决程序。 如果**0**，不使用交互式冲突解决程序。|  
|**subid**|**uniqueidentifier**|订阅服务器的 ID。|  
|**dynamic_snapshot_location**|**nvarchar(255)**|保存快照文件的文件夹路径。|  
|**last_sync_status**|**int**|同步状态：<br /><br /> **1** = 启动<br /><br /> **2** = 成功<br /><br /> **3** = 正在进行<br /><br /> **4** = 空闲<br /><br /> **5** = 正在重试上一次失败后<br /><br /> **6** = 失败<br /><br /> **7** = 未通过验证<br /><br /> **8** = 通过验证<br /><br /> **9** = 请求关闭|  
|**last_sync_summary**|**sysname**|对上一次同步结果的说明。|  
|**use_web_sync**|**bit**|指定其中的一个值，是否可以通过 HTTPS 中, 同步订阅**1**意味着是否启用了此功能。|  
|**internet_url**|nvarchar(260)|表示 Web 同步复制侦听器的位置的 URL。|  
|**internet_login**|**nvarchar(128)**|在使用基本身份验证连接到承载 Web 同步的 Web 服务器时，合并代理所使用的登录名。|  
|**internet_password**|**nvarchar(524)**|在使用基本身份验证连接到承载 Web 同步的 Web 服务器时，合并代理所使用的登录密码。|  
|**internet_security_mode**|**int**|连接到承载 Web 同步的 Web 服务器时使用的身份验证模式。 值为**1**意味着 Windows 身份验证，并且值为**0**意味着[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]身份验证。|  
|**internet_timeout**|**int**|Web 同步请求过期之前的时间长度（秒）。|  
|**主机名**|**nvarchar(128)**|指定的重载的值[HOST_NAME](../../t-sql/functions/host-name-transact-sql.md)当在参数化的行筛选器的 WHERE 子句中使用此函数。|  
|**job_login**|**nvarchar(512)**|是以格式返回的 Windows 帐户运行合并代理*域*\\*用户名*。|  
|**job_password**|**sysname**|出于安全原因，值为"**\*\*\*\*\*\*\*\*\*\***"是始终返回。|  
  
## <a name="return-code-values"></a>返回代码值  
 **0** （成功） 或**1** （失败）  
  
## <a name="remarks"></a>注释  
 **sp_helpmergepullsubscription**合并复制中使用。 在结果集中，在中返回的日期**last_updated**格式化为*YYYYMMDD hh:mm:ss.fff*。  
  
## <a name="permissions"></a>权限  
 只有的成员**sysadmin**固定的服务器角色和**db_owner**固定的数据库角色可以执行**sp_helpmergepullsubscription**。  
  
## <a name="see-also"></a>另请参阅  
 [sp_addmergepullsubscription &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-addmergepullsubscription-transact-sql.md)   
 [sp_changemergepullsubscription &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-changemergepullsubscription-transact-sql.md)   
 [用 sp_dropmergepullsubscription &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropmergepullsubscription-transact-sql.md)   
 [复制存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
