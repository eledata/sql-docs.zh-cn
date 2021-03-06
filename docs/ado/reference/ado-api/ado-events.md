---
title: "ADO 事件 |Microsoft 文档"
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
helpviewer_keywords:
- events [ADO]
- ADO, events
ms.assetid: 0ded5ad9-8f83-4224-95af-38512783b972
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4315048296c450e1365874e021725c8160612313
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="ado-events"></a>ADO 事件
|||  
|-|-|  
|[BeginTransComplete](../../../ado/reference/ado-api/begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md)|之后调用**BeginTrans**操作。|  
|[CommitTransComplete](../../../ado/reference/ado-api/begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md)|之后调用**CommitTrans**操作。|  
|[ConnectComplete](../../../ado/reference/ado-api/connectcomplete-and-disconnect-events-ado.md)|连接开始后调用。|  
|[断开连接](../../../ado/reference/ado-api/connectcomplete-and-disconnect-events-ado.md)|连接结束后调用。|  
|[EndOfRecordset](../../../ado/reference/ado-api/endofrecordset-event-ado.md)|尝试移动到末尾的某一行时调用**记录集**。|  
|[ExecuteComplete](../../../ado/reference/ado-api/executecomplete-event-ado.md)|命令已完成执行后调用。|  
|[FetchComplete](../../../ado/reference/ado-api/fetchcomplete-event-ado.md)|调用较长的异步操作中的所有记录已经都检索到后**记录集**。|  
|[FetchProgress](../../../ado/reference/ado-api/fetchprogress-event-ado.md)|定期在较长的异步操作以报告多少行当前已经检索到过程中调用**记录集**。|  
|[FieldChangeComplete](../../../ado/reference/ado-api/willchangefield-and-fieldchangecomplete-events-ado.md)|在一个或多个值之后调用**字段**对象已更改。|  
|[InfoMessage](../../../ado/reference/ado-api/infomessage-event-ado.md)|每当期间出现警告时调用**ConnectionEvent**操作。|  
|[MoveComplete](../../../ado/reference/ado-api/willmove-and-movecomplete-events-ado.md)|在中的当前位置之后调用**记录集**更改。|  
|[RecordChangeComplete](../../../ado/reference/ado-api/willchangerecord-and-recordchangecomplete-events-ado.md)|一个或多个记录更改后调用。|  
|[RecordsetChangeComplete](../../../ado/reference/ado-api/willchangerecordset-and-recordsetchangecomplete-events-ado.md)|之后调用**记录集**已更改。|  
|[RollbackTransComplete](../../../ado/reference/ado-api/begintranscomplete-committranscomplete-and-rollbacktranscomplete-events-ado.md)|之后调用**不**操作。|  
|[WillChangeField](../../../ado/reference/ado-api/willchangefield-and-fieldchangecomplete-events-ado.md)|一个或多个值更改为挂起的操作之前调用**字段**中的对象**记录集**。|  
|[WillChangeRecord](../../../ado/reference/ado-api/willchangerecord-and-recordchangecomplete-events-ado.md)|在中调用一个或多个记录 （行） 之前**记录集**更改。|  
|[WillChangeRecordset](../../../ado/reference/ado-api/willchangerecordset-and-recordsetchangecomplete-events-ado.md)|在挂起的操作将更改之前调用**记录集**。|  
|[WillConnect](../../../ado/reference/ado-api/willconnect-event-ado.md)|在连接启动之前调用。|  
|[WillExecute](../../../ado/reference/ado-api/willexecute-event-ado.md)|挂起命令在此连接上执行，并为用户提供了机会来检查和修改挂起的执行参数前立即调用。|  
|[WillMove](../../../ado/reference/ado-api/willmove-and-movecomplete-events-ado.md)|**WillMove**事件时调用*之前*挂起的操作将更改中的当前位置**记录集**。|  
  
## <a name="see-also"></a>另请参阅  
 [ADO API 参考](../../../ado/reference/ado-api/ado-api-reference.md)   
 [ADO 集合](../../../ado/reference/ado-api/ado-collections.md)   
 [ADO 动态属性](../../../ado/reference/ado-api/ado-dynamic-properties.md)   
 [ADO 枚举常量](../../../ado/reference/ado-api/ado-enumerated-constants.md)   
 [附录 b: ADO 错误](../../../ado/guide/appendixes/appendix-b-ado-errors.md)   
 [处理 ADO 事件](../../../ado/guide/data/handling-ado-events.md)   
 [ADO 方法](../../../ado/reference/ado-api/ado-methods.md)   
 [ADO 对象模型](../../../ado/reference/ado-api/ado-object-model.md)   
 [ADO 对象和接口](../../../ado/reference/ado-api/ado-objects-and-interfaces.md)   
 [ADO 属性](../../../ado/reference/ado-api/ado-properties.md)
