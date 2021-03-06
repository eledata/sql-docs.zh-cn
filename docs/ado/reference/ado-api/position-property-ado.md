---
title: "定位属性 (ADO) |Microsoft 文档"
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
- _Stream::Position
helpviewer_keywords:
- Position property [ADO]
ms.assetid: daa8319a-49aa-4c1c-9af6-0b01e9ab2f9d
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: c11f5153f63c0fcacd6286b64ee6628c2e0ee439
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="position-property-ado"></a>位置属性 (ADO)
指示当前位置[流](../../../ado/reference/ado-api/stream-object-ado.md)对象。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 设置或返回**长**指定的偏移量中的流的当前位置从一开始的字节数的值。 默认值为 0，它表示流中的第一个字节。  
  
## <a name="remarks"></a>注释  
 可以移动到点结束后的流的当前位置。 如果指定超出流末尾当前位置[大小](../../../ado/reference/ado-api/size-property-ado-stream.md)的**流**对象将会相应地增加。 在这种方式中添加任何新字节将为 null。  
  
> [!NOTE]
>  **位置**始终测量字节。 对于使用多字节字符集的文本流，位置值乘以字符大小来确定字符数。 例如，对于双字节字符集的第一个字符位于位置 0，在位置 2，第三个字符的第二个字符在位置 4，依此类推。  
  
> [!NOTE]
>  负值不能用于更改中的当前位置**流**。 可用于仅正数**位置**。  
  
> [!NOTE]
>  有关只读**流**对象，ADO 将不会返回错误，如果**位置**设置为值大于**大小**的**流**。 这不会更改的大小**流**，或更改**流**以任何方式的内容。 但是，执行此操作应避免使用，因为这会导致无意义**位置**值。  
  
## <a name="applies-to"></a>适用范围  
 [流对象 (ADO)](../../../ado/reference/ado-api/stream-object-ado.md)  
  
## <a name="see-also"></a>另请参阅  
 [Charset 属性 (ADO)](../../../ado/reference/ado-api/charset-property-ado.md)
