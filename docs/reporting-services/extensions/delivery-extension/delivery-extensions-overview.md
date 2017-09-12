---
title: "传递扩展概述 |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
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
- subscriptions [Reporting Services], delivery extensions
- delivery extensions [Reporting Services], about extensions
ms.assetid: a30600a9-bbed-4519-9426-3470ff2982e7
caps.latest.revision: 37
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: 79894381bf493132c1f73d711ecd6d1ba282401e
ms.contentlocale: zh-cn
ms.lasthandoff: 08/12/2017

---
# <a name="delivery-extensions-overview"></a>传递扩展插件概述
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]使用户能够创建和发布报表，一次创建和发布，可以传递给不同的位置。 此外，[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 包括多个传递扩展插件和一个传递 API，它们使得开发人员能够创建其他传递扩展插件，以便在 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 中进一步扩展传递的功能。  
  
 下表列出 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 随附的传递扩展插件。  
  
|传递扩展插件|Description|  
|------------------------|-----------------|  
|报表服务器电子邮件|使用 SMTP 服务器通过电子邮件将报表发送到单独用户或组。|  
|报表服务器文件共享|用于将组织内的报表分发到网络文件共享。 提供了按指定的计划自动将报表复制到文件共享的功能。|  
  
 ![Reporting Services 传递扩展体系结构](../../../reporting-services/extensions/delivery-extension/media/bk-reportservicedelivery.gif "Reporting Services 传递扩展体系结构")  
Reporting Services 传递扩展插件体系结构  
  
 传递扩展插件可以与订阅配对。 创建订阅后，用户可以选择可用的传递扩展插件之一来确定传递报表的方式。 在 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 中，订阅位于报表服务器数据库中。 发生事件时，[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 根据报表服务器数据库中包含的订阅匹配事件。 对于与此事件关联的每个订阅，报表服务器都将创建一个通知。 对于数据驱动订阅，将为每个收件人创建一个通知。 一旦创建了通知，报表服务器就调用特定的传递扩展插件，并为在通知中指定的扩展插件设置传递值。 此传递扩展插件按照所选传递扩展插件指定的方式将通知发送给用户。  
  
 传递扩展插件实现 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 传递扩展插件 API。 通过支持 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 传递扩展插件 API，传递扩展插件可以从报表服务器接收通知，并提供通知的状态。  
  
 报表服务器不为通知和报表管理传递目标。 收集目标信息是通过您在传递扩展插件中编写的代码来完成的。  
  
## <a name="subscriptions-and-delivery-extensions"></a>订阅和传递扩展插件  
 客户端应用程序通过报表服务器 Web 服务的两个方法 <xref:ReportService2010.ReportingService2010.CreateSubscription%2A> 和 <xref:ReportService2010.ReportingService2010.CreateDataDrivenSubscription%2A> 创建使用传递扩展插件的订阅。 若要修改已存在的订阅，请使用 <xref:ReportService2010.ReportingService2010.SetSubscriptionProperties%2A> 和 <xref:ReportService2010.ReportingService2010.SetDataDrivenSubscriptionProperties%2A> 方法。 当创建订阅时，用户还可以为订阅选择传递扩展插件，并为所需扩展插件设置输入值。 当用户保存订阅时，它将存储在报表服务器数据库中。 订阅基于计划或事件创建通知。 当开始传递时，所选传递扩展插件首先从配置文件加载任何配置数据。 接下来，检索订阅的扩展插件设置并设置值。 最后，调用 <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension.Deliver%2A> 方法并发送通知。  
  
## <a name="developer-requirements"></a>开发人员要求  
 开发 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 传递扩展插件要求您具备：  
  
-   一台安装了报表服务器的部署计算机。  
  
-   开发计算机与[!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)]或[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]软件开发工具包 (SDK) 安装。  
  
-   深入了解 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 特性和功能，尤其是订阅和传递。  
  
-   深入了解 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 和 Web 控件（如果您计划为报表管理器实现您自己的订阅用户界面）。  
  
-   中的开发体验[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]如语言[!INCLUDE[msCoName](../../../includes/msconame-md.md)]Visual C# 或[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET。  
  
## <a name="see-also"></a>另请参阅  
 [Implementing a Delivery Extension](../../../reporting-services/extensions/delivery-extension/implementing-a-delivery-extension.md)   
 [Reporting Services 扩展库](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  