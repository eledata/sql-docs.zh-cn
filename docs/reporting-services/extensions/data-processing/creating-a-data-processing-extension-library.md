---
title: "创建数据处理扩展库 |Microsoft 文档"
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
- data processing extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 82f4b71b-dd39-467d-8d8c-6771eb2b12de
caps.latest.revision: 39
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: a6aab5e722e732096e9e4ffdf458ac25088e09ae
ms.openlocfilehash: f8b4f2e9254eb34745d36ccbffe36c21fdb0d75d
ms.contentlocale: zh-cn
ms.lasthandoff: 08/12/2017

---
# <a name="creating-a-data-processing-extension-library"></a>创建数据处理扩展插件库
  您创建的每个 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 数据处理扩展插件都应分配到唯一的命名空间并被内置到某个库或程序集文件中。 命名空间的确切名称并不重要，但命名空间必须是唯一的且不能与任何其他扩展插件共享。 [!INCLUDE[msCoName](../../../includes/msconame-md.md)] 可以将命名空间 <xref:Microsoft.ReportingServices.DataProcessing> 用于 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 提供的数据处理扩展插件。 您应该为公司的数据处理扩展插件创建您自己的唯一命名空间。  
  
 以下示例说明开始某个 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 数据处理扩展插件的代码，此扩展插件使用包含数据处理接口和任何实用工具类的命名空间。  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.DataProcessing  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.DataProcessing;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 当编译 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 数据处理扩展插件时，因为此处包含数据处理扩展插件接口，所以您必须向编译器提供对于 Microsoft.ReportingServices.Interfaces.dll 的引用。 实现数据处理扩展插件接口需要 <xref:Microsoft.ReportingServices.DataProcessing> 命名空间，而实现 <xref:Microsoft.ReportingServices.Interfaces> 接口需要 <xref:Microsoft.ReportingServices.Interfaces.IExtension> 命名空间。 例如，如果扩展名为 .cs 的所有文件（其中包含实现以 C# 编写的 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] 数据处理扩展插件的代码）都位于单个目录中，则将从该目录发出以下命令，以编译存储在 CompanyName.ExtensionName.dll 中的文件。  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 下面的代码示例显示将用于命令[!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]带有扩展名的文件。 vb.  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  还可以使用 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 设计、开发和生成数据处理扩展插件。 有关在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中开发程序集的详细信息，请参阅 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 文档。  
  
## <a name="see-also"></a>另请参阅  
 [Reporting Services 扩展插件](../../../reporting-services/extensions/reporting-services-extensions.md)   
 [实现数据处理扩展插件](../../../reporting-services/extensions/data-processing/implementing-a-data-processing-extension.md)   
 [Reporting Services 扩展库](../../../reporting-services/extensions/reporting-services-extension-library.md)  
  
  