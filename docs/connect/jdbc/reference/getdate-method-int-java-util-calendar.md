---
title: "getDate 方法 （int、 java.util.Calendar） |Microsoft 文档"
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
apiname: SQLServerCallableStatement.getDate (int, java.util.Calendar)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 38ce7b75-2623-4eff-bc18-8cf7193adec8
caps.latest.revision: "10"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 4aeaade0f605e2450ed689af5bae41e1ef4b1315
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="getdate-method-int-javautilcalendar"></a>getDate 方法 (int, java.util.Calendar)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  与给定的参数索引和日历对象的 Java 编程语言中某个 java.sql.Date 对象中检索指定参数的值。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.sql.Date getDate(int index,  
                             java.util.Calendar cal)  
```  
  
#### <a name="parameters"></a>Parameters  
 *索引*  
  
 **Int** ，该值指示参数索引。  
  
 *cal*  
  
 日历对象中。  
  
## <a name="return-value"></a>返回值  
 Date 对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 GetDate 方法 java.sql.CallableStatement 界面中指定此 getDate 方法。  
  
 此方法返回的有效日期部分的[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)] **datetime**或**smalldatetime**数据类型，其设置为 00:00 （午夜） 的 Java 时间基线的时间部分。  
  
## <a name="see-also"></a>另请参阅  
 [getDate 方法 &#40;SQLServerCallableStatement &#41;](../../../connect/jdbc/reference/getdate-method-sqlservercallablestatement.md)   
 [SQLServerCallableStatement 成员](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [SQLServerCallableStatement 类](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
