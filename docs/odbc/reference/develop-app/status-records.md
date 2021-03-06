---
title: 状态记录 |Microsoft 文档
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
- diagnostic information [ODBC], diagnostic records
- status records [ODBC]
- diagnostic records [ODBC]
ms.assetid: 4a987f69-158f-4cc4-a31b-2b7dd8dcbb87
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: e748612bf8293a0c7fca29b0baa21c9278e44d15
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="status-records"></a>状态记录
中的状态记录的字段包含有关特定错误或警告的驱动程序管理器、 驱动程序或数据源，包括 SQLSTATE、 本机错误号、 诊断消息，列数和行号返回的信息。 仅当该函数将返回 SQL_ERROR、 SQL_SUCCESS_WITH_INFO、 SQL_NO_DATA、 SQL_NEED_DATA 或 SQL_STILL_EXECUTING，可以创建状态记录。 中的状态记录的字段的完整列表，请参阅[SQLGetDiagField](../../../odbc/reference/syntax/sqlgetdiagfield-function.md)函数说明。  
  
 本部分包含以下主题。  
  
-   [状态记录的序列](../../../odbc/reference/develop-app/sequence-of-status-records.md)  
  
-   [SQLSTATEs](../../../odbc/reference/develop-app/sqlstates.md)  
  
-   [诊断消息](../../../odbc/reference/develop-app/diagnostic-messages.md)
