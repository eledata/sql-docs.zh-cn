---
title: "SQLServerConnection 类 |Microsoft 文档"
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
ms.assetid: 937292a6-1525-423e-a2b2-a18fd34c2893
caps.latest.revision: "17"
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 385bef4155f4b41f181774b1559282c42ac1fbee
ms.sourcegitcommit: 2713f8e7b504101f9298a0706bacd84bf2eaa174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="sqlserverconnection-class"></a>SQLServerConnection 类
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  表示与的 JDBC 连接[!INCLUDE[msCoName](../../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion_md.md)]数据库。  
  
 **包：** com.microsoft.sqlserver.jdbc  
  
 **实现：** [ISQLServerConnection](../../../connect/jdbc/reference/isqlserverconnection-interface.md)，java.io.Serializable  
  
## <a name="syntax"></a>语法  
  
```  
  
public class SQLServerConnection  
```  
  
## <a name="remarks"></a>注释  
 SQLServerConnection 支持 JDBC 连接池，可以是物理的 JDBC 连接或逻辑的 JDBC 连接。 SQLServerConnection 管理事务控制的所有语句，从它，创建的并且它可以参与 XA 分布式事务通过 XAResource 适配器管理。  
  
 SQLServerConnection 管理的已准备的语句句柄的池。 预定义语句仅准备一次，但通常使用不同的语句参数数据值运行多次。 预定义语句还可跨多个关闭的逻辑（入池）连接进行维护。  
  
> [!NOTE]  
>  SQLServerConnection 不是线程安全。 但是，可以在并发线程中同时处理基于单个连接创建的多个语句。  
  
 此类支持到 SQLServerConnection 类、 java.sql.connection 接口和 ISQLServerConnection 接口解包。 有关详细信息，请参阅[包装和接口](../../../connect/jdbc/wrappers-and-interfaces.md)。  
  
## <a name="see-also"></a>另请参阅  
 [SQLServerConnection 成员](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [JDBC 驱动程序 API 参考](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
