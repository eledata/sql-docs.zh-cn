---
title: 显式分配描述符 |Microsoft 文档
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
- descriptors [ODBC], allocating and freeing
- explicitly allocated descriptors [ODBC]
- allocating and freeing descriptors [ODBC]
ms.assetid: f590251d-56a6-4d58-a405-9e85e68fbc47
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 5f92ad0615047da9fd775ec8faa491e8d9a4ba79
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="explicitly-allocated-descriptors"></a>显式分配的描述符
应用程序可以显式分配随时连接到数据库的连接上的应用程序描述符。 通过指定语句的属性处理使用该描述符句柄**SQLSetStmtAttr**，应用程序将使用该描述符以代替对应的驱动程序隐式分配应用程序描述符。 应用程序不能指定备用实现描述符。  
  
 应用程序可以将多个语句关联显式分配的描述符。 仅当应用程序实际连接到数据库时，才描述符可以是显式分配的描述符。 应用程序可以通过来释放此类描述符显式或隐式释放其连接。
