---
title: CRYPT_GEN_RANDOM (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 07/24/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: t-sql|functions
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- CRYPT_GEN_RANDOM_TSQL
- CRYPT_GEN_RANDOM
dev_langs:
- TSQL
helpviewer_keywords:
- CRYPT_GEN_RANDOM function
ms.assetid: b74bd9d4-758e-4b94-89a0-76dcda6d8c42
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 695af04a3ee411392cf00be6b6483c9338a4c989
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="cryptgenrandom-transact-sql"></a>CRYPT_GEN_RANDOM (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-asdb-xxxx-xxx-md.md)]

返回 Crypto API (CAPI) 生成的加密随机数。 该输出是十六进制形式的指定字节数。
  
![主题链接图标](../../database-engine/configure-windows/media/topic-link.gif "主题链接图标") [TRANSACT-SQL 语法约定](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>语法  
  
```sql
CRYPT_GEN_RANDOM ( length [ , seed ] )   
```  
  
## <a name="arguments"></a>参数  
*length*  
创建的数字的长度。 最大值为 8000。 length 的数据类型为 int 。
  
seed  
用作随机种子的可选数据。  必须至少包含 length 个字节的数据。 seed 的数据类型为 varbinary(8000)。
  
## <a name="returned-types"></a>返回类型  
varbinary(8000)
  
## <a name="permissions"></a>权限  
此函数是公用的，因此不需要任何特殊权限。
  
## <a name="examples"></a>示例  
  
### <a name="a-generating-a-random-number"></a>A. 生成随机数  
下面的示例生成一个长度为 50 个字节的随机数。
  
```sql
SELECT CRYPT_GEN_RANDOM(50) ;  
```  
  
下面的示例使用 4 个字节的种子生成一个长度为 4 个字节的随机数。
  
```sql
SELECT CRYPT_GEN_RANDOM(4, 0x25F18060) ;  
```  
  
## <a name="see-also"></a>另请参阅
[RAND (Transact-SQL)](../../t-sql/functions/rand-transact-sql.md)
  
  
