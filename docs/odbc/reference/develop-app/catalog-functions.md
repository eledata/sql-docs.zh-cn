---
title: 目录函数 |Microsoft 文档
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
- catalog functions [ODBC], about catalog functions
- data dictionary [ODBC]
- catalog functions [ODBC]
- functions [ODBC], catalog functions
ms.assetid: 81ba9453-c085-47c0-b411-90ca6a5ee428
caps.latest.revision: 7
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a9ef633c9d5ee19489e8c796e99562ec26ec9d03
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="catalog-functions"></a>目录函数
所有数据库都有一个结构，它概述了将存储在数据库中的数据的方式。 例如，简单的销售订单数据库可能具有在下图中，在其中将使用的 ID 列链接的表中所示的结构。  
  
 ![显示一个简单的数据库的结构](../../../odbc/reference/develop-app/media/pr19.gif "pr19")  
  
 此结构，以及其他信息的权限，例如存储在一组称为数据库的系统表*目录，*即也称为*数据字典*。  
  
 应用程序可以发现通过调用此结构*目录函数*。 目录函数返回结果集和是否中的信息通常实现通过**选择**语句在目录中的表。 例如，应用程序可以请求包含系统上所有表的相关信息的结果集或包含特定表中的所有列的相关信息的结果集。  
  
 本部分包含以下主题。  
  
-   [目录数据的用法](../../../odbc/reference/develop-app/uses-of-catalog-data.md)  
  
-   [ODBC 中的目录函数](../../../odbc/reference/develop-app/catalog-functions-in-odbc.md)
