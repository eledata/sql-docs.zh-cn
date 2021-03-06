---
title: "在报表中添加钻取操作（报表生成器和 SSRS）| Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.service: 
ms.component: report-design
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 153729c4-d01e-4629-b78f-0cfd5a7f83da
caps.latest.revision: "9"
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: 668cf69ec377fa01b494aacde2a56f0579deed1e
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="add-a-drillthrough-action-on-a-report-report-builder-and-ssrs"></a>在报表中添加钻取操作（报表生成器和 SSRS）
  单击主报表中的链接时打开的报表称为“钻取报表” 。 此钻取链接启用了一个钻取操作。  
  
 钻取报表必须发布到与主报表相同的报表服务器上，但可位于不同的文件夹中。 可以向具有 **“操作”** 属性的任何项添加钻取链接，例如文本框、图像或图表中的数据点。  
  
 若要为某个报表添加钻取链接，必须首先创建主报表将链接到的钻取报表。 钻取报表通常包含原始摘要报表中包含的某项的详细信息，并且经常包含一些参数，将基于从主报表传递给钻取报表的这些参数来筛选钻取报表。 有关创建钻取报表的详细信息，请参阅[钻取报表（报表生成器和 SSRS）](../../reporting-services/report-design/drillthrough-reports-report-builder-and-ssrs.md)。  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-drillthrough-action"></a>添加钻取操作  
  
1.  在“设计”视图中，右键单击要添加链接的文本框、图像或图表，然后单击“属性”。  
  
2.  在项的 **“属性”** 对话框中，单击 **“操作”**。  
  
3.  选择 **“转到报表”**。 其他部分将显示在此选项的对话框中。  
  
4.  在 **“指定报表”**中，单击 **“浏览”** 以查找要跳转到的报表，或键入报表的名称。 也可以单击表达式 (**fx**) 按钮为该报表名创建表达式。  
  
     对于本机模式和 SharePoint 集成模式，钻取报表的路径格式有所不同。 如果浏览到报表，则将提供正确格式的路径。 有关详细信息，请参阅[指定外部项的路径（报表生成器和 SSRS）](../../reporting-services/report-design/specifying-paths-to-external-items-report-builder-and-ssrs.md)。  
  
     如果必须为钻取报表指定参数，请执行下一个步骤。  
  
5.  在 **“使用这些参数运行报表”**中，单击 **“添加”**。 将向参数网格添加一个新行。  
  
    -   在“名称”文本框中，单击下拉列表或键入钻取报表中的报表参数名称。  
  
        > [!NOTE]  
        >  参数列表中的名称必须与目标报表中的期望参数完全匹配。 例如，参数名称必须大小写格式匹配。 如果名称不匹配，或者并未列出某个预期的参数，则钻取报表将出错。  
  
    -   在 **“值”**中，键入或选择要传递给钻取报表中的参数的值。  
  
        > [!NOTE]  
        >  值可以包含其计算结果将传递到报表参数的表达式。 值列表中的表达式包括当前报表的字段列表。  
  
     有关如何在报表中隐藏参数的信息，请参阅[添加、更改或删除报表参数（报表生成器和 SSRS）](../../reporting-services/report-design/add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)。  
  
6.  （可选）对于文本框，通过更改功能区的“主文件夹”选项卡上的文本颜色和效果有助于向用户指示该文本是一个链接。  
  
7.  若要测试该链接，请运行报表，然后单击对其设置此链接的报表项。  
  
## <a name="see-also"></a>另请参阅  
 [“操作属性”对话框（报表生成器和 SSRS）](http://msdn.microsoft.com/library/2c5d915b-4f97-42cf-b8f1-49ca3ff3d0f9)   
 [设置图表上数据点的格式（报表生成器和 SSRS）](../../reporting-services/report-design/formatting-data-points-on-a-chart-report-builder-and-ssrs.md)   
 [在序列上显示工具提示（报表生成器和 SSRS）](../../reporting-services/report-design/show-tooltips-on-a-series-report-builder-and-ssrs.md)  
  
  
