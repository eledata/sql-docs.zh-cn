---
title: "getQueryTimeout 方法 (SQLServerStatement) |Microsoft 文档"
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
apiname: SQLServerStatement.getQueryTimeout
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 8dff954f-b458-4fa6-abe6-be62ff75e2b9
caps.latest.revision: "11"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: e186dba1f77d8b3c8062b91e33b80917a3e5c6af
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="getquerytimeout-method-sqlserverstatement"></a>getQueryTimeout 方法 (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索的秒数[!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)]将等待对此[SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)对象能够运行。  
  
## <a name="syntax"></a>语法  
  
```  
  
public final int getQueryTimeout()  
```  
  
## <a name="return-value"></a>返回值  
 **Int** ，该值指示 JDBC 驱动程序将等待的秒或 0 的数，如果没有任何限制。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.Statement 接口中的 getQueryTimeout 方法指定此 getQueryTimeout 方法。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerStatement 成员](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 类](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
