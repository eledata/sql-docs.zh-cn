---
title: 使用目录函数 |Microsoft 文档
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: ''
ms.component: native-client|ODBC
ms.reviewer: ''
ms.suite: sql
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
caps.latest.revision: 36
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: ff184bbcfc3e638bf15badc98a060e88cac3e0d1
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="using-catalog-functions"></a>使用目录函数
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  所有数据库都具有一个包含该数据中存储的数据的结构。 此结构的定义以及权限等其他信息存储在目录（作为一组系统表实现）中，也称为数据字典。  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序可让应用程序确定通过对 ODBC 目录函数的调用的数据库结构。 目录函数返回结果集中的信息，这些函数是使用目录存储过程实现的，用于查询该目录中的系统表。 例如，应用程序可以请求包含系统上所有表的相关信息的结果集或包含特定表中的所有列的相关信息的结果集。 标准 ODBC 目录函数用于获取连接应用程序的 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 中的目录信息。  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 支持通过一个查询访问多个异类 OLE DB 数据源的数据的分布式查询。 访问远程 OLE DB 数据源的一种方法是将数据源定义为链接服务器。 这可以通过使用[sp_addlinkedserver](../../../relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql.md)。 定义链接服务器后，使用由四个部分组成的名称可以在 Transact-SQL 语句中引用该服务器上的对象：  
  
 *linked_server_name.catalog.schema.object_name*.  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序支持两个有助于获取链接服务器的目录信息的特定于驱动程序的函数：  
  
-   **SQLLinkedServers**  
  
     返回定义到本地服务器的链接服务器列表。  
  
-   **SQLLinkedCatalogs**  
  
     返回链接服务器包含的目录的列表。  
  
 你具有链接的服务器名称和目录的名称后, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序支持使用的两部分名称从目录获取信息*linked_server_name***。***目录*为*CatalogName*上以下 ODBC 目录函数：  
  
-   **SQLColumnPrivileges**  
  
-   **SQLColumns**  
  
-   **SQLPrimaryKeys**  
  
-   **SQLStatistics**  
  
-   **SQLTablePrivileges**  
  
-   **SQLTables**  
  
 两个部分构成*linked_server_name***。***目录*也支持*FKCatalogName*和*PKCatalogName*上[SQLForeignKeys](../../../relational-databases/native-client-odbc-api/sqlforeignkeys.md)。  
  
 使用 SQLLinkedServers 和 SQLLinkedCatalogs 需要以下文件：  
  
-   sqlncli.h  
  
     包括用于链接服务器目录函数的函数原型和常量定义。 必须在 ODBC 应用程序中包括 sqlncli.h，并且在编译应用程序时必须将其放在 include 路径中。  
  
-   sqlncli11.lib  
  
     必须放在链接器的库路径中，并将其指定为要链接的文件。 sqlncli11.lib 随 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序一起分发。  
  
-   sqlncli11.dll  
  
     在执行时必须存在。 sqlncli11.dll 随 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序一起分发。  
  
## <a name="see-also"></a>另请参阅  
 [SQL Server Native Client &#40;ODBC&#41;](../../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)   
 [SQLColumnPrivileges](../../../relational-databases/native-client-odbc-api/sqlcolumnprivileges.md)   
 [SQLColumns](../../../relational-databases/native-client-odbc-api/sqlcolumns.md)   
 [SQLPrimaryKeys](../../../relational-databases/native-client-odbc-api/sqlprimarykeys.md)   
 [SQLTablePrivileges](../../../relational-databases/native-client-odbc-api/sqltableprivileges.md)   
 [SQLTables](../../../relational-databases/native-client-odbc-api/sqltables.md)   
 [SQLStatistics](../../../relational-databases/native-client-odbc-api/sqlstatistics.md)  
  
  
