---
title: SearchDirectionEnum | Microsoft Docs
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
- SearchDirectionEnum
helpviewer_keywords:
- SearchDirectionEnum enumeration [ADO]
ms.assetid: 81272ae3-2165-4f4e-adfe-9ede0368cb17
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 46b8e127ed67c71a733cf232e92e967a031b4314
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="searchdirectionenum"></a>SearchDirectionEnum
指定的记录中搜索方向[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)。  
  
|常量|“值”|Description|  
|--------------|-----------|-----------------|  
|**adSearchBackward**|-1|搜索向后，在开始处停止**记录集**。 如果未找到匹配项，则记录指针位于[BOF](../../../ado/reference/ado-api/bof-eof-properties-ado.md)。|  
|**adSearchForward**|1|向前搜索，在末尾处停止**记录集**。 如果未找到匹配项，则记录指针位于[EOF](../../../ado/reference/ado-api/bof-eof-properties-ado.md)。|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 等效项  
 Package: **com.ms.wfc.data**  
  
|常量|  
|--------------|  
|AdoEnums.SearchDirection.BACKWARD|  
|AdoEnums.SearchDirection.FORWARD|  
  
## <a name="applies-to"></a>适用范围  
 [Find 方法 (ADO)](../../../ado/reference/ado-api/find-method-ado.md)
