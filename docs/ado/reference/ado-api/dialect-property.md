---
title: "方言属性 |Microsoft 文档"
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
- _Command::Dialect
helpviewer_keywords:
- Dialect property
ms.assetid: 329c3a71-ba88-4009-b04f-2f52195a5957
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a0dbf91200e241596217566d8859626f69dcbe1f
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="dialect-property"></a>方言属性
指示的方言[CommandText](../../../ado/reference/ado-api/commandtext-property-ado.md)或[CommandStream](../../../ado/reference/ado-api/commandstream-property-ado.md)属性。 方言定义的语法和提供程序使用来分析字符串或流的一般规则。  
  
## <a name="settings-and-return-values"></a>设置和返回值  
 **方言**属性包含一个有效的 GUID，它表示的命令文本或流的方言。 此属性的默认值是 {C8B521FB-5CF3-11CE-ADE5-00AA0044773D} 表示提供程序，应选择如何解释命令文本或流。  
  
## <a name="remarks"></a>注释  
 当用户读取此属性; 的值时，ADO 不查询提供程序它将返回的字符串表示形式中当前存储的值[命令](../../../ado/reference/ado-api/command-object-ado.md)对象。  
  
 当用户设置**方言**属性，ADO 验证 GUID，并引发错误，如果提供的值不是有效的 GUID。 请参阅你的提供商，以确定支持的 GUID 值的文档**方言**属性。  
  
## <a name="applies-to"></a>适用范围  
 [命令对象 (ADO)](../../../ado/reference/ado-api/command-object-ado.md)  
  
## <a name="see-also"></a>另请参阅  
 [Execute 方法（ADO 命令）](../../../ado/reference/ado-api/execute-method-ado-command.md)
