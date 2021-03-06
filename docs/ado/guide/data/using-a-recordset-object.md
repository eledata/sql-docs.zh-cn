---
title: "使用记录集对象 |Microsoft 文档"
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
- connections [ADO]
ms.assetid: 01c630d8-eb35-4bd0-a99f-7c0f85316cc1
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 737b0b01da5f339c1fbda1cf234301dfafad4d19
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="using-a-recordset-object"></a>使用记录集对象
或者，可以使用**Recordset.Open**隐式建立连接，通过该连接在单个操作中发出命令。 例如，在 Visual Basic:  
  
```  
Dim oRs As ADODB.Recordset  
Dim sConn As String  
Dim sSQL as String  
  
sConn = "Provider='SQLOLEDB';Data Source='MySqlServer';" & _             "Initial Catalog='Northwind';Integrated Security='SSPI';"  
  
sSQL = "SELECT ProductID, ProductName, CategoryID, UnitPrice " & _  
             "FROM Products"  
  
' Create and Open the Recordset object.  
Set oRs = New ADODB.Recordset  
oRs.CursorLocation = adUseClient  
oRs.Open sSQL, sConn, adOpenStatic, _  
               adLockBatchOptimistic, adCmdText  
  
MsgBox oRs.RecordCount  
  
oRs.MarshalOptions = adMarshalModifiedOnly  
' Disconnect the Recordset.  
Set oRs.ActiveConnection = Nothing  
oRs.Close          
Set oRs = Nothing  
```  
  
 请注意， **oRs.Open**采用连接字符串 (*sConn*)，代替了**连接**对象 (*oConn*)，作为其的值**ActiveConnection**参数。 也通过设置强制客户端游标类型**CursorLocation**属性**记录集**对象。 同样，相比之下与**HelloData**示例。
