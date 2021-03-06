---
title: "连接和检索数据 |Microsoft 文档"
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
ms.assetid: ce43cc20-46a3-42ff-a3fb-75ad1ed10e08
caps.latest.revision: "11"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 856e4ea4fe28bf8884ea498a747d0bb4e9753699
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="connecting-and-retrieving-data"></a>连接和检索数据
[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

  当你正在使用[!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)]，有两种主要方法建立的连接[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]数据库。 在连接 URL 设置连接属性，然后调用的驱动程序管理器类以返回 getConnection 方法之一是[SQLServerConnection](../../connect/jdbc/reference/sqlserverconnection-class.md)对象。  
  
> [!NOTE]  
>  JDBC 驱动程序支持的连接属性的列表，请参阅[设置连接属性](../../connect/jdbc/setting-the-connection-properties.md)。  
  
 第二种方法涉及使用 setter 方法的设置连接属性[SQLServerDataSource](../../connect/jdbc/reference/sqlserverdatasource-class.md)类，并调用[getConnection](../../connect/jdbc/reference/getconnection-method-sqlserverdatasource.md)方法以返回 SQLServerConnection对象。  
  
 本部分中的主题介绍你可以连接到的不同方式[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]数据库，并且它们还演示了不同的技术来检索数据。  
  
## <a name="in-this-section"></a>本节内容  
  
|主题|Description|  
|-----------|-----------------|  
|[连接 URL 示例](../../connect/jdbc/connection-url-sample.md)|介绍如何使用连接 URL 以连接到[!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]，然后使用 SQL 语句检索数据。|  
|[数据源示例](../../connect/jdbc/data-source-sample.md)|说明如何先使用数据源来连接 SQL Server，然后再使用存储过程来检索数据。|  
  
## <a name="see-also"></a>另请参阅  
 [示例 JDBC 驱动程序应用程序](../../connect/jdbc/sample-jdbc-driver-applications.md)  
  
  
