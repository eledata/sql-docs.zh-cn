---
title: 多线程应用程序 |Microsoft 文档
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
- threads [SQL Server], multithreaded applications
- ODBC applications, multithreaded applications
- asynchronous operations [SQL Server Native Client]
- SQL Server Native Client ODBC driver, multithreaded applications
- multithreaded applications [SQL Server Native Client]
ms.assetid: d352c91a-6e08-4e50-9f3e-a37892d9c2cc
caps.latest.revision: 29
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
monikerRange: '>= aps-pdw-2016 || = azuresqldb-current || = azure-sqldw-latest || >= sql-server-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: f35701b0490dc059942868c9970af432b5250abc
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="creating-a-driver-application---multithreaded-applications"></a>创建多线程应用程序的驱动程序应用程序-
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../../includes/snac-deprecated.md)]

  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC 驱动程序是多线程驱动程序。 编写多线程应用程序是使用异步调用处理多个 ODBC 调用的替代方法。 线程可以进行同步 ODBC 调用，而在第一个线程被阻塞以等待其调用的响应时可以处理其他线程。 此模型比进行异步调用效率更高，因为它避免了诸如网络流量的开销以及对 SQL_STILL_EXECUTING 执行重复的 ODBC 函数调用测试。  
  
 异步模式仍是一种有效的处理方法。 尽管多线程模型的性能不断改进，但是仍没有必要对异步应用程序进行重新编写。 如果用户正在转换使用 DB-Library 异步模型的 DB-Library 应用程序，将它们转换为 ODBC 异步模型更为容易。  
  
## <a name="see-also"></a>另请参阅  
 [创建 SQL Server Native Client ODBC 驱动程序应用程序](../../../relational-databases/native-client/odbc/creating-a-driver-application.md)  
  
  
