---
title: "执行方法 (java.lang.String) (SQLServerStatement) |Microsoft 文档"
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
apiname: SQLServerStatement.execute (java.lang.String)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 64ac78b8-d5b3-4134-9b72-d2b0c52168a2
caps.latest.revision: "8"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 3860a208491aab40235fcc19bbbc8750875d526e
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="execute-method-javalangstring-sqlserverstatement"></a>执行方法 (java.lang.String) (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  运行可返回多个结果的给定的 SQL 语句。  
  
## <a name="syntax"></a>语法  
  
```  
  
public boolean execute(java.lang.String sql)  
```  
  
#### <a name="parameters"></a>Parameters  
 *sql*  
  
 A**字符串**包含 SQL 语句。  
  
## <a name="return-value"></a>返回值  
 **true**如果第一个结果是一个结果集。 否则为 **false**。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.Statement 接口中的 execute 方法指定此 execute 方法。  
  
## <a name="see-also"></a>另请参阅  
 [执行方法 &#40;SQLServerStatement &#41;](../../../connect/jdbc/reference/execute-method-sqlserverstatement.md)   
 [SQLServerStatement 成员](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [SQLServerStatement 类](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
