---
title: "Analysis Services 脚本项目中 SQL Server Management Studio |Microsoft 文档"
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
- scripts [Analysis Services]
- scripts [Analysis Services], projects
- projects [Analysis Services], Analysis Server Scripts project
- projects [Analysis Services], creating
- Analysis Server Scripts project
- items [Analysis Services]
ms.assetid: c4f5a06b-e2e4-4660-a3a8-6fd356742c02
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 2b8652fbb1028fa58f06d7ff165b02dc8f5fdc02
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="analysis-services-scripts-project-in-sql-server-management-studio"></a>SQL Server Management Studio 中的 Analysis Services 脚本项目
[!INCLUDE[ssas-appliesto-sqlas-all-aas](../../includes/ssas-appliesto-sqlas-all-aas.md)]

  在 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]中，您可以在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 中创建分析服务器脚本项目，将相关脚本分组到一起，以便用于开发、管理和源代码管理。 如果 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中当前未加载任何解决方案，则创建新的分析服务器脚本项目将自动创建一个新的解决方案。 否则，新的分析服务器脚本项目可以添加到现有解决方案中，或者在新的解决方案中进行创建。  
  
 您可以使用以下基本步骤在 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中创建分析服务器脚本项目：  
  
1.  在“文件”菜单上，指向 **“新建”**，然后单击 **“项目”**。  
  
     选择 **“分析服务器脚本”** 项目模板，然后为新项目指定名称和位置。  
  
2.  右键单击“连接”，在解决方案资源管理器中的分析服务器脚本项目的“连接”文件夹中新建一个连接。  
  
     此文件夹包含指向 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 实例（分析服务器脚本项目所包含的脚本可以针对其执行）的连接字符串。 一个分析服务器脚本项目中可以有多个连接，您可以在执行时选择项目包含的脚本针对其运行的连接。  
  
3.  右键单击“查询”可以在解决方案资源管理器的分析服务器脚本项目的“脚本”文件夹中创建多维表达式 (MDX)、数据挖掘扩展插件 (DMX) 和 XML for Analysis (XMLA) 脚本。
  
4.  右键单击该项目，指向“添加”，然后选择“现有项”，将杂项文件（如包含项目注释的文本文件）添加到解决方案资源管理器的分析服务器脚本项目的“杂项”文件夹中。 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]将忽略这些文件。  
  
## <a name="file-types"></a>文件类型  
 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 解决方案可以包含多种文件类型，具体取决于解决方案中包括的项目以及解决方案的各个项目中包括的项。 有关 [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]中解决方案文件类型的详细信息，请参阅 [用于管理解决方案和项目的文件](http://msdn.microsoft.com/library/e19d2859-0b97-4727-ac27-c4c226d86b2f)。 通常， [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] 解决方案中各项目的文件都存储在解决方案文件夹中，每个项目各有单独的文件夹。  
  
 分析服务器脚本项目的项目文件夹可包含下表中列出的文件类型。  
  
|文件类型|Description|  
|---------------|-----------------|  
|分析服务器脚本项目定义文件 (.ssmsasproj)|包含显示在解决方案资源管理器中的文件夹的元数据，以及指示哪些文件夹应显示项目中包含的文件的信息。<br /><br /> 项目定义文件还包含项目中包含的 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 连接的元数据，以及将这些连接与项目中所包含的脚本文件相关联的元数据。|  
|DMX 脚本文件 (.dmx)|包含一个包括在项目中的 DMX 脚本。|  
|MDX 脚本文件 (.mdx)|包含一个包括在项目中的 MDX 脚本。|  
|XMLA 脚本文件 (.xmla)|包含一个包括在项目中的 XMLA 脚本。|  
  
## <a name="analysis-services-templates"></a>Analysis Services 模板  
 向分析服务器脚本项目添加新的 MDX、DMX 或 XMLA 脚本时，您可以选择使用模板资源管理器来查找 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 模板，这些模板是演示如何执行指定操作的预定义脚本或语句的集合。 模板资源管理器在 **“视图”** 菜单上提供，并且包括用于 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]、 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]和 [!INCLUDE[ssEW](../../includes/ssew-md.md)]的模板。 有关详细信息，请参阅 [Use Analysis Services Templates in SQL Server Management Studio](../../analysis-services/instances/use-analysis-services-templates-in-sql-server-management-studio.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 SQL Server Data Tools 创建多维模型 (SSDT)](../../analysis-services/multidimensional-models/creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)   
 [多维表达式 &#40;MDX &#41;引用](../../mdx/multidimensional-expressions-mdx-reference.md)   
 [数据挖掘扩展插件 &#40; DMX &#41;引用](../../dmx/data-mining-extensions-dmx-reference.md)   
 [Analysis Services 脚本语言（支持 XMLA 的 ASSL）](../../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md)   
 [Analysis Services 脚本语言 &#40;ASSL 为 XMLA &#41;](../../analysis-services/scripting/analysis-services-scripting-language-assl-for-xmla.md)  
  
  
