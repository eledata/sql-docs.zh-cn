---
title: "Children 属性 (ADO MD) |Microsoft 文档"
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
- Member::Children
- Children
helpviewer_keywords:
- Children property [ADO MD]
ms.assetid: 61d36468-1ccd-467a-9cb5-17d0bfacc766
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 39c1ba30aab6f6a972241c0e564a7a0680165828
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="children-property-ado-md"></a>Children 属性 (ADO MD)
返回[成员](../../../ado/reference/ado-md-api/members-collection-ado-md.md)为其集合当前[成员](../../../ado/reference/ado-md-api/member-object-ado-md.md)是层次结构中的父级。  
  
## <a name="return-values"></a>返回值  
 返回**成员**集合是只读的和。  
  
## <a name="remarks"></a>注释  
 **子级**属性包含**成员**为其集合当前**成员**是分层的父级。 叶级别**成员**对象在中有任何子成员**成员**集合。 在上才支持此属性**成员**属于对象[级别](../../../ado/reference/ado-md-api/level-object-ado-md.md)对象。 从引用此属性时出现错误**成员**属于对象[位置](../../../ado/reference/ado-md-api/position-object-ado-md.md)对象。  
  
## <a name="applies-to"></a>适用范围  
 [成员对象 (ADO MD)](../../../ado/reference/ado-md-api/member-object-ado-md.md)  
  
## <a name="see-also"></a>另请参阅  
 [ChildCount 属性 (ADO MD)](../../../ado/reference/ado-md-api/childcount-property-ado-md.md)
