---
title: "getTablePrivileges 方法 (SQLServerDatabaseMetaData) |Microsoft 文档"
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
apiname: SQLServerDatabaseMetaData.getTablePrivileges
apilocation: sqljdbc.jar
apitype: Assembly
ms.assetid: 0610d667-a16d-4201-a14b-0a40048911e1
caps.latest.revision: "14"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b0164ce48c06196a71bd9831bb5b66b4a2ad4395
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="gettableprivileges-method-sqlserverdatabasemetadata"></a>getTablePrivileges 方法 (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  检索可用于给定目录、架构或表名称模式的各表的访问权限的说明。  
  
## <a name="syntax"></a>语法  
  
```  
  
public java.sql.ResultSet getTablePrivileges(java.lang.String catalog,  
                                             java.lang.String schema,  
                                             java.lang.String table)  
```  
  
#### <a name="parameters"></a>Parameters  
 *目录*  
  
 A**字符串**，其中包含目录名称。 对此参数提供 Null 值指示无需使用目录名称。  
  
 *架构*  
  
 A**字符串**，其中包含的架构名称模式。 对此参数提供 Null 值指示无需使用架构名称。  
  
 *table*  
  
 A**字符串**，其中包含的表名称模式。  
  
## <a name="return-value"></a>返回值  
 A [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)对象。  
  
## <a name="exceptions"></a>异常  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>注释  
 由 java.sql.DatabaseMetaData 接口中的 getTablePrivileges 方法指定此 getTablePrivileges 方法。  
  
 GetTablePrivileges 方法所返回的结果集将包含以下信息：  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|TABLE_CAT|**字符串**|目录名称。|  
|TABLE_SCHEM|**字符串**|表架构名称。|  
|TABLE_NAME|**字符串**|表名称。|  
|GRANTOR|**字符串**|授予访问权限的对象。|  
|GRANTEE|**字符串**|获得访问权限的对象。|  
|PRIVILEGE|**字符串**|授予的访问权限的类型。|  
|IS_GRANTABLE|**字符串**|指示是否允许被授权者向其他用户授予权限。|  
  
> [!NOTE]  
>  有关 getTablePrivileges 方法返回的数据的详细信息，请参阅"sp_table_privileges (TRANSACT-SQL)"中[!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]联机丛书。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用 getTablePrivileges 方法返回的 Person.Contact 表中的访问权限[!INCLUDE[ssSampleDBnormal](../../../includes/sssampledbnormal_md.md)]示例数据库。  
  
```  
public static void executeGetTablePrivileges(Connection con) {  
   try {  
      DatabaseMetaData dbmd = con.getMetaData();  
      ResultSet rs = dbmd.getTablePrivileges("AdventureWorks", "Person", "Contact");  
      ResultSetMetaData rsmd = rs.getMetaData();  
  
      // Display the result set data.  
      int cols = rsmd.getColumnCount();  
      while(rs.next()) {  
         for (int i = 1; i <= cols; i++) {  
            System.out.println(rs.getString(i));  
         }  
      }  
      rs.close();  
   }   
  
   catch (Exception e) {  
      e.printStackTrace();  
   }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerDatabaseMetaData 方法](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [SQLServerDatabaseMetaData 成员](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [SQLServerDatabaseMetaData 类](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
