---
title: "FetchComplete 事件 (ADO) |Microsoft 文档"
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
- Recordset::ExecuteComplete
- ExecuteComplete
helpviewer_keywords:
- FetchComplete event [ADO]
ms.assetid: a28d3858-566c-468d-b070-d1de4339fbea
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a8332a6332f27a8e2022975a80814be9c28cf4da
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="fetchcomplete-event-ado"></a>FetchComplete 事件 (ADO)
**FetchComplete**较长的异步操作中的所有记录已经都检索到后，将调用事件[记录集](../../../ado/reference/ado-api/recordset-object-ado.md)。  
  
## <a name="syntax"></a>语法  
  
```  
  
FetchComplete pError, adStatus, pRecordset  
```  
  
#### <a name="parameters"></a>Parameters  
 *pError*  
 [错误](../../../ado/reference/ado-api/error-object.md)对象。 它描述发生错误的值**adStatus**是**adStatusErrorsOccurred**; 不会设置。  
  
 *adStatus*  
 [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md)状态值。 当调用此事件时，此参数设置为**adStatusOK**引起该事件的操作是否成功，或到**adStatusErrorsOccurred**如果操作失败。  
  
 此事件返回之前，将此参数设置为**adStatusUnwantedEvent**以防止后续的通知。  
  
 *pRecordset*  
 A**记录集**对象。 记录已为其检索到的对象。  
  
## <a name="remarks"></a>注释  
 若要使用**FetchComplete**与 Microsoft Visual Basic 中，Visual Basic 6.0 或更高版本是所需。  
  
## <a name="see-also"></a>另请参阅  
 [ADO 事件模型示例 （VC + +）](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [ADO 事件处理程序摘要](../../../ado/guide/data/ado-event-handler-summary.md)
