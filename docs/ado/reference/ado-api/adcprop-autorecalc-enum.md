---
title: ADCPROP_AUTORECALC_ENUM | Microsoft Docs
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
f1_keywords:
- ADCPROP_AUTORECALC_ENUM
helpviewer_keywords:
- ADCPROP_AUTORECALC_ENUM [ADO]
ms.assetid: ded4f087-87b9-4efa-8026-bde53d3e9e8a
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: febcd58f0ae5fb96f40708712520ea8d0bcd7d0b
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="adcpropautorecalcenum"></a>ADCPROP_AUTORECALC_ENUM
指定何时[MSDataShape](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)提供程序重新计算在分层记录集中的聚合和计算列。  
  
 这些常量仅用于**MSDataShape**提供程序和**记录集**"**自动重新计算**"动态属性，这在中引用[ADO动态属性索引](../../../ado/reference/ado-api/ado-dynamic-property-index.md)和中有案可稽[Microsoft 游标服务用于 OLE DB](../../../ado/guide/appendixes/microsoft-cursor-service-for-ole-db-ado-service-component.md)或[用于 OLE DB 的 Microsoft 数据调整服务](../../../ado/guide/appendixes/microsoft-data-shaping-service-for-ole-db-ado-service-provider.md)文档。  
  
|常量|“值”|Description|  
|--------------|-----------|-----------------|  
|**adRecalcAlways**|1|默认值。 每当重新计算**MSDataShape**提供程序确定取决于计算的列的值已更改。|  
|**adRecalcUpFront**|0|仅在最初生成层次结构时计算**记录集**。|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 等效项  
 这些常量没有 ADO/WFC 等效项。
