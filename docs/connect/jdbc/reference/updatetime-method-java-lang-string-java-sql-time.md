---
title: "updateTime 方法 （java.lang.String，java.sql.Time） |Microsoft 文档"
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
apiname: SQLServerResultSet.updateTime (java.lang.String, java.sql.Time)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: fbbcef68-b903-4cfd-911c-a7e239d17c74
caps.latest.revision: "20"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 16b2ae835e289e826e20f5ecdf5613611ec23d58
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="updatetime-method-javalangstring-javasqltime"></a>updateTime 方法 (java.lang.String, java.sql.Time)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  根据给定的列名称使用时间值更新指定的列。  
  
## <a name="syntax"></a>语法  
  
```  
  
public void updateTime(java.lang.String columnName,  
                       java.sql.Time x)  
```  
  
#### <a name="parameters"></a>Parameters  
 *columnName*  
  
 A**字符串**包含列名称。  
  
 *x*  
  
 时间值。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.ResultSet 接口中的 updateTime 方法指定此 updateTime 方法。  
  
## <a name="see-also"></a>另请参阅  
 [updateTime 方法 &#40;SQLServerResultSet &#41;](../../../connect/jdbc/reference/updatetime-method-sqlserverresultset.md)   
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
