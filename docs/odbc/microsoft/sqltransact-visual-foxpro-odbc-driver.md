---
title: SQLTransact （Visual FoxPro ODBC 驱动程序） |Microsoft 文档
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
- SQLTransact function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 92cf86c0-f7a8-44d7-b59f-a1342677440b
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4f787e04610187011b12c25ce738432066120365
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sqltransact-visual-foxpro-odbc-driver"></a>SQLTransact （Visual FoxPro ODBC 驱动程序）
> [!NOTE]  
>  本主题包含 Visual FoxPro ODBC 驱动程序相关的信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
 支持： 完整  
  
 ODBC API 一致性： 核心级别  
  
 请求对所有语句句柄的所有活动操作的提交或回滚操作 (*hstmt*s) 关联的连接或与环境句柄，关联的所有连接*henv*。 **SQLTransact**仅适用于数据源[数据库](../../odbc/microsoft/visual-foxpro-terminology.md)。  
  
 如果提交失败时在手动模式下，则事务会保持活动状态，则你可以选择回滚事务，或重试提交操作。 如果在自动事务模式下，提交操作失败，事务将自动回滚;事务不能为非活动状态。  
  
 有关详细信息，请参阅[SQLTransact](../../odbc/reference/syntax/sqltransact-function.md)中*ODBC 程序员参考*。
