---
title: "avg 函数 (XQuery) |Microsoft 文档"
ms.custom: 
ms.date: 08/09/2016
ms.prod: sql-non-specified
ms.prod_service: sql-non-specified
ms.service: 
ms.component: xquery
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- fn:avg function
- avg function [XQuery]
ms.assetid: 0cc60267-3c56-4a88-8ad7-bb07f0255d56
caps.latest.revision: 
author: rothja
ms.author: jroth
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: ee1d24bc4b28b7a041baa42ac829424e5daa6f8b
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="aggregate-functions---avg"></a>聚合函数的平均值
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  返回一组数值的平均值。  
  
## <a name="syntax"></a>语法  
  
```  
  
fn:avg($arg as xdt:anyAtomicType*) as xdt:anyAtomicType?  
```  
  
## <a name="arguments"></a>参数  
 *$arg*  
 一组要计算平均值的原子值。  
  
## <a name="remarks"></a>注释  
 传递到的原子化值的所有类型**avg （)**必须恰好有一个三个内置的数值基类型或 xdt:untypedAtomic 的子类型。 不能使用不同的数值类型。 类型为 xdt:untypedAtomic 的值视为 xs:double。 结果**avg （)**接收传入的类型，如在 xdt:untypedAtomic 的情况下将 xs: double 的基类型。  
  
 如果输入为静态空值，则空值为隐式表达，并会返回静态错误。  
  
 **Avg （)**函数将返回计算数值的平均值。 例如：  
  
 **sum(** *$arg* **) div count(** *$arg* **)**  
  
 如果*$arg*空序列，则返回空序列。  
  
 如果 xdt:untypedAtomic 值无法转换为将 xs: double，在输入序列中，忽略值*$arg*。  
  
 在所有其他情况下，函数均返回静态错误。  
  
## <a name="examples"></a>示例  
 本主题提供对存储在各种的 XML 实例的 XQuery 示例**xml** AdventureWorks 数据库中的类型列。  
  
### <a name="a-using-the-avg-xquery-function-to-find-work-center-locations-in-the-manufacturing-process-in-which-labor-hours-are-greater-than-the-average-for-all-work-center-locations"></a>A. 使用 avg() XQuery 函数来查找生产过程中工时大于所有生产车间的工时平均值的生产车间。  
 你可以重写中提供的查询[min 函数 (XQuery)](../xquery/aggregate-functions-min.md)使用**avg （)**函数。  
  
## <a name="implementation-limitations"></a>实现限制  
 限制如下：  
  
-   **Avg （)**函数映射到 xs: decimal 的所有整数。  
  
-   **Avg （)**不支持对类型 xs: duration 值的函数。  
  
-   不支持跨基类型边界混合类型的序列。  
  
## <a name="see-also"></a>另请参阅  
 [针对 xml 数据类型的 XQuery 函数](../xquery/xquery-functions-against-the-xml-data-type.md)  
  
  
