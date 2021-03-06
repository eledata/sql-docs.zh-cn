---
title: SQLSetScrollOptions （Visual FoxPro ODBC 驱动程序） |Microsoft 文档
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
- SQLSetScrollOptions function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 693e6e28-a845-41b1-9622-5058b0d87229
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3e1fa742dc9c17e2e72b6c17732a10dd04662781
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sqlsetscrolloptions-visual-foxpro-odbc-driver"></a>SQLSetScrollOptions （Visual FoxPro ODBC 驱动程序）
> [!NOTE]  
>  本主题包含 Visual FoxPro ODBC 驱动程序相关的信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
 支持： 部分  
  
 ODBC API 一致性： 级别 2  
  
 设置控制游标语句句柄，与关联的行为的选项*hstmt*。  
  
 Visual FoxPro ODBC 驱动程序还支持仅 SQL_CONCUR_READ_ONLY;它不支持*fConcurrency*值 SQL_CONCUR_ROWVER。 该驱动程序可将 SQL_KEYSET_SIZE、 SQL_CURSOR_DYNAMIC 和 SQL_CURSOR_KEYSET_DRIVEN 转换为 SQL_SCROLL_STATIC，警告 ODBC_01S02 处理。  
  
 有关详细信息，请参阅[SQLSetScrollOptions](../../odbc/reference/syntax/sqlsetscrolloptions-function.md)中*ODBC 程序员参考*。
