---
title: CREATE SECURITY POLICY (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 08/10/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|statements
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SECURITY_POLICY_TSQL
- CREATE SECURITY
- SECURITY
- CREATE_SECURITY_POLICY_TSQL
- CREATE_SECURITY_TSQL
- SECURITY POLICY
- SECURITY_TSQL
- CREATE SECURITY POLICY
dev_langs:
- TSQL
helpviewer_keywords:
- RLS
- CREATE SECURITY POLICY statement
- Row-Level Security
ms.assetid: d6ab70ee-0fa2-469c-96f6-a3c16d673bc8
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: 205a09efdef9e59736fa20238455b4327dced330
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="create-security-policy-transact-sql"></a>CREATE SECURITY POLICY (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  为行级别安全性创建安全策略。  
  
 ![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>语法  
  
```     
CREATE SECURITY POLICY [schema_name. ] security_policy_name    
    { ADD [ FILTER | BLOCK ] } PREDICATE tvf_schema_name.security_predicate_function_name   
      ( { column_name | arguments } [ , …n] ) ON table_schema_name. table_name    
      [ <block_dml_operation> ] , [ , …n] 
    [ WITH ( STATE = { ON | OFF }  [,] [ SCHEMABINDING = { ON | OFF } ] ) ]  
    [ NOT FOR REPLICATION ] 
[;]  
  
<block_dml_operation>  
    [ { AFTER { INSERT | UPDATE } }   
    | { BEFORE { UPDATE | DELETE } } ]  
```  
  
## <a name="arguments"></a>参数  
 *security_policy_name*  
 安全策略的名称。 安全策略名称必须符合有关标识符的规则，并且在数据库中以及对其架构来说必须是唯一的。  
  
 *schema_name*  
 是安全策略所属架构的名称。 由于架构绑定，必须使用 schema_name。  
  
 [ FILTER | BLOCK ]  
 绑定到目标表的函数的安全谓词类型。 FILTER 谓词以静默方式筛选可用于读取操作的行。 BLOCK 谓词显式阻止违反谓词函数的写入操作。  
  
 tvf_schema_name.security_predicate_function_name  
 是将用作谓词的内联表值函数，并且将强制用于对目标表的查询。 最多能为针对特定表的特定 DML 操作定义一个安全谓词。 必须使用 SCHEMABINDING 选项创建内联表值函数。  
  
 { *column_name* | *arguments* }  
 用作安全谓词函数的参数的列名和表达式。 目标表上的任意列都能用作谓词函数的参数。 可以使用包含文字、内置的表达式和使用算术运算符的表达式。  
  
 table_schema_name.table_name  
 是将要应用安全谓词的目标表。 对于特定 DML 操作，多个禁用的安全策略能以单个表为目标，但是在任何给定时间只能启用一个。  
  
 *\<block_dml_operation>* 要应用阻止谓词的特定 DML 操作。 AFTER 指定将针对 DML 操作（INSERT 或 UPDATE）执行后的行值计算谓词。 BEFORE 指定将针对 DML 操作（UPDATE 或 DELETE）执行前的行值计算谓词。 如果不指定任何操作，则谓词将应用到所有操作。  
  
 [ STATE = { ON | **OFF** } ]  
 使安全策略能够或禁止其对目标表强制执行其安全谓词。 如果未指定，则将启用正在创建的安全性策略。  
  
 [ SCHEMABINDING = { ON | OFF } ]  
 指示是否策略中的所有谓词函数都必须使用 SCHEMABINDING 选项创建。 默认情况下，所有函数必须使用 SCHEMABINDING 创建。  
  
 NOT FOR REPLICATION  
 指示当复制代理修改目标对象时不应执行安全策略。 有关详细信息，请参阅[控制同步期间触发器和约束的行为（复制 Transact-SQL 编程）](../../relational-databases/replication/control-behavior-of-triggers-and-constraints-in-synchronization.md)。  
  
 [table_schema_name.] table_name  
 是将要应用安全谓词的目标表。 多个禁用的安全策略能以单个表为目标，但是在任何给定时间只能启用一个。  
  
## <a name="remarks"></a>Remarks  
 将谓词函数用于内存优化表时，必须包含 SCHEMABINDING 并使用 WITH NATIVE_COMPILATION 编译提示。  
  
 在执行相应 DML 操作后计算阻止谓词。 因此，READ UNCOMMITTED 查询可看到要回滚的临时值。  
  
## <a name="permissions"></a>权限  
 要求对架构具有 ALTER ANY SECURITY POLICY 权限和 ALTER 权限。  
  
 另外，每个添加的谓词都需要以下权限：  
  
-   针对被用作谓词的函数的 SELECT 和 REFERENCES 权限。  
  
-   针对绑定到策略的目标表的 REFERENCES 权限。  
  
-   针对目标表上被用作参数的每一列的 REFERENCES 权限。  
  
## <a name="examples"></a>示例  
 以下示例展示了 **CREATE SECURITY POLICY** 语法的使用。 有关完整安全策略方案的示例，请参阅[行级安全性](../../relational-databases/security/row-level-security.md)。  
  
### <a name="a-creating-a-security-policy"></a>A. 创建安全策略  
 以下语法为 Customer 表创建了带有一个筛选器谓词的安全策略，并使安全策略处于禁用状态。  
  
```  
CREATE SECURITY POLICY [FederatedSecurityPolicy]   
ADD FILTER PREDICATE [rls].[fn_securitypredicate]([CustomerId])   
ON [dbo].[Customer];  
```  
  
### <a name="b-creating-a-policy-that-affects-multiple-tables"></a>B. 创建影响多个表的策略  
 以下语法对三个不同的表创建了带有三个筛选谓词的安全策略，并启用了该安全策略。  
  
```  
CREATE SECURITY POLICY [FederatedSecurityPolicy]   
ADD FILTER PREDICATE [rls].[fn_securitypredicate1]([CustomerId])   
    ON [dbo].[Customer],  
ADD FILTER PREDICATE [rls].[fn_securitypredicate1]([VendorId])   
    ON [dbo].[ Vendor],  
ADD FILTER PREDICATE [rls].[fn_securitypredicate2]([WingId])   
    ON [dbo].[Patient]  
WITH (STATE = ON);  
```  
  
### <a name="c-creating-a-policy-with-multiple-types-of-security-predicates"></a>C. 使用多个类型的安全谓词创建策略  
 同时将筛选器谓词和阻止谓词添加到 Sales 表。  
  
```  
CREATE SECURITY POLICY rls.SecPol  
    ADD FILTER PREDICATE rls.tenantAccessPredicate(TenantId) ON dbo.Sales,  
    ADD BLOCK PREDICATE rls.tenantAccessPredicate(TenantId) ON dbo.Sales AFTER INSERT;  
```  
  
## <a name="see-also"></a>另请参阅  
 [行级安全性](../../relational-databases/security/row-level-security.md)   
 [ALTER SECURITY POLICY (Transact-SQL)](../../t-sql/statements/alter-security-policy-transact-sql.md)   
 [DROP SECURITY POLICY (Transact-SQL)](../../t-sql/statements/drop-security-policy-transact-sql.md)   
 [sys.security_policies (Transact-SQL)](../../relational-databases/system-catalog-views/sys-security-policies-transact-sql.md)   
 [sys.security_predicates (Transact-SQL)](../../relational-databases/system-catalog-views/sys-security-predicates-transact-sql.md)  
  
  

