---
title: "setClob 方法 （int、 java.io.Reader，长） |Microsoft 文档"
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: jdbc
ms.reviewer: 
ms.suite: sql
ms.technology: drivers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 157882dd-1a96-4501-a895-46e88a49266e
caps.latest.revision: "26"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7ed6649bc445fb01f4eb68d5d3bc5afbc261778c
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="setclob-method-int-javaioreader-long"></a>setClob 方法 (int, java.io.Reader, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  将指定的参数设置为指定的读取器对象，它是给定的字符数。  
  
## <a name="syntax"></a>语法  
  
```  
  
public final void setClob(int parameterIndex,  
                          java.io.Reader reader,  
                          long length)  
```  
  
#### <a name="parameters"></a>Parameters  
 *parameterIndex*  
  
 **Int** ，该值指示参数索引。  
  
 *读取器*  
  
 一个读取器对象。  
  
 *length*  
  
 A**长**，该值指示参数值中的字符数。  
  
## <a name="remarks"></a>注释  
 由 java.sql.PreparedStatement 接口中的 setClob 方法指定此 setClob 方法。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="see-also"></a>另请参阅  
 [setClob 方法 &#40;SQLServerPreparedStatement &#41;](../../../connect/jdbc/reference/setclob-method-sqlserverpreparedstatement.md)   
 [SQLServerPreparedStatement 成员](../../../connect/jdbc/reference/sqlserverpreparedstatement-members.md)  
  
  
