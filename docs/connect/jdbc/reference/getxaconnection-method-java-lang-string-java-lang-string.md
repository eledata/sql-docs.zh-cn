---
title: "getXAConnection 方法 （java.lang.String，java.lang.String） |Microsoft 文档"
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
apiname: SQLServerXADataSource.getXAConnection (java.lang.String, java.lang.String)
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 276e0093-3d42-4f73-acc4-2b5b98245b40
caps.latest.revision: "9"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 7b9cb48cab11159a3494f785921368010144bbe8
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="getxaconnection-method-javalangstring-javalangstring"></a>getXAConnection 方法 (java.lang.String, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  使用给定的用户名和密码尝试建立物理数据库连接。  
  
## <a name="syntax"></a>语法  
  
```  
  
public javax.sql.XAConnection getXAConnection(java.lang.String user,  
                                              java.lang.String password)  
```  
  
#### <a name="parameters"></a>Parameters  
 *用户*  
  
 A**字符串**包含的用户名称。  
  
 *密码*  
  
 A**字符串**包含的密码。  
  
## <a name="return-value"></a>返回值  
 XAConnection 对象。  
  
## <a name="exceptions"></a>异常  
 java.sql.SQLException  
  
## <a name="remarks"></a>注释  
 由 javax.sql.XADataSource 接口中的 getXAConnection 方法指定此 getXAConnection 方法。  
  
> [!NOTE]  
>  此方法一般由 XA 连接池实现调用，而不由常规的 JDBC 应用程序代码调用。  
  
## <a name="see-also"></a>另请参阅  
 [getXAConnection 方法 &#40;SQLServerXADataSource &#41;](../../../connect/jdbc/reference/getxaconnection-method-sqlserverxadatasource.md)   
 [SQLServerXADataSource 方法](../../../connect/jdbc/reference/sqlserverxadatasource-methods.md)   
 [SQLServerXADataSource 成员](../../../connect/jdbc/reference/sqlserverxadatasource-members.md)   
 [SQLServerXADataSource 类](../../../connect/jdbc/reference/sqlserverxadatasource-class.md)  
  
  
