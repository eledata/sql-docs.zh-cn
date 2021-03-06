---
title: DBSCHEMA_TABLES 行集 |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- DBSCHEMA_TABLES
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DBSCHEMA_TABLES rowset
ms.assetid: 14c16e6b-0aff-4ad1-b98f-cdb7df0f8d73
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: e823aca2ca72fe756fe41cabf49fe61f26cec106
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="dbschematables-rowset"></a>DBSCHEMA_TABLES 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]标识的度量值组和维度中的表作为公开[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)]。  
  
## <a name="rowset-columns"></a>行集列  
 **DBSCHEMA_TABLES**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**TABLE_CATALOG**|**DBTYPE_WSTR**|255|此对象所属目录的名称。|  
|**TABLE_SCHEMA**|**DBTYPE_WSTR**|255|此对象所属多维数据集的名称。|  
|**TABLE_NAME**|**DBTYPE_WSTR**|255|对象的名称，如果**TABLE_TYPE**是**表**。|  
|**TABLE_TYPE**|**DBTYPE_WSTR**||表的类型。<br /><br /> **表**指示对象是度量值组。<br /><br /> **系统表**指示对象是一个维度。|  
|**TABLE_GUID**|**DBTYPE_GUID**||不提供支持。|  
|**DESCRIPTION**|**DBTYPE_WSTR**||用户可以阅读的对象说明。|  
|**TABLE_PROPID**|**DBTYPE_UI4**||不提供支持。|  
|**DATE_CREATED**|**DBTYPE_DBTIMESTAMP**||不提供支持。|  
|**DATE_MODIFIED**|**DBTYPE_DBTIMESTAMP**||上次修改对象的日期。|  
|**TABLE_OLAP_TYPE**|**DBTYPE_WSTR**||对象的 OLAP 类型。<br /><br /> **MEASURE_GROUP**指示对象是度量值组。<br /><br /> **CUBE_DIMENSION**指示对象是一个维度。|  
  
 行集按排序**TABLE_TYPE**， **TABLE_CATALOG**， **TABLE_SCHEMA**，和**TABLE_NAME**。  
  
## <a name="restriction-columns"></a>限制列  
 **DBSCHEMA_TABLES**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**TABLE_CATALOG**|**DBTYPE_WSTR**|可选|  
|**TABLE_SCHEMA**|**DBTYPE_WSTR**|可选|  
|**TABLE_NAME**|**DBTYPE_WSTR**|可选|  
|**TABLE_TYPE**|**DBTYPE_WSTR**|可选|  
|**TABLE_OLAP_TYPE**|**DBTYPE_WSTR**|可选|  
  
## <a name="see-also"></a>另请参阅  
 [OLE DB 架构行集](../../../analysis-services/schema-rowsets/ole-db/ole-db-schema-rowsets.md)  
  
  
