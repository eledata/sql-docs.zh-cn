---
title: DropOnlyMode 元素 (DTA) |Microsoft 文档
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: sql-tools
ms.service: ''
ms.component: dta
ms.reviewer: ''
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- XML
helpviewer_keywords:
- DropOnlyMode element
ms.assetid: 80960676-7581-4074-889b-80ee665963dd
caps.latest.revision: 14
author: stevestein
ms.author: sstein
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 6c30ec1f3a06e0bb2142dd889852ddb071b68d96
ms.sourcegitcommit: b6116b434d737d661c09b78d0f798c652cf149f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="droponlymode-element-dta"></a>DropOnlyMode 元素 (DTA)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]指定数据库引擎优化顾问应只考虑在优化会话过程中删除现有索引、 索引的视图或分区。 如果指定了此优化选项，则不考虑任何新物理设计结构。  
  
## <a name="syntax"></a>语法  
  
```  
  
<DTAInput>  
...code removed...  
    <TuningOptions>  
      <DropOnlyMode>...</DropOnlyMode>  
```  
  
## <a name="element-characteristics"></a>元素特征  
 **数据类型和长度**  
  
 **默认值**  
  
 **出现次数**：可选。 对于每个 **TuningOptions** 元素只能使用一次。 如果在 **TuningOptions** 元素中指定了下列元素，则不能使用此元素：  
  
-   [FeatureSet 元素 &#40; DTA &#41;](../../tools/dta/featureset-element-dta.md)  
  
-   [分区元素 &#40; DTA &#41;](../../tools/dta/partitioning-element-dta.md)  
  
-   将 [KeepExisting 元素 (DTA)](../../tools/dta/keepexisting-element-dta.md) 设置为 **ALL**  
  
## <a name="element-relationships"></a>元素关系  
 **父元素**：[TuningOptions 元素 (DTA)](../../tools/dta/tuningoptions-element-dta.md)  
  
 **子元素**  
  
## <a name="example"></a>示例  
 以下示例说明数据库引擎优化顾问 XML 输入文件的 **TuningOptions** 部分，其中指定了 **DropOnlyMode** 。 本例中，优化时间限定为 24 小时（1440 分钟），并且所有现有的聚集索引和非聚集索引将被删除：  
  
```xml  
<TuningOptions  
  <TuningTimeInMin>1440</Name>  
  <KeepExisting>ALIGNED</KeepExisting>  
  <DropOnlyMode />  
</TuningOptions>  
```  
  
## <a name="see-also"></a>另请参阅  
 [XML 输入文件引用（数据库引擎优化顾问）](../../tools/dta/xml-input-file-reference-database-engine-tuning-advisor.md)  
  
  
