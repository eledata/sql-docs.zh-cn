---
title: "SQL 全文筛选器后台程序启动器 （选项卡上的日志） |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: 
ms.component: configuration-manager
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13e260f9-a75f-430b-88a3-959ddcead8fe
caps.latest.revision: 
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 9f54e45734a06030f3a216eea5247a555a94673c
ms.sourcegitcommit: c556eaf60a49af7025db35b7aa14beb76a8158c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="sql-full-text-filter-daemon-launcher-log-on-tab"></a>SQL 全文筛选器后台程序启动器（“登录”选项卡）
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
从 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]开始， [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 全文搜索将使用 SQL 全文筛选器后台程序启动器 (FDHOST Launcher) 服务。 如果使用全文搜索，则必须运行此服务。 有关筛选器后台程序主机进程的信息，请参阅 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 联机丛书中的“全文搜索体系结构”。  
  
 使用 **“SQL 全文筛选器后台程序启动器属性”** 对话框的 **“登录”** 选项卡可以指定 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 全文服务所使用的帐户，还可以更改帐户的密码以及启动和停止此服务。 更改帐户的密码将在重新启动此服务后生效。  
  
> [!NOTE]  
>  更改群集实例的服务所使用的帐户名时，新帐户必须是安装期间为服务指定的域组的成员，或者您必须具有向该组添加成员的权限。 如果您无权修改组成员身份，请与域管理员联系。  
>   
>  有关选择帐户以运行服务的详细信息，请参阅 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 联机帮助中的“设置 Windows 服务帐户”。  
  
## <a name="options"></a>选项  
 **内置帐户**  
 **Local System**  
 指定本地系统帐户。 该帐户不需要密码。 但是，本地系统帐户可能会阻止该服务与其他服务器进行交互，具体取决于该帐户所拥有的权限。  
  
 **Local Service**  
 指定本地服务帐户。 该帐户不需要密码。 不过，本地服务帐户可能会阻止该服务与其他服务器进行交互，具体取决于该帐户所拥有的权限。  
  
 **Network Service**  
 我们建议不要使用 Network Service 帐户运行 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 服务或 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 代理服务。 Local User 帐户或 Domain User 帐户更适用于这些服务。  
  
 **本帐户**  
 指定一个使用 Windows 身份验证的本地用户帐户或域用户帐户。 建议使用具有最低服务权限的域用户帐户。  
  
 **帐户名**  
 指定本地用户帐户名或域用户帐户名。  
  
 **密码**  
 键入帐户的密码。  
  
 **确认密码**  
 再次键入帐户的密码。  
  
 **开始**  
 启动服务。  
  
 **停止**  
 停止服务。  
  
 **暂停**  
 暂停服务。 不可用于此服务。  
  
 **恢复**  
 恢复暂停的服务。  
  
  
