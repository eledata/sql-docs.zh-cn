---
title: "HelpContext、 HelpFile 属性 |Microsoft 文档"
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
- Error::GetHelpContext
- Error::GetHelpFile
- Error::get_HelpFile
- Error::get_HelpContext
- Error::HelpContext
- Error::HelpFile
helpviewer_keywords:
- HelpContext property [ADO]
- HelpFile property [ADO]
ms.assetid: 2b9ef441-993c-44d4-8f87-fac0979dac1d
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 1d93d8f16d828892e8e5c11ca1036f7dc83b75fb
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="helpcontext-helpfile-properties"></a>HelpContext，HelpFile 属性
指示的帮助文件和相关联的主题[错误](../../../ado/reference/ado-api/error-object.md)对象。  
  
## <a name="return-values"></a>返回值  
  
-   **帮助上下文 Id**形式返回的上下文 ID，**长**值，帮助文件中的主题。  
  
-   **HelpFile**返回**字符串**计算结果为的帮助文件的完全解析路径的值。  
  
## <a name="remarks"></a>注释  
 如果在中指定的帮助文件**HelpFile**属性， **HelpContext**属性用于自动显示其所标识的帮助主题。 如果不没有可用的任何相关的帮助主题**HelpContext**属性将返回零和**HelpFile**属性返回一个零长度字符串 ("")。  
  
## <a name="applies-to"></a>适用范围  
 [错误对象](../../../ado/reference/ado-api/error-object.md)  
  
## <a name="see-also"></a>另请参阅  
 [描述、 HelpContext、 HelpFile、 NativeError、 数量、 源和 SQLState 属性示例 (VB)](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vb.md)   
 [描述、 HelpContext、 HelpFile、 NativeError、 数量、 源和 SQLState 属性示例 （VC + +）](../../../ado/reference/ado-api/description-helpcontext-helpfile-nativeerror-number-source-example-vc.md)   
 [Description 属性](../../../ado/reference/ado-api/description-property.md)   
 [Number 属性 (ADO)](../../../ado/reference/ado-api/number-property-ado.md)   
 [Source 属性（ADO 错误）](../../../ado/reference/ado-api/source-property-ado-error.md)
