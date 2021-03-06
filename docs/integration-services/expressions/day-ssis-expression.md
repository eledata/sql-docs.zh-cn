---
title: "DAY（SSIS 表达式）| Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: expressions
ms.reviewer: 
ms.suite: sql
ms.technology:
- integration-services
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DAY function
- dates [Integration Services], DAY
ms.assetid: d8447187-49df-45b7-a98e-142ad44fd3e2
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 417f08ab011404918c1f87ecb4aaf14a08e6f4fa
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="day-ssis-expression"></a>DAY（SSIS 表达式）
  返回一个整数，表示日期的“日”日期部分。  
  
## <a name="syntax"></a>语法  
  
```  
  
DAY(date)  
```  
  
## <a name="arguments"></a>参数  
 *date*  
 返回有效日期或日期格式的字符串的表达式。  
  
## <a name="result-types"></a>结果类型  
 DT_I4  
  
## <a name="remarks"></a>Remarks  
 如果参数为空，则 DAY 将返回空结果。  
  
 日期文字必须显式转换为日期数据类型之一。 有关详细信息，请参阅 [Integration Services Data Types](../../integration-services/data-flow/integration-services-data-types.md)。  
  
> [!NOTE]  
>  在日期文本显式转换为以下日期数据类型之一时，表达式验证失败：DT_DBTIMESTAMPOFFSET 和 DT_DBTIMESTAMP2。  
  
 与 DATEPART("Day", date) 相比，DAY 函数效果相同，但更简洁。  
  
## <a name="expression-examples"></a>表达式示例  
 以下示例返回日期文字中的日期数字。 如果日期格式是“mm/dd/yyyy”格式，则此示例将返回 23。  
  
```  
DAY((DT_DBTIMESTAMP)"11/23/2002")  
```  
  
 此示例返回 **ModifiedDate** 列中表示天的整数。  
  
```  
DAY(ModifiedDate)  
```  
  
 以下示例返回表示当前日期的“日”部分的整数。  
  
```  
DAY(GETDATE())  
```  
  
## <a name="see-also"></a>另请参阅  
 [DATEADD（SSIS 表达式）](../../integration-services/expressions/dateadd-ssis-expression.md)   
 [DATEDIFF（SSIS 表达式）](../../integration-services/expressions/datediff-ssis-expression.md)   
 [DATEPART（SSIS 表达式）](../../integration-services/expressions/datepart-ssis-expression.md)   
 [MONTH（SSIS 表达式）](../../integration-services/expressions/month-ssis-expression.md)   
 [YEAR（SSIS 表达式）](../../integration-services/expressions/year-ssis-expression.md)   
 [函数（SSIS 表达式）](../../integration-services/expressions/functions-ssis-expression.md)  
  
  
