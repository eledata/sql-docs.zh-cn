---
title: KPIValue (MDX) |Microsoft 文档
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- kbMDX
helpviewer_keywords:
- KPIValue function
ms.assetid: c4f8532c-4c24-4ad5-8847-4522511e0039
caps.latest.revision: 19
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 90f82b02602733d6af86193d750d57751714fc96
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="kpivalue-mdx"></a>KPIValue (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  返回计算指定关键绩效指标 (KPI) 的值的成员。  
  
## <a name="syntax"></a>语法  
  
```  
  
KPIValue(KPI_Name)  
```  
  
## <a name="arguments"></a>参数  
 *KPI_Name*  
 一个有效的字符串表达式，指定 KPI 的名称。  
  
## <a name="remarks"></a>Remarks  
  
## <a name="example"></a>示例  
 下例将返回 Fiscal Year 属性层次结构中三个成员后代的渠道收入度量值的 KPI 值、KPI 目标、KPI 状态和 KPI 走向。  
  
```  
SELECT  
   { KPIValue("Channel Revenue"),   
     KPIGoal("Channel Revenue"),  
     KPIStatus("Channel Revenue"),   
     KPITrend("Channel Revenue")  
   } ON Columns,  
Descendants  
   ( { [Date].[Fiscal].[Fiscal Year].&[2002],  
       [Date].[Fiscal].[Fiscal Year].&[2003],  
       [Date].[Fiscal].[Fiscal Year].&[2004]   
     }, [Date].[Fiscal].[Fiscal Quarter]  
   ) ON Rows  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>另请参阅  
 [MDX 函数引用 &#40;MDX &#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
