---
title: FrameWindowVisible | Microsoft Docs
ms.custom: 
ms.date: 03/17/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9091d714-98bc-43ec-b8d1-9c892cb57f19
caps.latest.revision: 6
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: f09e83d79a913bb56042a5a48b832a940e0f9ea9
ms.contentlocale: zh-cn
ms.lasthandoff: 06/22/2017

---
# <a name="sqltoolsvsnativehelpers---framewindowvisible"></a>SqlToolsVSNativeHelpers - FrameWindowVisible
  指定特定窗口框架是否可见的属性。 帮助器方法是从托管代码使用的。  
  
## <a name="syntax"></a>语法  
  
```  
  
BOOL WINAPI IsFrameWindowVisible(IVsWindowFrame* frame)  
{  
    if (NULL == frame)  
    {  
        return FALSE;  
    }  
  
    return S_OK == frame->IsVisible();  
}  
```  
  
#### <a name="parameters"></a>Parameters  
 *frame*  
  
 指向 Visual Studio WindowFrame 的 IVsWindowFrame* 指针。  
  
## <a name="property-valuereturn-value"></a>属性值/返回值  
 一个布尔值，该值指定由 *frame* 指定的窗口框架是否可见。  
  
## <a name="see-also"></a>另请参阅  
 [SqlToolsVSNativeHelpers](../relational-databases/sqltoolsvsnativehelpers.md)  
  
  