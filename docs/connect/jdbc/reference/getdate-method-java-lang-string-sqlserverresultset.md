---
title: "getDate 方法 (java.lang.String) 列 |Microsoft 文档"
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
apiname: SQLServerResultSet.getDate (java.lang.String)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 821058ae-cbe3-4a14-aa02-d55e45491437
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 2b20e134b918592f563d1e0630e25454635c46ac
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="getdate-method-javalangstring-sqlserverresultset"></a>getDate 方法 (java.lang.String) (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索此当前行中的指定的列名称的值[SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)作为 Java 编程语言中的 java.sql.Date 对象的对象。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.sql.Date getDate(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>Parameters  
 *columnName*  
  
 A**字符串**包含列名称。  
  
## <a name="return-value"></a>返回值  
 Date 对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 GetDate 方法 java.sql.ResultSet 界面中指定此 getDate 方法。  
  
 此方法返回的有效日期部分的[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]datetime 或 smalldatetime 数据类型，其设置为 00:00 （午夜） 的 Java 时间基线的时间部分。  
  
## <a name="see-also"></a>另请参阅  
 [getDate 方法 &#40;SQLServerResultSet &#41;](../../../connect/jdbc/reference/getdate-method-sqlserverresultset.md)   
 [SQLServerResultSet 成员](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [SQLServerResultSet 类](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
