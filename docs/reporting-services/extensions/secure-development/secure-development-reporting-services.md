---
title: "安全开发 (Reporting Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.service: 
ms.component: extensions
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to: SQL Server 2016 Preview
helpviewer_keywords:
- development security [Reporting Services]
- security [Reporting Services], development
- security [Reporting Services], strategies
ms.assetid: 12161a6c-b93b-4312-9d27-0c922561eb9b
caps.latest.revision: "15"
author: markingmyname
ms.author: maghan
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 1e9152b933bbb6a021b232a7271d412c30169b5d
ms.sourcegitcommit: 7e117bca721d008ab106bbfede72f649d3634993
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="secure-development-reporting-services"></a>安全开发 (Reporting Services)
  [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 提供了一个功能强大的安全系统，该系统可以在一个受到严格约束并由管理员定义的安全上下文中运行代码。 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 使用 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 安全系统，该系统也称为“代码访问安全”（或“基于证据的安全”）。 对于代码访问安全性，可以信任用户访问某个资源，但是如果用户执行的代码不受信任，则会拒绝其访问该资源。  
  
 基于代码而不是基于特定用户的安全性允许表达您为 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 开发的自定义程序集或数据、传递、呈现和安全扩展插件的安全性。 您的扩展代码可由任何数量的 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 用户执行，所有这些用户在开发时都是未知的。 您开发的自定义程序集或扩展插件需要 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 中的特定安全策略。 这些安全策略在 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 中表示为类型。 有关代码访问安全性的详细信息，请参阅 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 文档中的“代码访问安全性”。  
  
## <a name="in-this-section"></a>本节内容  
 [Reporting Services 中的代码访问安全性](../../../reporting-services/extensions/secure-development/code-access-security-in-reporting-services.md)  
 介绍针对 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 中的自定义程序集和扩展插件的代码访问安全性和策略配置。  
  
 [了解安全策略](../../../reporting-services/extensions/secure-development/understanding-security-policies.md)  
 介绍 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 中的各种程序集类型以及代码访问安全性如何影响代码权限。  
  
 [使用 Reporting Services 安全策略文件](../../../reporting-services/extensions/secure-development/using-reporting-services-security-policy-files.md)  
 介绍不同的 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 组件和相应的策略配置文件。  
  
  
