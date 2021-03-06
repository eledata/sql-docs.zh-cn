---
title: "SkipLine 方法 |Microsoft 文档"
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
- _Stream::raw_SkipLine
- _Stream::SkipLine
helpviewer_keywords:
- Skipline method [ADO]
ms.assetid: 0abc00fe-ee09-4c8e-b1f2-48ee9c5f3329
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2f959ab3e83b91f8c8d8529e44c48a4cbe370882
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="skipline-method"></a>SkipLine 方法
读取文本时，跳过一整行[流](../../../ado/reference/ado-api/stream-object-ado.md)。  
  
## <a name="syntax"></a>语法  
  
```  
  
Stream.SkipLine  
```  
  
## <a name="remarks"></a>注释  
 将跳过所有字符直到并包括下一步的行分隔符。 默认情况下， [LineSeparator](../../../ado/reference/ado-api/lineseparator-property-ado.md)是**adCRLF**。 如果你尝试跳过[EOS](../../../ado/reference/ado-api/eos-property.md)，当前的位置将保持为**EOS**。  
  
 **SkipLine**与文本流中使用方法 ([类型](../../../ado/reference/ado-api/type-property-ado-stream.md)是**adTypeText**)。  
  
## <a name="applies-to"></a>适用范围  
 [流对象 (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
