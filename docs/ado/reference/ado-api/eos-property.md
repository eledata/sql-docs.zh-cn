---
title: "EOS 属性 |Microsoft 文档"
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
- EOS
- Stream::EOS
helpviewer_keywords:
- EOS property
ms.assetid: 57e08c5f-f3ed-4ecd-8c66-50b83b1031d1
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: d05f66a056a9436209c7551f348762313b0ba8d2
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="eos-property"></a>EOS 属性
该值指示当前的位置是否在末尾[流](../../../ado/reference/ado-api/stream-object-ado.md)。  
  
## <a name="return-values"></a>返回值  
 返回**布尔**值，该值指示当前的位置是否位于流的末尾。 **EOS**返回**True**如果有更多字节流，则它将返回**False**是否存在以下当前位置的更多字节。  
  
 若要设置的末尾的流位置，使用[SetEOS](../../../ado/reference/ado-api/seteos-method.md)方法。 若要确定当前的位置，请使用[位置](../../../ado/reference/ado-api/position-property-ado.md)属性。  
  
## <a name="applies-to"></a>适用范围  
 [流对象 (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## <a name="see-also"></a>另请参阅  
 [EOS 和 LineSeparator 属性 SkipLine 方法示例 (VB)](../../../ado/reference/ado-api/eos-and-lineseparator-properties-and-skipline-method-example-vb.md)   
 [流对象 (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)
