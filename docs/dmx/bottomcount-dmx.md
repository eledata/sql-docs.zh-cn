---
title: BottomCount (DMX) |Microsoft 文档
ms.custom: ''
ms.date: 03/02/2016
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- BOTTOMCOUNT
dev_langs:
- DMX
helpviewer_keywords:
- BottomCount function
ms.assetid: bbe2f1d6-c8b5-49ce-ae13-337114a50aee
caps.latest.revision: 37
author: Minewiskan
ms.author: owend
manager: erikre
ms.workload: Inactive
ms.openlocfilehash: 90362587d913e70447157a353b738410122c6c38
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="bottomcount-dmx"></a>BottomCount (DMX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  按指定数量返回最底部的行，以表达式指定的升序排列。  
  
## <a name="syntax"></a>语法  
  
```  
  
BottomCount(<table expression>, <rank expression>, <count>)  
```  
  
## <a name="applies-to"></a>适用范围  
 一个表达式，返回一个表，如\<表列引用 >，或函数返回一个表。  
  
## <a name="return-type"></a>返回类型  
 \<表表达式 >  
  
## <a name="remarks"></a>Remarks  
 由提供的值\<排名表达式 > 自变量确定中提供的行级别的递增顺序\<表表达式 > 自变量，并在指定的最底部的行数\<计数 > 返回自变量。  
  
## <a name="examples"></a>示例  
 下面的示例创建针对你通过使用生成的关联模型的预测查询[Basic Data Mining Tutorial](http://msdn.microsoft.com/library/6602edb6-d160-43fb-83c8-9df5dddfeb9c)。  
  
 若要了解 BottomCount 的工作原理，它可能是第一次执行返回嵌套的表的预测查询很有帮助。  
  
```  
SELECT Predict ([Association].[v Assoc Seq Line Items], INCLUDE_STATISTICS, 10)  
FROM   
     [Association]  
NATURAL PREDICTION JOIN  
SELECT (SELECT 'Women''s Mountain Shorts' as [Model]) AS [v Assoc Seq Line Items]) AS t  
```  
  
> [!NOTE]  
>  在本示例中，作为输入而提供的值包含一个单引号；因此，必须通过在该值前面加一个单引号来进行转义。 如果不熟悉有关插入转义符的语法，则您可以使用预测查询生成器创建查询。 从下拉列表中选择值时，会为您插入所需的转义符。 有关详细信息，请参阅[在数据挖掘设计器中创建单独查询](../analysis-services/data-mining/create-a-singleton-query-in-the-data-mining-designer.md)。  
  
 示例结果：  
  
|“模型”|$SUPPORT|$PROBABILITY|$ADJUSTEDPROBABILITY|  
|-----------|--------------|------------------|--------------------------|  
|Sport-100|4334|0.291283016|0.252695851|  
|Water Bottle|2866|0.192620472|0.175205052|  
|Patch kit|2113|0.142012232|0.132389356|  
|Mountain Tire Tube|1992|0.133879965|0.125304948|  
|Mountain-200|1755|0.117951475|0.111260823|  
|Road Tire Tube|1588|0.106727603|0.101229538|  
|Cycling Cap|1473|0.098998589|0.094256014|  
|Fender Set - Mountain|1415|0.095100477|0.090718432|  
|Mountain Bottle Cage|1367|0.091874454|0.087780332|  
|Road Bottle Cage|1195|0.080314537|0.077173962|  
  
 BottomCount 函数使用此查询的结果，并将最小值行返回其总和的指定百分比。  
  
```  
SELECT   
BottomCount  
    (  
    Predict ([Association].[v Assoc Seq Line Items],INCLUDE_STATISTICS,10),  
    $SUPPORT,  
    3)  
FROM   
     [Association]  
NATURAL PREDICTION JOIN  
(SELECT (SELECT 'Women''s Mountain Shorts' as [Model]) AS [v Assoc Seq Line Items]) AS t  
```  
  
 BottomCount 函数的第一个参数是一个表列的名称。 在此示例中，嵌套的表返回通过调用预测函数并使用 INCLUDE_STATISTICS 自变量。  
  
 BottomCount 函数的第二个参数是使用对结果进行排序的嵌套表中的列。 在此示例中，INCLUDE_STATISTICS 选项返回 $SUPPORT、$PROBABILTY 和 $ADJUSTED PROBABILITY 列。 此示例使用 $SUPPORT，因为支持值不带有小数，所以很容易进行验证。  
  
 BottomCount 函数的第三个参数指定行的数。 若要获取按 $SUPPORT 排序的排名最低的最后三个行，请键入 3。  
  
 示例结果：  
  
|“模型”|$SUPPORT|$PROBABILITY|$ADJUSTEDPROBABILITY|  
|-----------|--------------|------------------|--------------------------|  
|Road Bottle Cage|1195|0.080314537|0.077173962|  
|Mountain Bottle Cage|1367|0.091874454|0.087780332|  
|Fender Set - Mountain|1415|0.095100477|0.090718432|  
  
 **请注意**提供了此示例仅为说明 BottomCount 使用。 运行此查询可能需要很长时间，具体取决于数据集的大小。  
  
## <a name="see-also"></a>另请参阅  
 [函数 &#40; DMX &#41;](../dmx/functions-dmx.md)   
 [常规预测函数 &#40; DMX &#41;](../dmx/general-prediction-functions-dmx.md)   
 [BottomPercent &#40; DMX &#41;](../dmx/bottompercent-dmx.md)   
 [BottomSum &#40; DMX &#41;](../dmx/bottomsum-dmx.md)   
 [TopCount &#40; DMX &#41;](../dmx/topcount-dmx.md)  
  
  
