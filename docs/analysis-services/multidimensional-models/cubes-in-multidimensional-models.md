---
title: "多维模型中的多维数据集 |Microsoft 文档"
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
- OLAP objects [Analysis Services], cubes
- cubes [Analysis Services], about cubes
- cubes [Analysis Services]
- OLAP [Analysis Services], cubes
ms.assetid: e0f7acf3-4b07-41fc-a5fc-ac30b4a56c54
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: On Demand
ms.openlocfilehash: a7a63cc3ce5a86701a20bb4083b7eb88ef1d4b66
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="cubes-in-multidimensional-models"></a>多维模型中的多维数据集
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
多维数据集是包含用于分析的信息的多维结构；多维数据集主要由维度和度量值构成。 维度定义您用来对其执行切片操作的多维数据集的结构，而度量值提供最终用户感兴趣的聚合数值。 作为逻辑结构，多维数据集允许客户端应用程序检索度量值的值，就像它们包含在多维数据集的单元中一样；将为每个可能的摘要值都定义单元。 多维数据集中的单元通过维度成员的交集定义，并且包含该特定交集处的度量值的聚合值。  
  
## <a name="benefits-of-using-cubes"></a>使用多维数据集的好处  
 多维数据集提供存储所有相关数据以便进行分析的单一位置。  
  
## <a name="components-of-cubes"></a>多维数据集的组件  
 一个多维数据集由以下组件构成：  
  
|元素|Description|  
|-------------|-----------------|  
|维度|[多维模型中的维度](../../analysis-services/multidimensional-models/dimensions-in-multidimensional-models.md)|  
|度量值和度量值组|[在多维模型中创建度量值和度量值组](../../analysis-services/multidimensional-models/create-measures-and-measure-groups-in-multidimensional-models.md)|  
|分区|[多维模型中的分区](../../analysis-services/multidimensional-models/partitions-in-multidimensional-models.md)|  
|透视|[多维模型中的透视](../../analysis-services/multidimensional-models/perspectives-in-multidimensional-models.md)|  
|层次结构|[创建用户定义的层次结构](../../analysis-services/multidimensional-models/user-defined-hierarchies-create.md)|  
|操作|[多维模型中的操作](../../analysis-services/multidimensional-models/actions-in-multidimensional-models.md)|  
|关键绩效指标 (KPI)|[关键绩效指标 &#40;Kpi &#41;多维模型中](../../analysis-services/multidimensional-models/key-performance-indicators-kpis-in-multidimensional-models.md)|  
|计算|[多维模型中的计算](../../analysis-services/multidimensional-models/calculations-in-multidimensional-models.md)|  
|翻译|[多维模型中的翻译 (Analysis Services)](../../analysis-services/multidimensional-models/translations-in-multidimensional-models-analysis-services.md)|  
  
## <a name="related-tasks"></a>相关任务  
  
|主题|Description|  
|-----------|-----------------|  
|[创建多维数据集使用多维数据集向导](../../analysis-services/multidimensional-models/create-a-cube-using-the-cube-wizard.md)|说明如何使用多维数据集向导定义多维数据集、维度、维度属性以及用户定义层次结构。|  
|[在多维模型中创建度量值和度量值组](../../analysis-services/multidimensional-models/create-measures-and-measure-groups-in-multidimensional-models.md)|介绍如何定义度量值组。|  
|[多维模型中的计算](../../analysis-services/multidimensional-models/calculations-in-multidimensional-models.md)|说明如何在 MDX 脚本中定义和配置计算。|  
|[多维模型中的操作](../../analysis-services/multidimensional-models/actions-in-multidimensional-models.md)|说明如何定义和配置操作。|  
|[多维模型中的透视](../../analysis-services/multidimensional-models/perspectives-in-multidimensional-models.md)|说明如何定义和配置透视。|  
|[定义存储的过程](../../analysis-services/multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)|说明如何使用存储过程。|  
  
  
