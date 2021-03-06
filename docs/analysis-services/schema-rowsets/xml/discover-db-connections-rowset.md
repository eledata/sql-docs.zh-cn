---
title: DISCOVER_DB_CONNECTIONS 行集 |Microsoft 文档
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
- DISCOVER_DB_CONNECTIONS rowset
ms.assetid: 12a51a4e-5f3d-4449-9d94-7836fea1bc8b
caps.latest.revision: 17
author: Minewiskan
ms.author: owend
manager: kfile
ms.workload: Inactive
ms.openlocfilehash: 8a932cfa872e0cceed0b132f486349716ba4210b
ms.sourcegitcommit: f486d12078a45c87b0fcf52270b904ca7b0c7fc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2018
---
# <a name="discoverdbconnections-rowset"></a>DISCOVER_DB_CONNECTIONS 行集
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]提供有关当前打开的连接，可从服务器到数据库的资源使用情况和活动信息。  
  
## <a name="rowset-columns"></a>行集列  
 **DISCOVER_DB_CONNECTIONS**行集包含以下各列。  
  
|列名|类型指示符|长度|Description|  
|-----------------|--------------------|------------|-----------------|  
|**CONNECTION_CATALOG_NAME**|**DBTYPE_WSTR**||当前连接到的数据库的数据库名称。|  
|**CONNECTION_ID**|**DBTYPE_I4**||标识连接的唯一编号。|  
|**CONNECTION_IDLE_TIME_MS**|**是 DBTYPE_I8**||自连接开始后的空闲时间（毫秒）。|  
|**CONNECTION_IN_USE**|**DBTYPE_I4**||指示连接是活动状态 (1) 还是空闲状态 (0)。|  
|**CONNECTION_LAST_COMMAND_END_TIME**|**DBTYPE_DBTIMESTAMP**||上次命令执行结束时的服务器 UTC 日期和时间。|  
|**CONNECTION_LAST_COMMAND_START_TIME**|**DBTYPE_DBTIMESTAMP**||上次命令启动执行时的服务器 UTC 日期和时间。|  
|**CONNECTION_SERVER_NAME**|**DBTYPE_WSTR**||当前连接到的服务器的名称。|  
|**CONNECTION_SPID**|**DBTYPE_I4**||会话 ID。|  
|**CONNECTION_START_TIME**|**DBTYPE_DBTIMESTAMP**||启动连接时的服务器 UTC 日期和时间。|  
|**CONNECTION_USAGE_TIME_MS**|**是 DBTYPE_I8**||自连接开始后的连接活动时间（毫秒）。|  
  
 未对此架构行集进行排序。  
  
> [!IMPORTANT]  
>  **DISCOVER_DB_CONNECTIONS**行集将仅显示信息时服务连接到关系数据源。  
  
## <a name="restriction-columns"></a>限制列  
 **DISCOVER_DB_CONNECTIONS**行集可限制在下表中列出的列。  
  
|列名|类型指示符|限制状态|  
|-----------------|--------------------|-----------------------|  
|CONNECTION_ID|DBTYPE_I4|可选。|  
|CONNECTION_IN_USE|DBTYPE_I4|可选。|  
|CONNECTION_SERVER_NAME|DBTYPE_WSTR|可选。|  
|CONNECTION_CATALOG_NAME|DBTYPE_WSTR|必需的。|  
|CONNECTION_SPID|DBTYPE_I4|可选。|  
  
## <a name="see-also"></a>另请参阅  
 [XML for Analysis 架构行集](../../../analysis-services/schema-rowsets/xml/xml-for-analysis-schema-rowsets.md)  
  
  
