---
title: "脚本组件中的日志记录 | Microsoft Docs"
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.prod_service: integration-services
ms.service: 
ms.component: extending-packages-scripting
ms.reviewer: 
ms.suite: sql
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- Script component [Integration Services], logging
ms.assetid: 17c19787-379e-43fe-9107-e36e17ecda53
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: b8673343ce198cdf61f7726888694045d4fff4df
ms.sourcegitcommit: 9e6a029456f4a8daddb396bc45d7874a43a47b45
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2018
---
# <a name="logging-in-the-script-component"></a>脚本组件中的日志记录
  使用 [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] 包中的日志记录可以记录预定义的事件或用户定义的消息，从而将有关执行进度、结果和问题的详细信息保存下来，以供日后分析。 脚本组件可以使用 ScriptMain 类的 <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> 方法记录用户定义的数据。 如果启用了日志记录，并且已选择 ScriptComponentLogEntry 事件登录“配置 SSIS 日志”对话框的“详细信息”选项卡，调用一次 <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> 方法会将事件信息存储在为数据流任务配置的所有日志提供程序中。  
  
 下面是一个简单的日志记录示例：  
  
 `Dim bt(0) As Byte`  
  
 `Me.Log("Test Log Event", _`  
  
 `0, _`  
  
 `bt)`  
  
> [!NOTE]  
>  尽管可以直接从脚本组件执行日志记录，但是您可能希望考虑实现事件，而不是日志记录。 如果使用事件，不仅能够启用事件消息的日志记录，而且能够通过默认的或用户定义的事件处理程序响应事件。  
  
 有关日志记录的详细信息，请参阅 [Integration Services (SSIS) 日志记录](../../../integration-services/performance/integration-services-ssis-logging.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Integration Services (SSIS) 日志记录](../../../integration-services/performance/integration-services-ssis-logging.md)  
  
  
