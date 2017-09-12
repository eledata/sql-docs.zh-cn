---
title: "（取模）（SSIS 表达式） |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- '% (modulo operator)'
- remainder of division operation
- modulo operator (%)
ms.assetid: e2920821-2f5b-4c76-8db8-8b9eddf4606f
caps.latest.revision: 34
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 135fbe7a231de0b77ba3637ef53a4fc785453c10
ms.contentlocale: zh-cn
ms.lasthandoff: 08/03/2017

---
# <a name="modulo-ssis-expression"></a>（取模）（SSIS 表达式）
  将第一个数据表达式的值除以第二个数据表达式的值后，提供整数余数。  
  
## <a name="syntax"></a>语法  
  
```  
  
dividend % divisor  
  
```  
  
## <a name="arguments"></a>参数  
 *被除数*  
 被除数的数值表达式。 *dividend* 可以是任意有效的数值表达式。 有关详细信息，请参阅 [Integration Services 数据类型](../../integration-services/data-flow/integration-services-data-types.md)。  
  
 *除数*  
 除数的数值表达式。 *divisor* 可以是除 0 之外的任意有效的数值表达式。  
  
## <a name="result-types"></a>结果类型  
 由两个参数的数据类型确定。 有关详细信息，请参阅 [Integration Services Data Types in Expressions](../../integration-services/expressions/integration-services-data-types-in-expressions.md)。  
  
## <a name="remarks"></a>注释  
 两个表达式的计算结果必须为有符号或无符号整数数据类型。  
  
 如果任意一个操作数为 Null，则结果为 Null。  
  
 不可对零取模。  
  
## <a name="expression-examples"></a>表达式示例  
 以下示例对两个数值取模。 结果为 3。  
  
```  
42 % 13  
```  
  
 以下示例对 **SalesQuota** 列和一个数值文字取模。  
  
```  
SalesQuota % 12  
```  
  
 以下示例对两个数值变量 **Sales$** 和 **Month**取模。 变量 **Sales$** 的名称包含 $ 字符，所以必须括在括号内。 有关详细信息，请参阅[标识符 (SSIS)](../../integration-services/expressions/identifiers-ssis.md)。  
  
```  
@[Sales$] % @Month  
```  
  
 以下示例使用取模运算符确定 **Value** 变量的值为偶数还是奇数，并使用条件运算符返回对结果进行说明的字符串。 有关详细信息，请参阅 [?：（条件）（SSIS 表达式）](../../integration-services/expressions/conditional-ssis-expression.md)。  
  
```  
@Value % 2 == 0? "even":"odd"  
```  
  
## <a name="see-also"></a>另请参阅  
 [运算符优先级和结合性](../../integration-services/expressions/operator-precedence-and-associativity.md)   
 [运算符 &#40;SSIS 表达式 &#41;](../../integration-services/expressions/operators-ssis-expression.md)  
  
  