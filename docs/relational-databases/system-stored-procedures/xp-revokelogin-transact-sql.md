---
title: xp_revokelogin (Transact SQL) |Microsoft 文档
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
- xp_revokelogin
- xp_revokelogin_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- xp_revokelogin
ms.assetid: b3fa7678-dba4-4537-be94-5ae63ca11f81
caps.latest.revision: 25
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c9edf410ce4ffb8fee8b1130770bd27c0e2ca160
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="xprevokelogin-transact-sql"></a>xp_revokelogin (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  撤消 Windows 组或用户对 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 的访问权限。  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] 使用[DROP LOGIN](../../t-sql/statements/drop-login-transact-sql.md)相反。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
xp_revokelogin {[@loginame=] 'login'}  
```  
  
## <a name="arguments"></a>参数  
 [ **@loginame =** ] **'***login***'**  
 撤消其访问权限的 Windows 用户或用户组的名称。 *登录名*必须包括域名，例如**[ADVWKS\sylvester1]**。 *登录名*是**sysname**，无默认值。  
  
## <a name="return-code-values"></a>返回代码值  
 0（成功）或 1（失败）  
  
## <a name="remarks"></a>注释  
 请改用 DROP LOGIN。  
  
## <a name="permissions"></a>权限  
 要求对服务器拥有 ALTER ANY LOGIN 权限。  
  
## <a name="see-also"></a>另请参阅  
 [sp_denylogin (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-denylogin-transact-sql.md)   
 [sp_grantlogin (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-grantlogin-transact-sql.md)   
 [sp_revokelogin (Transact-SQL)](../../relational-databases/system-stored-procedures/sp-revokelogin-transact-sql.md)   
 [系统存储过程 (Transact-SQL)](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)   
 [常规扩展存储的过程&#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/general-extended-stored-procedures-transact-sql.md)   
 [xp_loginconfig &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/xp-loginconfig-transact-sql.md)   
 [xp_logininfo &#40;Transact SQL&#41;](../../relational-databases/system-stored-procedures/xp-logininfo-transact-sql.md)  
  
  
