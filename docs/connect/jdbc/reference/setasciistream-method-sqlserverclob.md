---
title: "setAsciiStream 方法 (SQLServerClob) |Microsoft 文档"
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
apiname: SQLServerClob.setAsciiStream
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 6e1779df-3b2a-41d1-8dca-99692cc9da14
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: f501c9c610319e0cad34dfabfe70dbf3f6cfffe2
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="setasciistream-method-sqlserverclob"></a>setAsciiStream 方法 (SQLServerClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  返回用来将 ASCII 字符写入 CLOB 的流（从指定位置开始写入）。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.io.OutputStream setAsciiStream(long pos)  
```  
  
#### <a name="parameters"></a>Parameters  
 *pos*  
  
 开始写入 CLOB 对象的位置。  
  
## <a name="return-value"></a>返回值  
 可向其中写入 ASCII 编码字符的流。  
  
## <a name="exceptions"></a>异常  
 java.sql.SQLException  
  
## <a name="remarks"></a>注释  
 由 java.sql.Clob 接口中的 setAsciiStream 方法指定此 setAsciiStream 方法。  
  
 输出流从指定位置开始覆盖 CLOB 中的字符数据，并可以超过 CLOB 的初始长度。 指定“位置+1”值将追加 ASCII 字符。 指定“位置+2”或更大值（或零或更小值）会引发位置错误。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerClob 方法](../../../connect/jdbc/reference/sqlserverclob-methods.md)   
 [SQLServerClob 成员](../../../connect/jdbc/reference/sqlserverclob-members.md)   
 [SQLServerClob 类](../../../connect/jdbc/reference/sqlserverclob-class.md)  
  
  
