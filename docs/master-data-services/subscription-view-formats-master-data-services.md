---
title: "订阅视图格式 (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-non-specified
ms.prod_service: mds
ms.service: 
ms.component: non-specific
ms.reviewer: 
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff1e2566-ac8f-467d-a6d9-12c3f13879b9
caps.latest.revision: 
author: leolimsft
ms.author: lle
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 7f5d996cc9ccbf7f131056e7b02a7f756d048e02
ms.sourcegitcommit: 6ac1956307d8255dc544e1063922493b30907b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="subscription-view-formats-master-data-services"></a>订阅视图格式 (Master Data Services)
  基于您选择的实体或派生层次结构，为订阅视图提供以下格式。  
  
## <a name="subscription-view-formats"></a>订阅视图格式  
  
|“属性”|Description|  
|----------|-----------------|  
|**叶成员**|包含叶成员及其关联的属性值。|  
|**叶成员历史记录**|包含叶成员历史数据及其关联的属性值。 视图格式是缓慢更改维度类型 4 样式。|  
|**叶成员 SCD 类型 2**|包含叶成员历史数据和当前数据及其关联的属性值。 视图格式是缓慢更改维度类型 2 样式。|  
|**合并成员**|包含合并成员及其关联的属性值。|  
|**合并成员历史记录**|包含合并成员历史数据及其关联的属性值。 视图格式是缓慢更改维度类型 4 样式。|  
|**合并成员 SCD 类型 2**|包含合并成员历史数据和当前数据及其关联的属性值。 视图格式是缓慢更改维度类型 2 样式。|  
|**集合成员身份**|包含集合列表及其关联的属性值。|  
|**集合**|包含集合列表、每个集合中的成员以及权重值和排序顺序。|  
|**集合成员历史记录**|包含集合成员历史数据及其关联的属性值。 视图格式是缓慢更改维度类型 4 样式。|  
|**集合成员 SCD 类型 2**|包含集合成员历史数据和当前数据及其关联的属性值。 视图格式是缓慢更改维度类型 2 样式。|  
|**显式父子**|包含实体的显式层次结构，以父子格式显示。|  
|**显式级别**|包含实体的显式层次结构，以级别格式显示。|  
|**派生的父子（派生层次结构视图）**|包含派生层次结构，以父子格式显示。|  
|**派生级别（派生层次结构视图）**|包含派生层次结构，以级别格式显示。|  
  
## <a name="see-also"></a>另请参阅  
 [概述：导出数据 (Master Data Services)](../master-data-services/overview-exporting-data-master-data-services.md)   
 [创建订阅视图以导出数据 (Master Data Services)](../master-data-services/create-a-subscription-view-to-export-data-master-data-services.md)  
  
  
