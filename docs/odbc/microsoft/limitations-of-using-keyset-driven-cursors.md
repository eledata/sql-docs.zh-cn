---
title: 使用键集驱动游标的限制 |Microsoft 文档
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
- ODBC driver for Oracle [ODBC], cursors
- keyset-driven cursors [ODBC]
ms.assetid: 59d86fed-387c-4719-9550-36343e74da44
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f6661ca9104e683cdac84cb3d533736d3a02f42f
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="limitations-of-using-keyset-driven-cursors"></a>使用键集驱动游标的限制
> [!IMPORTANT]  
>  将 Windows 的未来版本中删除该功能。 请避免在新的开发工作中使用该功能，并着手修改当前还在使用该功能的应用程序。 相反，使用提供的 Oracle 的 ODBC 驱动程序。  
  
 你必须能够检索用于查询的表的单个 ROWID 列。 在联接、 查询或包含 DISTINCT、 GROUP BY、 UNION、 INTERSECT 的语句上或减去子句，不能使用键集驱动游标。  
  
 此外，如果你的应用程序使用表别名，将不会工作键集驱动游标;只进或静态游标类型是必需的。 使用键集游标类型与表别名将导致以下错误:"[Microsoft] [适用于 Oracle 的 ODBC 驱动程序] 不能使用键集驱动游标上联接，使用 union、 intersect 或减或只读结果集。"  
  
> [!NOTE]  
>  由于该驱动程序处理发送到 Oracle 服务器的 SQL 语句的方法，Oracle 内部返回以下错误消息:"ORA 00964： 表名称不是在从列表中。"
