---
title: "调整 APPEND 子句 |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shape commands [ADO]
- data shaping [ADO], APPEND clause
- append clause [ADO]
ms.assetid: f90fcf55-6b24-401d-94e1-d65bd24bd342
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 8f4c9bf19fd1df07bb4271a8db94311548a4e092
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="shape-append-clause"></a>形状 APPEND 子句
形状命令 APPEND 子句将某一列或列追加**记录集**。 通常情况下，这些列即变为章节列，后者是指子**记录集**。  
  
## <a name="syntax"></a>语法  
  
```  
SHAPE [parent-command [[AS] parent-alias]] APPEND column-list  
```  
  
## <a name="description"></a>Description  
 此子句的部分如下所示：  
  
 *parent-command*  
 零个或以下一项 (可以忽略*父命令*完全):  
  
-   返回的提供程序命令括在大括号 （"{"）**记录集**对象。 对基础数据提供程序发出该命令，其语法取决于该提供程序的要求。 通常，这是 SQL 语言中，尽管 ADO 不需要任何特定的查询语言。  
  
-   另一个形状命令嵌入在括号中。  
  
-   表关键字后, 跟的表中的数据提供程序的名称。  
  
 *parent-alias*  
 可选别名引用父**记录集**。  
  
 *column-list*  
 一个或多个以下：  
  
-   聚合列。  
  
-   计算的列。  
  
-   通过使用新子句创建的新列。  
  
-   章节列。 章节列的定义括在括号 （"（）"）。 请参阅下面的语法。  
  
```  
SHAPE [parent-command [[AS] parent-alias]]  
   APPEND (child-recordset [ [[AS] child-alias]   
      RELATE parent-column TO child-column | PARAMETER param-number, ... ])  
   [[AS] chapter-alias]   
   [, ... ]  
```  
  
## <a name="remarks"></a>注释  
 *child-recordset*  
 -   返回的提供程序命令括在大括号 （"{"）**记录集**对象。 对基础数据提供程序发出该命令，其语法取决于该提供程序的要求。 通常，这是 SQL 语言中，尽管 ADO 不需要任何特定的查询语言。  
  
-   另一个形状命令嵌入在括号中。  
  
-   现有的形状名称**记录集**。  
  
-   表关键字后, 跟的表中的数据提供程序的名称。  
  
 *child-alias*  
 到子引用的别名**记录集**。  
  
 *parent-column*  
 中的列**记录集**返回*父命令。*  
  
 *child-column*  
 中的列**记录集**返回*子命令*。  
  
 *param-number*  
 请参阅[操作的参数化命令](../../../ado/guide/data/operation-of-parameterized-commands.md)。  
  
 *chapter-alias*  
 指追加到父级的章节列别名。  
  
> [!NOTE]
>  *"父列*收件人*子列"*子句实际上是一个列表，其中用逗号分隔每个定义的关系  
  
> [!NOTE]
>  子句后追加关键字实际上是一个列表，其中每个子句用逗号分隔，并定义要追加到父级的另一列。  
  
## <a name="remarks"></a>注释  
 构造时提供程序从用户输入的命令为形状命令的一部分，形状会将用户提供的提供程序命令视为不透明的字符串并将它们传递给提供程序的忠实。 例如，在下面的形状命令中，  
  
```  
SHAPE {select * from t1} APPEND ({select * from t2} RELATE k1 TO k2)  
```  
  
 形状将执行两个命令：`select * from t1`和 (`select * from t2 RELATE k1 TO k2)`。 如果在用户提供的用分号分隔的多个提供程序命令所组成的复合命令，则形状不能区分差异。 因此，在以下的形状命令，  
  
```  
SHAPE {select * from t1; drop table t1} APPEND ({select * from t2} RELATE k1 TO k2)  
```  
  
 形状执行`select * from t1; drop table t1`和 (`select * from t2 RELATE k1 TO k2),`未意识到，`drop table t1`都单独和在此种情况下，很危险，提供程序命令中。 应用程序必须始终验证用户输入，以防止发生这种潜在的黑客攻击。  
  
 本部分包含以下主题。  
  
-   [操作非参数化命令](../../../ado/guide/data/operation-of-non-parameterized-commands.md)  
  
-   [参数化命令的操作](../../../ado/guide/data/operation-of-parameterized-commands.md)  
  
-   [混合命令](../../../ado/guide/data/hybrid-commands.md)  
  
-   [中间 Shape COMPUTE 子句](../../../ado/guide/data/intervening-shape-compute-clauses.md)  
  
## <a name="see-also"></a>另请参阅  
 [调整示例数据](../../../ado/guide/data/data-shaping-example.md)   
 [正式形状语法](../../../ado/guide/data/formal-shape-grammar.md)   
 [常用 Shape 命令](../../../ado/guide/data/shape-commands-in-general.md)
