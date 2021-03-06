---
title: ParameterDirectionEnum | Microsoft Docs
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
- ParameterDirectionEnum
helpviewer_keywords:
- ParameterDirectionEnum enumeration [ADO]
ms.assetid: c66aa6e6-d4f0-4f0f-9640-e08ae6cfdef3
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 40c8ef97704d48b13eebd7c76aeb6dbe0d709377
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="parameterdirectionenum"></a>ParameterDirectionEnum
指定是否[参数](../../../ado/reference/ado-api/parameter-object.md)表示输入的参数、 输出参数，这两个输入和输出参数或存储过程的返回值。  
  
|常量|“值”|Description|  
|--------------|-----------|-----------------|  
|**adParamInput**|1|默认值。 指示该参数表示输入的参数。|  
|**adParamInputOutput**|3|指示该参数表示一个输入和输出参数。|  
|**adParamOutput**|2|指示该参数表示输出参数。|  
|**adParamReturnValue**|4|指示该参数表示的返回值。|  
|**adParamUnknown**|0|指示参数方向为未知。|  
  
## <a name="adowfc-equivalent"></a>ADO/WFC 等效项  
 Package: **com.ms.wfc.data**  
  
|常量|  
|--------------|  
|AdoEnums.ParameterDirection.INPUT|  
|AdoEnums.ParameterDirection.INPUTOUTPUT|  
|AdoEnums.ParameterDirection.OUTPUT|  
|AdoEnums.ParameterDirection.RETURNVALUE|  
|AdoEnums.ParameterDirection.UNKNOWN|  
  
## <a name="applies-to"></a>适用范围  
  
|||  
|-|-|  
|[CreateParameter 方法 (ADO)](../../../ado/reference/ado-api/createparameter-method-ado.md)|[Direction 属性](../../../ado/reference/ado-api/direction-property.md)|
