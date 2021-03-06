---
title: DBSCHEMA_CATALOGS 行集 |Microsoft 文档
ms.custom: ''
ms.date: 03/03/2017
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
- DBSCHEMA_CATALOGS
apitype: NA
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- DBSCHEMA_CATALOGS rowset
ms.assetid: f02dc75d-5442-4eea-b33a-567dc816be7a
caps.latest.revision: 31
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 493ffd66eb4bcddd0e4aaef7c79c4c771520be92
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="dbschemacatalogs-rowset"></a>DBSCHEMA_CATALOGS 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]标识与从数据库管理系统 (DBMS) 可访问的目录关联的物理属性。  
  
## <a name="rowset-columns"></a>行集列  
 **DBSCHEMA_CATALOGS**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|255|目录名称。 不可为 null。|  
|**DESCRIPTION**|**DBTYPE_WSTR**||可读的表说明。|  
|**角色**|**DBTYPE_WSTR**||当前用户所属角色的逗号分隔列表。<br /><br /> 星号 (\*) 是包括作为角色，如果当前用户是服务器或数据库管理员。<br /><br /> **用户名**追加到**角色**如果角色之一使用动态安全。|  
|**DATE_MODIFIED**|**DBTYPE_DBTIMESTAMP**||相应目录上次修改的日期。|  
  
 行集按排序**CATALOG_NAME**。  
  
## <a name="restriction-columns"></a>限制列  
 **DBSCHEMA_CATALOGS**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|**CATALOG_NAME**|**DBTYPE_WSTR**|可选|  
  
## <a name="see-also"></a>另请参阅  
 [OLE DB 架构行集](../../../analysis-services/schema-rowsets/ole-db/ole-db-schema-rowsets.md)  
  
  
