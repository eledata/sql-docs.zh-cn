---
title: "Power Pivot 数据刷新 |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: data-mining
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 22a4a92f63616664ff5018d8a440e437879c7225
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="power-pivot-data-refresh"></a>Power Pivot 数据刷新
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
在你创建包含 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 数据的某一工作簿后，可能希望通过重新运行查询或命令从你最初用于创建该工作簿的数据源获取更新的信息，从而定期刷新数据。 此过程称作 **数据刷新**，并且可以在 [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)]中按需刷新数据，或者作为在 SharePoint 场中的应用程序服务器上以 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 进程形式运行的定期操作来刷新数据。 有关详细信息，请参阅：  
  
-   [使用 SharePoint 2010 进行 Power Pivot 数据刷新](http://msdn.microsoft.com/en-us/01b54e6f-66e5-485c-acaa-3f9aa53119c9)  
  
-   [配置 Power Pivot 无人参与的数据刷新帐户 (Power Pivot for SharePoint)](http://msdn.microsoft.com/en-us/81401eac-c619-4fad-ad3e-599e7a6f8493)  
  
-   [为 Power Pivot 数据刷新配置存储的凭据 (Power Pivot for SharePoint)](http://msdn.microsoft.com/en-us/987eff0f-bcfe-4bbd-81e0-9aca993a2a75)  
  
-   [计划数据刷新 (Power Pivot for SharePoint)](http://msdn.microsoft.com/en-us/8571208f-6aae-4058-83c6-9f916f5e2f9b)  
  
-   [查看数据刷新历史记录 (PowerPivot for SharePoint)](../../analysis-services/power-pivot-sharepoint/view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]  
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] 和 SharePoint Server 2013 Excel Services 将不同的体系结构用于 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 数据模型的数据刷新。 SharePoint 2013 支持的体系结构利用 Excel Services 作为主要组件加载 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 数据模型。 以前使用的数据刷新体系结构依赖在 SharePoint 模式下运行 [!INCLUDE[ssGemini](../../includes/ssgemini-md.md)] 系统服务和 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 的服务器来加载数据模型。 有关详细信息，请参见以下内容：  
>   
>  -   [使用 SharePoint 2013 进行 Power Pivot 数据刷新](../../analysis-services/power-pivot-sharepoint/power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [升级工作簿和计划的数据刷新 (SharePoint 2013)](../../analysis-services/instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  
