---
title: SQL 92 法规遵从性 |Microsoft 文档
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
- Jet-based ODBC drivers [ODBC], SQL-92 compliance
- desktop database drivers [ODBC], SQL-92 compliance
- SQL-92 compliance [ODBC]
- ODBC desktop database drivers [ODBC], SQL-92 compliance
ms.assetid: 50c8c7df-df01-4f4d-ad62-d059cf29d73a
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 09b1a044a362207b5bc1c04d3a90e210ad7c8137
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sql-92-compliance"></a>SQL 92 法规遵从性
ODBC 桌面数据库驱动程序和基础的 Microsoft Jet 引擎不符合 SQL 92。 它们支持 SQL 92 中已定义的许多功能。 在 SQL 92 中不支持驱动程序中支持一些功能。 有关详细信息，请参阅*Microsoft Jet 数据库引擎程序员指南*。 两者之间的主要区别如下：  
  
-   桌面数据库驱动程序使用 SQL 支持更强大超过这些指定的 SQL 92 表达式。  
  
-   不同的规则适用于 BETWEEN 谓词。  
  
-   桌面数据库驱动程序和 ANSI SQL 所使用的 SQL 支持不同的关键字。  
  
 Microsoft Jet SQL 不支持以下 SQL 92 功能：  
  
-   安全语句，例如授予和锁定。  
  
-   与聚合函数引用的 DISTINCT。  
  
 以下功能是中未指定的 SQL 92 桌面数据库驱动程序使用的 SQL 的增强功能：  
  
-   TRANSFORM 语句为交叉表查询提供支持。  
  
-   其他聚合函数 (**StDev**和**VarP**)。  
  
> [!NOTE]  
>  桌面数据库驱动程序支持标准的 ANSI 语法不支持对于 %（百分比） _ （下划线） * （星号） 和？ （问号）。
