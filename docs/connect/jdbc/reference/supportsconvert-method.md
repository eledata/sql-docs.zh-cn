---
title: "supportsConvert 方法 （) |Microsoft 文档"
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
apiname: SQLServerDatabaseMetaData.supportsConvert ()
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 45c83c4f-649a-4cd6-9d44-d38524758bb8
caps.latest.revision: "6"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: bbc9946f63a3c0c794e8d31210bb64cad689668a
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="supportsconvert-method-"></a>supportsConvert 方法 ()
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索此数据库是否支持在 SQL 类型之间使用 CONVERT 函数。  
  
## <a name="syntax"></a>语法  
  
```  
  
public boolean supportsConvert()  
```  
  
## <a name="return-value"></a>返回值  
 **true**如果支持。 否则为 **false**。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.DatabaseMetaData 接口中的 supportsConvert 方法指定此 supportsConvert 方法。  
  
## <a name="see-also"></a>另请参阅  
 [supportsConvert 方法 &#40;SQLServerDatabaseMetaData &#41;](../../../connect/jdbc/reference/supportsconvert-method-sqlserverdatabasemetadata.md)   
 [SQLServerDatabaseMetaData 方法](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData 成员](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData 类](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
