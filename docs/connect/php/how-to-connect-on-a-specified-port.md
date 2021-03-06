---
title: 如何： 在指定端口上连接 |Microsoft 文档
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: ''
ms.component: php
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connecting to the server, specifying a port
ms.assetid: 65a154d1-375c-439b-a653-7815c9d70ff3
caps.latest.revision: ''
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 0b3c8f76026c7065cf6d790b323f559e1b101126
ms.sourcegitcommit: 2e130e9f3ce8a7ffe373d7fba8b09e937c216386
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-connect-on-a-specified-port"></a>如何：在指定端口上连接
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

本主题介绍如何使用 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]在指定端口上连接到 SQL Server。  
  
### <a name="to-connect-on-a-specified-port"></a>在指定端口上连接  
  
1.  对服务器配置为接受连接的端口进行验证。 有关配置服务器以接受指定端口上的连接的信息，请参阅[如何： 配置服务器以侦听特定 TCP 端口 （SQL Server 配置管理器）](../../database-engine/configure-windows/configure-a-server-to-listen-on-a-specific-tcp-port.md)。  
  
2.  添加到所需的端口*$serverName*参数[sqlsrv_connect](../../connect/php/sqlsrv-connect.md)函数。 用逗号分隔服务器名称和端口。 例如，以下代码行使用 SQLSRV 驱动程序来演示如何在端口 1521 上连接到名为 *myServer* 的服务器：  
  
    ```  
    $serverName = "myServer, 1521";  
    sqlsrv_connect( $serverName );  
    ```  
  
    下面的代码行使用 PDO_SQLSRV 驱动程序来演示如何连接到一个名为服务器*myServer*在端口 1521年上：  
  
    ```  
    $serverName = "(local), 1521";  
    $database = "AdventureWorks";  
    $conn = new PDO( "sqlsrv:server=$serverName;Database=$database", "", "");  
    ```  
  
## <a name="see-also"></a>另请参阅  
[连接到服务器](../../connect/php/connecting-to-the-server.md)

[For PHP for SQL Server 编程 Microsoft 驱动程序的指南](../../connect/php/programming-guide-for-php-sql-driver.md)

[开始使用 Microsoft Drivers for PHP for SQL Server](../../connect/php/getting-started-with-the-php-sql-driver.md)

[SQLSRV 驱动程序 API 参考](../../connect/php/sqlsrv-driver-api-reference.md)

[PDO_SQLSRV 驱动程序参考](../../connect/php/pdo-sqlsrv-driver-reference.md)  
  
