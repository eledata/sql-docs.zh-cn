---
title: 值列表参数 |Microsoft 文档
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
- catalog functions [ODBC], arguments
- arguments in catalog functions [ODBC], value list
- value list arguments [ODBC]
ms.assetid: 863837be-603b-4c7a-8b96-b71014037ee5
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 47ef5564ae56f04877aa33b4ffb0f1644aa4d605
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="value-list-arguments"></a>值列表自变量
值列表参数由逗号分隔值要用于匹配的列表组成。 ODBC 目录函数没有只有一个值列表自变量： *TableType*中的参数**SQLTables**。 设置*TableType*到 null 指针是相同好像设置为 SQL_ALL_TABLE_TYPES，可枚举的值列表的所有可能的成员。 此参数不受 SQL_ATTR_METADATA_ID 语句属性。 有关详细信息，请参阅[SQLTables](../../../odbc/reference/syntax/sqltables-function.md)函数说明。
