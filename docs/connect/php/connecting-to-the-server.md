---
title: 连接到服务器 |Microsoft 文档
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
ms.assetid: c251a239-e0bd-4f45-9207-b76651072dd0
caps.latest.revision: ''
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: 818a71b8e0bc60168602e7fc0228c21319d08a21
ms.sourcegitcommit: 2e130e9f3ce8a7ffe373d7fba8b09e937c216386
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="connecting-to-the-server"></a>连接到服务器
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

本部分中的主题介绍使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 连接到 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]的选项和过程。  

[!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] 可以使用 Windows 身份验证或使用 SQL Server 身份验证连接到 [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] 。 默认情况下， [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] 尝试使用 Windows 身份验证连接到服务器。  

## <a name="in-this-section"></a>本節內容  

|主题|Description|  
|---------|---------------|  
|[如何：使用 Windows 身份验证进行连接](../../connect/php/how-to-connect-using-windows-authentication.md)|介绍如何使用 Windows 身份验证建立连接。|  
|[如何：使用 SQL Server 身份验证进行连接](../../connect/php/how-to-connect-using-sql-server-authentication.md)|介绍如何使用 SQL Server 身份验证建立连接。|  
|[如何：使用 Azure Active Directory 身份验证进行连接](../../connect/php/azure-active-directory.md)|描述如何设置身份验证模式和使用 Azure Active Directory 标识进行连接。|  
|[如何：在指定端口上连接](../../connect/php/how-to-connect-on-a-specified-port.md)|介绍如何在指定端口上连接到服务器。|  
|[连接池](../../connect/php/connection-pooling-microsoft-drivers-for-php-for-sql-server.md)|提供有关驱动程序中的连接池的信息。|  
|[如何：禁用多个活动的结果集 (MARS)](../../connect/php/how-to-disable-multiple-active-resultsets-mars.md)|介绍如何在建立连接时禁用 MARS 功能。|  
|[连接选项](../../connect/php/connection-options.md)|列出在包含连接属性的关联阵列中允许的选项。|  
|[对 LocalDB 的支持](../../connect/php/php-driver-for-sql-server-support-for-localdb.md)|介绍对 LocalDB 功能的 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] 支持，该支持已在 [!INCLUDE[ssSQL11](../../includes/sssql11_md.md)]中添加。|  
|[对高可用性、 灾难恢复的支持](../../connect/php/php-driver-for-sql-server-support-for-high-availability-disaster-recovery.md)|讨论如何配置你的应用程序以充分利用添加功能的高可用性、 灾难恢复[!INCLUDE[ssSQL11](../../includes/sssql11_md.md)]。|  
|[连接到 Microsoft Azure SQL 数据库](../../connect/php/connecting-to-microsoft-azure-sql-database.md)|讨论如何连接到 Azure SQL 数据库。|  
|[连接复原](../../connect/php/connection-resiliency.md)|讨论重新连接断开连接复原功能。|  

## <a name="see-also"></a>另请参阅  
[For PHP for SQL Server 编程 Microsoft 驱动程序的指南](../../connect/php/programming-guide-for-php-sql-driver.md)

[示例应用程序（SQLSRV 驱动程序）](../../connect/php/example-application-sqlsrv-driver.md)  
