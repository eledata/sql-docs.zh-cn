---
title: "章属性 (ADO) |Microsoft 文档"
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
- ADORecordsetConstruction::Chapter
- ADORecordsetConstruction::put_Chapter
- ADORecordsetConstruction::get_Chapter
helpviewer_keywords:
- Chapter property [ADO]
ms.assetid: 8aa90cb0-f588-4141-9dc9-3b22918394ee
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 938eeef6f18e154c4b9c17792f00254934d7cc4b
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="chapter-property-ado"></a>章属性 (ADO)
获取或设置 OLE DB**章**对象从/上[ADORecordsetConstruction 接口](../../../ado/reference/ado-api/adorecordsetconstruction-interface.md)对象。 当你使用**put_Chapter**设置**章**对象，行的子集转换为 ADO[记录集对象](../../../ado/reference/ado-api/recordset-object-ado.md)对象。 这将设置读 /**行集**对象。 此属性是可读写的。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT get_Chapter([out, retval] long* plChapter);  
HRESULT put_Chapter([in] long lChapter);  
```  
  
## <a name="parameters"></a>Parameters  
 *plChapter*  
 指向某章节的句柄的指针。  
  
 *LChapter*  
 子集的句柄。  
  
## <a name="return-values"></a>返回值  
 此属性方法返回的标准的 HRESULT 值，包括，则为 S_OK 和 E_FAIL。  
  
## <a name="applies-to"></a>适用范围  
 [ADORecordsetConstruction 接口](../../../ado/reference/ado-api/adorecordsetconstruction-interface.md)
