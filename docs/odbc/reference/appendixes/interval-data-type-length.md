---
title: 间隔数据类型长度 |Microsoft 文档
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
- data types [ODBC], interval data types
- length of data types [ODBC]
- interval data type [ODBC], length
ms.assetid: e9eb38d8-f9db-4401-8c62-aa394054cbbf
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 67cfccf9823f59e02ece652acc35f26b07e3ce89
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="interval-data-type-length"></a>间隔数据类型长度
以下规则用于确定以字符为单位的间隔数据类型的长度。 长度用的字符数表示。 字节数取决于的字符集。 长度包括以下值加在一起：  
  
-   每个字段中并不是前导字段的时间间隔的两个字符。  
  
-   对于前导字段，是明示或隐式前导精度的字符数。 如果未指定前导精度，则默认值为 2。  
  
-   字段之间的分隔符的的一个字符。  
  
-   加上 1 明示或暗示秒精度。 如果未指定秒精度，则默认值为 6。  
  
 每个间隔数据类型的特定列长度值包含在[列大小](../../../odbc/reference/appendixes/column-size.md)。
