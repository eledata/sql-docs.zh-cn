---
title: "浏览多维数据集 |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: get-started-article
applies_to:
- SQL Server 2016
ms.assetid: 3819946e-d3fa-4c1d-afe3-599c938b1b2e
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: f7b95813f17802e22e4b9308cc0a3805f65f5ff2
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="lesson-2-6---browsing-the-cube"></a>课程 2-6-浏览多维数据集
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

在部署多维数据集后，可以在多维数据集设计器的“浏览器”选项卡中查看多维数据集数据，以及在维度设计器的“浏览器”选项卡中查看维度数据。 浏览多维数据集和维度数据是以增量方式检查您的工作的方式。 您可以在处理对象后，验证对属性、关系和其他对象的细微更改是否具有期望的效果。 在使用“浏览器”选项卡来查看多维数据集和维度数据时，该选项卡将基于您正在浏览的对象提供不同的功能。  
  
对于维度，“浏览器”选项卡提供一个方法来查看成员或导航层次结构，可一直向下到叶节点。 您可以通过不同语言浏览维度数据，假定您已将翻译添加到您的模型中。  
  
对于多维数据集，“浏览器”选项卡提供了两种用于浏览数据的方法。 您可以使用内置 MDX 查询设计器生成从多维数据库返回平展行集的查询。 或者，您可以使用 Excel 快捷方式。 当您从 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]内启动 Excel 时，Excel 将打开，并且在工作表中已有数据透视表以及与模型工作区数据库的预定义连接。  
  
Excel 通常会提供更好的浏览体验，因为您可以交互方式浏览多维数据集数据，并且使用水平轴和垂直轴来分析数据中的关系。 相比之下，MDX 查询设计器局限于单个轴。 此外，因为行集将被平展，所以，您无法获得 Excel 数据透视表提供的深入分析。 随着您向多维数据集添加更多的维度和层次结构（在以后的课程中将会这样做），对于浏览数据而言，Excel 将是首选解决方案。  
  
### <a name="to-browse-the-deployed-cube"></a>浏览部署的多维数据集  
  
1.  切换到 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] 中的“产品”维度的“维度设计器”。 为此，请双击解决方案资源管理器的“维度”节点的“产品”维度。  
  
2.  单击“浏览器”选项卡可显示“产品密钥”属性层次结构的“所有”成员。 在第 3 课中，你将定义“产品”维度的用户层次结构，利用此结构可浏览该维度。  
  
3.  切换到 [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] 中的“多维数据集设计器”。 为此，请在“解决方案资源管理器”的“多维数据集”节点中，双击“Analysis Services 教程”多维数据集。  
  
4.  选择“浏览器”选项卡，然后在设计器的工具栏上单击“重新连接”图标。  
  
    该设计器的左窗格会显示 [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Tutorial 多维数据集中的对象。 在“浏览器”选项卡的右侧有两个窗格：上部窗格是“筛选器”窗格，下部是“数据”窗格。 在接下来的课程中，您将使用多维数据集浏览器进行分析。  
  
## <a name="next-lesson"></a>下一课  
[第 3 课︰ 修改度量值、 属性和层次结构](../analysis-services/lesson-3-modifying-measures-attributes-and-hierarchies.md)  
  
## <a name="see-also"></a>另请参阅  
[MDX 查询编辑器（Analysis Services - 多维数据）](http://msdn.microsoft.com/library/777f2c23-1c1c-4b72-9d19-48a4866551f8)  
  
  
  
