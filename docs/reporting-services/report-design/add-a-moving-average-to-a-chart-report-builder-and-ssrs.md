---
title: "向图表 （报表生成器和 SSRS） 中添加移动平均线 |Microsoft 文档"
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 166cf9c1-0750-4866-8381-542e4fbfe65a
caps.latest.revision: 13
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 0eb007a5207ceb0b023952d5d9ef6d95986092ac
ms.openlocfilehash: f838e4a7e9518587e91dddec6c2cab61c1061232
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="add-a-moving-average-to-a-chart-report-builder-and-ssrs"></a>向图表添加移动平均线（报表生成器和 SSRS）
移动平均值是序列中数据的平均值，它是根据定义的时间段内的数据计算的。 在 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] 分页报表中，可以在图表中显示移动平均值来标识明显趋势。  

![report-builder-column-chart-tutorial](../../reporting-services/media/report-builder-column-chart-tutorial.png)
  
 移动平均值公式是技术分析中最常用的价格指标。 包括平均值、中值和标准偏差在内的许多其他公式也可以从图表的序列中派生。 指定移动平均值时，每个公式可能有一个或多个必须指定的参数。  
 
 [教程： 将一个柱形图添加到您的报表 （报表生成器）](Tutorial:%20Add%20a%20Column%20Chart%20to%20Your%20Report%20\(Report%20Builder\).md)如果你想要使用示例数据尝试将指导你完成向图表添加移动平均线。
  
 在设计模式下添加移动平均值公式时，添加的行序列只会显示为占位符。 该图表将在报表处理期间计算每个公式的数据点。  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]中不提供对趋势线的内置支持。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-add-a-calculated-moving-average-to-a-series-on-the-chart"></a>将计算的移动平均值添加到图表的序列  
  
1.  右键单击“ **值** ”区域中的字段，然后单击“ **添加计算序列**”。 随即打开 **“计算序列属性”** 对话框。  
  
2.  从“ **公式** ”下拉列表中选择“ **移动平均值** ”选项。  
  
3.  为表示移动平均值期间的 **“期间”** 指定一个整数值。  
  
    > [!NOTE]  
    >  期间是用来计算移动平均值的天数。 如果未在 X 轴上指定日期／时间值，该期间将由用于计算移动平均值的数据点的数量来表示。 如果只有一个数据点，移动平均值公式将不会进行计算。 移动平均值从第二个点处开始计算。 如果您指定 **“从第一点开始”** 选项，则图表将从第一个点处的移动平均值开始。 如果只有一个数据点，则计算出的移动平均值中的点将与原始序列中的第一个点一致。  
  
## <a name="see-also"></a>另請參閱  
* [教程：向报表添加柱形图（报表生成器）](Tutorial:%20Add%20a%20Column%20Chart%20to%20Your%20Report%20\(Report%20Builder\).md)
*  [格式设置图表 &#40;报表生成器和 SSRS &#41;](../../reporting-services/report-design/formatting-a-chart-report-builder-and-ssrs.md)   
*  [图表&#40;报表生成器和 SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)   
*  [向图表添加空点&#40;报表生成器和 SSRS&#41;](../../reporting-services/report-design/add-empty-points-to-a-chart-report-builder-and-ssrs.md)  
  
  