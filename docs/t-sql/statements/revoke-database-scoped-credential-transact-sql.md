---
title: "REVOKE 数据库作用域凭据 (Transact-SQL) | Microsoft Docs"
ms.custom: 
ms.date: 12/16/2016
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- REVOKE DATABASE SCOPED CREDENTIAL
- REVOKE_DATABASE_SCOPED_CREDENTIAL_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- REVOKE statements, database scoped credentials
- revoking permissions [SQL Server], database scoped credentials
ms.assetid: b73233c5-9afa-48ca-ba34-a9f86b9b1d2e
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 074fe713de6116e2ba07ee9c5fedf7e34789cf4b
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="revoke-database-scoped-credential-transact-sql"></a>REVOKE 数据库作用域凭据 (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2017-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2017-asdb-xxxx-xxx-md.md)]

  撤消对数据库作用域凭据的权限。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```  
  
REVOKE [ GRANT OPTION FOR ] permission  [ ,...n ]   
    ON DATABASE SCOPED CREDENTIAL :: credential_name   
    { TO | FROM } database_principal [ ,...n ]  
    [ CASCADE ]  
    [ AS revoking_principal ]  
```  
  
## <a name="arguments"></a>参数  
 GRANT OPTION FOR  
 指示将撤消授予指定权限的能力。 不会撤消该权限本身。  
  
> [!IMPORTANT]  
>  如果主体具有不带 GRANT 选项的指定权限，则将撤消该权限本身。  
  
 *permission*  
 指定可对数据库作用域凭据撤消的权限。 如下所列。  
  
 ON CERTIFICATE ::credential_name  
 指定要对其撤消权限的数据库作用域凭据。 需要使用作用域限定符“::”。  
  
 *database_principal*  
 指定要从中撤消权限的主体。 可以是以下类型之一：  
  
-   数据库用户  
  
-   数据库角色  
  
-   应用程序角色  
  
-   映射到 Windows 登录名的数据库用户  
  
-   映射到 Windows 组的数据库用户  
  
-   映射到证书的数据库用户  
  
-   映射到非对称密钥的数据库用户  
  
-   未映射到服务器主体的数据库用户。  
  
 CASCADE  
 指示要撤消的权限也会从此主体授予该权限的其他主体中撤消。  
  
> [!CAUTION]  
>  如果对授予了 WITH GRANT OPTION 权限的权限执行级联撤消，将同时撤消该权限的 GRANT 和 DENY 权限。  
  
 AS revoking_principal  
 指定一个主体，执行该查询的主体从该主体获得撤消该权限的权利。 可以是以下类型之一：  
  
-   数据库用户  
  
-   数据库角色  
  
-   应用程序角色  
  
-   映射到 Windows 登录名的数据库用户  
  
-   映射到 Windows 组的数据库用户  
  
-   映射到证书的数据库用户  
  
-   映射到非对称密钥的数据库用户  
  
-   未映射到服务器主体的数据库用户。  
  
## <a name="remarks"></a>Remarks  
 数据库作用域凭据是一个数据库级的安全对象，包含于权限层次结构中作为其父级的数据库中。 下面列出了可以对数据库作用域凭据撤消的最特定、最有限的权限，以及暗含这些权限的较一般的权限。  
  
|数据库作用域凭据权限|数据库作用域凭据权限隐含的权限|数据库权限隐含的权限|  
|----------------------------|---------------------------------------|------------------------------------|  
|CONTROL|CONTROL|CONTROL|  
|TAKE OWNERSHIP|CONTROL|CONTROL|  
|ALTER|CONTROL|CONTROL|  
|REFERENCES|CONTROL|REFERENCES|  
|VIEW DEFINITION|CONTROL|VIEW DEFINITION|  
  
## <a name="permissions"></a>权限  
 要求对数据库作用域凭据具有 CONTROL 权限。  
  
## <a name="see-also"></a>另请参阅  
 [REVOKE (Transact-SQL)](../../t-sql/statements/revoke-transact-sql.md)      
 [GRANT 数据库作用域凭据 (Transact-SQL)](../../t-sql/statements/grant-database-scoped-credential-transact-sql.md)   
 [DENY 数据库作用域凭据 (Transact-SQL)](../../t-sql/statements/deny-database-scoped-credential-transact-sql.md)   
 [权限（数据库引擎）](../../relational-databases/security/permissions-database-engine.md)   
 [主体（数据库引擎）](../../relational-databases/security/authentication-access/principals-database-engine.md)   
 [加密层次结构](../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
