---
title: "getConcurrency 方法 (SQLServerResultSet) |Microsoft 文档"
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
apiname: SQLServerResultSet.getConcurrency
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 207e25f4-769c-4ff3-913c-3517b06208e4
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: ec5975c62b4c6161a44ef171c1406ac09df3a439
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="getconcurrency-method-sqlserverresultset"></a>getConcurrency 方法 (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索此并发模式[SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public int getConcurrency()  
```  
  
## <a name="return-value"></a>返回值  
 **Int** ，该值指示并发类型，可为下列值之一：  
  
 ResultSet.CONCUR_READ_ONLY  
  
 ResultSet.CONCUR_UPDATABLE  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSet 接口中的 getConcurrency 方法指定此 getConcurrency 方法。  
  
 使用的并发性由[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)创建结果集的对象。  
  
 此方法可以用于确定实际并发类型。 如果应用程序选择了 CONCUR_READ_ONLY 或 CONCUR_UPDATABLE，将返回这些并发类型。 如果应用程序使用了默认并发类型，将返回 CONCUR_READ_ONLY。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
