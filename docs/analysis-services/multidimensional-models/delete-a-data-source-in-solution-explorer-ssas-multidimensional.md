---
title: 删除数据源在解决方案资源管理器 (SSAS 多维) |Microsoft 文档
ms.custom: ''
ms.date: 03/01/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: data-mining
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql13.asvs.deleteobjects.f1
helpviewer_keywords:
- data sources [Analysis Services], deleting
- deleting data sources
- removing data sources
ms.assetid: b45441ef-f909-4736-98b9-cc80d0acac99
caps.latest.revision: 46
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 480082010e78c1db2c4e90af3176b797b97f26d7
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="delete-a-data-source-in-solution-explorer-ssas-multidimensional"></a>在解决方案资源管理器中删除数据源（SSAS 多维）
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]你可以删除数据源对象从 Analysis Services 多维模型项目中永久删除。  
  
 在 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]中，数据源提供了构造数据源视图的基础，而后，数据源视图用于定义 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 项目或数据库中的维度、多维数据集和挖掘结构。 因此，删除数据源可能会导致 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 项目中的其他 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 对象无效。 您应该始终在删除对象前查看提供的依赖对象的列表。  
  
> [!IMPORTANT]  
>  无法从处于联机模式的 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 打开的 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] 数据库中删除其他对象所依赖的数据源。 要删除该数据源，必须先删除 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 数据库中所有依赖该数据源的对象。 有关联机模式的详细信息，请参阅 [Connect in Online Mode to an Analysis Services Database](../../analysis-services/multidimensional-models/connect-in-online-mode-to-an-analysis-services-database.md)。  
  
### <a name="to-delete-a-data-source"></a>删除数据源  
  
1.  在 [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]中，打开要从其中删除数据源的项目或连接到要从其中删除数据源的数据库。  
  
2.  在 **“解决方案资源管理器”**中，展开 **“数据源”** 文件夹。  
  
3.  右键单击数据源，然后单击“删除”。 **“删除对象”**  对话框将出现，其中显示您删除数据源后将失效的对象。 在单击 **“确定”** 以便删除数据源之前请仔细查看此列表。  
  
4.  保存项目。  
  
     在从 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 项目中删除数据源后，必须保存已修改的项目，否则下次打开此项目时将会收到错误，因为当项目尝试加载已删除的数据源时，此数据源的基础 XML 文件将会丢失。  
  
## <a name="see-also"></a>另请参阅  
 [多维模型中的数据源](../../analysis-services/multidimensional-models/data-sources-in-multidimensional-models.md)   
 [支持的数据源（SSAS - 多维）](../../analysis-services/multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
