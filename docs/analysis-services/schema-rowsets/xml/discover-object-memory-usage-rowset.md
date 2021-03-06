---
title: DISCOVER_OBJECT_MEMORY_USAGE 行集 |Microsoft 文档
ms.custom: ''
ms.date: 03/06/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DISCOVER_OBJECT_MEMORY_USAGE rowset
ms.assetid: 211cfa04-7bd6-43fe-8bd5-bfbff78bdafb
caps.latest.revision: 13
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 9be5091d26d264d71dad5e6892f7f8d7448d83c4
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="discoverobjectmemoryusage-rowset"></a>DISCOVER_OBJECT_MEMORY_USAGE 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]提供有关对象所使用的内存资源的信息。  
  
## <a name="rowset-columns"></a>行集列  
 **DISCOVER_OBJECT_MEMORY_USAGE**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**OBJECT_PARENT_PATH**|**DBTYPE_WSTR**||当前对象的父路径。|  
|**OBJECT_ID**|**DBTYPE_WSTR**||创建时定义的对象的 ID。|  
|**OBJECT_MEMORY_SHRINKABLE**|**是 DBTYPE_I8**||当前对象直接拥有的所有可收缩对象使用的内存总量（字节）。 当前值不包括从归当前对象拥有的命名对象的对象的内存。|  
|**OBJECT_MEMORY_NONSHRINKABLE**|**是 DBTYPE_I8**||当前对象直接拥有的所有不可收缩对象的内存量（字节）。 当前值不包括当前对象拥有的命名对象所拥有的对象的内存。|  
|**OBJECT_VERSION**|**DBTYPE_I4**||对象的元数据版本号。 每次更改对象时，此编号随之发生变化。|  
|**OBJECT_DATA_VERSION**|**DBTYPE_I4**||对象中数据的沿袭编号。 每次处理对象时，此编号随之递增。|  
|**OBJECT_TYPE_ID**|**DBTYPE_I4**||保留以供内部使用。|  
|**OBJECT_TIME_CREATED**|**DBTYPE_DBTIMESTAMP**||创建对象时的 UTC 服务器时间。|  
  
 未对此架构行集进行排序。  
  
## <a name="restriction-columns"></a>限制列  
 **DISCOVER_OBJECT_MEMORY_USAGE**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**OBJECT_PARENT_PATH**|**DBTYPE_WSTR**|可选。|  
|**OBJECT_ID**|**DBTYPE_WSTR**|可选|  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis 架构行集](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
