---
title: "多维数据集单元格 (Analysis Services-多维数据) |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: 
ms.component: 
ms.reviewer: 
ms.suite: pro-bi
ms.technology: 
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- storing data [Analysis Services], cells
- hierarchies [Analysis Services], cells
- OLAP objects [Analysis Services], cells
- data members [Analysis Services]
- cubes [Analysis Services], cells
- empty cells [Analysis Services]
- nonleaf members
- cubes [Analysis Services], examples
- storage [Analysis Services], cells
- nonleaf cells
- calculated cells [Analysis Services]
- dimensions [Analysis Services], cells
- cells [Analysis Services]
- leaf members
- leaf cells
ms.assetid: 9945773c-a43b-40d4-91cf-3d2ebc90bca5
caps.latest.revision: 
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 6542727b42e98fa73f2e485f0bf88426c442df2d
ms.sourcegitcommit: 7519508d97f095afe3c1cd85cf09a13c9eed345f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2018
---
# <a name="cube-cells-analysis-services---multidimensional-data"></a>多维数据集单元（Analysis Services - 多维数据）
[!INCLUDE[ssas-appliesto-sqlas](../../includes/ssas-appliesto-sqlas.md)]
多维数据集由单元组成，单元按度量值组和维度进行组织。 单元表示多维数据集中来自多维数据集内每个维度的一个成员的唯一逻辑交集。 例如，以下关系图说明的多维数据集包含了一个有两个度量值的度量值组，它们通过三个名为“源”、“路线”和“时间”的维度组织在一起。  
  
 ![标识一个单元格的多维数据集关系图](../../analysis-services/multidimensional-models-olap-logical-cube-objects/media/as-cubeintro5.gif "标识单个单元格的多维数据集关系图")  
  
 此关系图中的单个带阴影的单元是下列成员的交集：  
  
-   “路线”维度的空运成员。  
  
-   “源”维度的非洲成员。  
  
-   “时间”维度的第四季度成员。  
  
-   包度量值。  
  
## <a name="leaf-and-nonleaf-cells"></a>叶和非叶单元  
 可以用几种方式获得多维数据集中的单元的值。 在前面的示例中，单元格中的值可以直接从检索事实数据表的多维数据集，因为用于标识该单元格的所有成员都是*叶成员*。 从层次结构上看，叶成员没有子成员，并且通常引用维度表中的单个记录。 这种类型的单元格称为*叶单元格*。  
  
 但是，一个单元格也都可以通过使用识别*非叶成员*。 非叶成员是有一个或多个子成员的成员。 在这种情况下，通常基于与非叶成员关联的子成员的聚合派生单元的值。 例如，下列成员和维度的交集是指其值由聚合提供的单元：  
  
-   “路线”维度的空运成员。  
  
-   “源”维度的非洲成员。  
  
-   “时间”维度的下半年成员。  
  
-   包成员。  
  
 “时间”维度的下半年成员是非叶成员。 因此，与它关联的所有值必须都是聚合值，如以下关系图所示。  
  
 ![第三和第四季度单元格，第二个半成员](../../analysis-services/multidimensional-models-olap-logical-cube-objects/media/as-cubeintro6.gif "第三和第四季度单元格，第二个半成员")  
  
 假定“第三季度”和“第四季度”成员的聚合就是汇总，则指定单元的值是 400，即上面关系图中所有带阴影叶单元的总和。 由于单元格的值派生自其他单元的聚合，被认为是指定的单元格*非叶单元格*。  
  
 除了自定义成员以外，为使用自定义汇总和成员组的成员所派生的单元值将以相似方式进行处理。 但是，为计算成员而派生的单元值将完全基于用来定义计算成员的多维表达式 (MDX)；在某些情况下，可能不涉及实际的单元数据。 有关详细信息，请参阅[父子维度中的自定义汇总运算符](../../analysis-services/multidimensional-models/parent-child-dimension-attributes-custom-rollup-operators.md)，[定义自定义成员公式](../../analysis-services/multidimensional-models/attribute-properties-define-custom-member-formulas.md)，和[计算](../../analysis-services/multidimensional-models-olap-logical-cube-objects/calculations.md)。  
  
## <a name="empty-cells"></a>空单元  
 并不是多维数据集中的每个单元都必须要包含值；多维数据集中可以有没有数据的交集。 这些称为空单元的交集经常出现在多维数据集中，因为并非多维数据集中带有度量值的维度属性的每个交集都在事实数据表中包含一个相应的记录。 多维数据集中的单元格总数多维数据集中的空单元格的比率通常称为*稀疏度*多维数据集。  
  
 例如，下列关系图中所示的多维数据集的结构与本主题中的其他示例类似。 但是，在本示例中，在第三季度没有到非洲的空运或者在第四季度没有到澳大利亚的空运。 由于事实数据表中无数据支持这些维度和度量值的交集，所以这些交集的单元为空。  
  
 ![用于标识空单元格的多维数据集关系图](../../analysis-services/multidimensional-models-olap-logical-cube-objects/media/as-cubeintro7.gif "标识空单元格的多维数据集关系图")  
  
 在[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]，空单元格是具有特殊质量一个单元格。 因为空单元可扭曲交叉联接、计数等的结果，因此为了进行计算，许多 MDX 函数都提供了忽略空单元的功能。 有关详细信息，请参阅[多维表达式 &#40;MDX &#41;引用](../../mdx/multidimensional-expressions-mdx-reference.md)，和[MDX &#40; 中的重要概念Analysis Services &#41;](../../analysis-services/multidimensional-models/mdx/key-concepts-in-mdx-analysis-services.md).  
  
## <a name="security"></a>Security  
 对单元数据的访问是在角色级别通过 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] 来进行管理的，并且可以使用 MDX 表达式进行严格控制。 有关详细信息，请参阅[授予维度数据 &#40; 的自定义访问权限Analysis Services &#41;](../../analysis-services/multidimensional-models/grant-custom-access-to-dimension-data-analysis-services.md)，和[授予单元数据 &#40; 的自定义访问权限Analysis Services &#41;](../../analysis-services/multidimensional-models/grant-custom-access-to-cell-data-analysis-services.md).  
  
## <a name="see-also"></a>另请参阅  
 [多维数据集存储 &#40;Analysis Services-多维数据 &#41;](../../analysis-services/multidimensional-models-olap-logical-cube-objects/cube-storage-analysis-services-multidimensional-data.md)   
 [聚合和聚合设计](../../analysis-services/multidimensional-models-olap-logical-cube-objects/aggregations-and-aggregation-designs.md)  
  
  
