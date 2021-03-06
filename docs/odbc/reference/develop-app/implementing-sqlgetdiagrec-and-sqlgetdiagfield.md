---
title: 实现 SQLGetDiagRec 和 SQLGetDiagField |Microsoft 文档
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: drivers
ms.service: ''
ms.component: odbc
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- diagnostic information [ODBC], SqlGetDiagField
- SQLGetDiagField function [ODBC], and SQLGetDiagRec
- SQLGetDiagRec function [ODBC], and SQLGetDiagField
- diagnostic information [ODBC], SqlGetDiagRec
- retrieving diagnostic information [ODBC]
ms.assetid: 11ba1857-b533-4517-8131-a2a8a0154a0a
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e4eda963538e6f5acb884e494a8c8a3dd533bf70
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="implementing-sqlgetdiagrec-and-sqlgetdiagfield"></a>实现 SQLGetDiagRec 和 SQLGetDiagField
**SQLGetDiagRec**和**SQLGetDiagField**由驱动程序管理器和每个驱动程序实现。 驱动程序管理器和每个驱动程序维护的每个环境、 连接、 语句和的描述符句柄的诊断记录，仅当另一个函数调用与将释放句柄或句柄释放这些记录。  
  
 尽管驱动程序管理器和每个驱动程序必须决定根据中排名第一条状态记录[状态记录序列](../../../odbc/reference/develop-app/sequence-of-status-records.md)，驱动程序管理器确定最终的记录序列。  
  
 **SQLGetDiagRec**和**SQLGetDiagField**不能开机自检有关自身的诊断记录。  
  
 本部分包含以下主题。  
  
-   [诊断处理规则](../../../odbc/reference/develop-app/diagnostic-handling-rules.md)  
  
-   [驱动程序管理器的角色](../../../odbc/reference/develop-app/role-of-the-driver-manager.md)  
  
-   [驱动程序的角色](../../../odbc/reference/develop-app/role-of-the-driver.md)
