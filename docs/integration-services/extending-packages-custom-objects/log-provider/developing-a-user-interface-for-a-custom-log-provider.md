---
title: "为自定义日志提供程序开发用户界面 | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: extending-packages-custom-objects
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- custom user interface [Integration Services], custom log providers
- custom log providers [Integration Services], developing custom user interface
ms.assetid: 6fd2d269-d87a-4134-82a1-40a09b3b5453
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 79eb2cb9fef0f8d957709e77c0a35fb8f4de0789
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="developing-a-user-interface-for-a-custom-log-provider"></a>为自定义日志提供程序开发用户界面
  许多 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] 日志提供程序都有一个自定义用户界面，该界面实现 <xref:Microsoft.SqlServer.Dts.Runtime.Design.IDtsLogProviderUI>，并用已筛选的可用连接管理器下拉列表替换“配置 SSIS 日志”对话框中的“配置”文本框。 但是，[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] 中不实现自定义日志提供程序的自定义用户界面。  
  
## <a name="see-also"></a>另请参阅  
 [创建自定义日志提供程序](../../../integration-services/extending-packages-custom-objects/log-provider/creating-a-custom-log-provider.md)   
 [编写自定义日志提供程序代码](../../../integration-services/extending-packages-custom-objects/log-provider/coding-a-custom-log-provider.md)  
  
  
