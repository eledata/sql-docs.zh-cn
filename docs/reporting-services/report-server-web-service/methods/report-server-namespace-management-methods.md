---
title: "报告服务器 Namespace 管理方法 |Microsoft 文档"
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- docset-sql-devref
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- reports [Reporting Services], managing
- management methods [Reporting Services]
- methods [Reporting Services], about methods
- methods [Reporting Services]
ms.assetid: 2aa43ce9-f51e-408a-8ce0-b40d3dd62561
caps.latest.revision: 37
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: 62bb63d2625e520f4808697677c12f27b4e4ece3
ms.contentlocale: zh-cn
ms.lasthandoff: 08/12/2017

---
# <a name="report-server-namespace-management-methods"></a>报表服务器命名空间管理方法
  报表服务器管理 Web 服务包含可用于管理报表、 文件夹和报表服务器数据库中的资源的方法。  
  
|方法|操作|  
|------------|------------|  
|<xref:ReportService2010.ReportingService2010.CancelJob%2A>|取消执行作业。|  
|<xref:ReportService2010.ReportingService2010.CreateFolder%2A>|将文件夹添加到报表服务器数据库或 SharePoint 库。|  
|<xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A>|将新项添加到报表服务器数据库或 SharePoint 库。 此方法适用于**报表**，**模型**，**数据集**，**组件**，**资源**，和**数据源**项类型。|  
|M:ReportService2010.ReportingService2010.CreateReportEditSession(System.String,System.String,System.Byte[],ReportService2010.Warning[]@)|创建新的报表编辑会话。|  
|<xref:ReportService2010.ReportingService2010.DeleteItem%2A>|从报表服务器数据库或 SharePoint 库删除项。|  
|<xref:ReportService2010.ReportingService2010.FindItems%2A>|返回报表服务器数据库或 SharePoint 库中与指定的搜索条件匹配的项。|  
|<xref:ReportService2010.ReportingService2010.FireEvent%2A>|基于提供的参数触发事件。|  
|<xref:ReportService2010.ReportingService2010.GetExtensionSettings%2A>|返回针对给定扩展插件的设置列表。|  
|<xref:ReportService2010.ReportingService2010.GetItemType%2A>|检索报表服务器数据库或 SharePoint 库中某一项的类型（如果该项存在）。|  
|<xref:ReportService2010.ReportingService2010.GetProperties%2A>|对于报表服务器数据库或 SharePoint 库中的项返回一个或多个属性的值。|  
|<xref:ReportService2010.ReportingService2010.GetItemDefinition%2A>|检索项的定义或内容。 此方法适用于**报表**，**模型**，**数据集**，**组件**，**资源**，和**数据源**项类型。|  
|<xref:ReportService2010.ReportingService2010.GetItemReferences%2A>|返回与项关联的目录项引用的列表。|  
|<xref:ReportService2010.ReportingService2010.GetReportServerConfigInfo%2A>|返回有关连接的报表服务器实例或扩展部署中所有报表服务器实例的信息。|  
|<xref:ReportService2010.ReportingService2010.GetSystemProperties%2A>|返回一个或多个系统属性。|  
|<xref:ReportService2010.ReportingService2010.ListChildren%2A>|获取指定的文件夹的子节点列表。|  
|<xref:ReportService2010.ReportingService2010.ListDatabaseCredentialRetrievalOptions%2A>|返回支持的凭据检索选项列表。|  
|<xref:ReportService2010.ReportingService2010.ListEvents%2A>|返回在报表服务器配置文件中出现的事件扩展插件的列表。|  
|<xref:ReportService2010.ReportingService2010.ListJobs%2A>|返回报表服务器上运行的作业的列表。|  
|<xref:ReportService2010.ReportingService2010.ListExtensions%2A>|返回为给定扩展插件类型配置的扩展插件的列表。|  
|<xref:ReportService2010.ReportingService2010.ListExtensionTypes%2A>|返回支持的扩展插件类型的列表。|  
|<xref:ReportService2010.ReportingService2010.ListItemTypes%2A>|返回支持的目录项类型的列表。|  
|<xref:ReportService2010.ReportingService2010.ListJobActions%2A>|返回支持的作业操作的列表。|  
|<xref:ReportService2010.ReportingService2010.ListJobStates%2A>|返回支持的作业状态的列表。|  
|<xref:ReportService2010.ReportingService2010.ListJobTypes%2A>|返回支持的作业类型的列表。|  
|<xref:ReportService2010.ReportingService2010.ListParents%2A>|检索给定项的父项。|  
|<xref:ReportService2010.ReportingService2010.ListSecurityScopes%2A>|返回支持的安全范围的列表。|  
|<xref:ReportService2010.ReportingService2010.Logoff%2A>|注销发出 Web 服务请求的当前用户。 此方法仅适用于本机模式。|  
|<xref:ReportService2010.ReportingService2010.LogonUser%2A>|使用户登录，然后验证对报表服务器 Web 服务的用户请求。 此方法仅适用于本机模式。|  
|<xref:ReportService2010.ReportingService2010.SetItemReferences%2A>|设置与项关联的目录项。|  
|<xref:ReportService2010.ReportingService2010.MoveItem%2A>|移动和/或重命名某项。|  
|<xref:ReportService2010.ReportingService2010.SetProperties%2A>|设置项的一个或多个属性。|  
|<xref:ReportService2010.ReportingService2010.SetItemDefinition%2A>|设置指定项的定义或内容。 此方法适用于**报表**，**模型**，**数据集**，**组件**，**资源**，和**数据源**项类型。|  
|<xref:ReportService2010.ReportingService2010.SetSystemProperties%2A>|在报表服务器或 SharePoint 场中设置一个或多个系统属性。|  
|<xref:ReportService2010.ReportingService2010.ValidateExtensionSettings%2A>|验证 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 扩展插件设置。|  
  
## <a name="see-also"></a>另请参阅  
 [使用 Web 服务和.NET Framework 构建应用程序](../../../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)   
 [报表服务器 Web 服务](../../../reporting-services/report-server-web-service/report-server-web-service.md)   
 [报表服务器 Web 服务方法](../../../reporting-services/report-server-web-service/methods/report-server-web-service-methods.md)   
 [技术参考 &#40;SSRS &#41;](../../../reporting-services/technical-reference-ssrs.md)  
  
  