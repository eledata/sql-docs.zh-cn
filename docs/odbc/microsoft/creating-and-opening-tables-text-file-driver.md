---
title: 创建和打开表 （文本文件驱动程序） |Microsoft 文档
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
- text file driver [ODBC], creating and opening tables
ms.assetid: e6a07dda-a665-4f5b-a8d6-9ff479700513
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 374a234f7c0f9eecc119e36d7dd4305a32745786
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="creating-and-opening-tables-text-file-driver"></a>创建和打开表 （文本文件驱动程序）
当使用文本驱动程序时，使用 Odbcinst.ini 中指定的格式创建一个新表。 如果未指定，CSVDELIMITED 格式中创建表。 默认情况下，默认为 11 个字符的整数列和 FLOAT 列默认为 22 个字符。 日期列使用 YYYY-月-日格式。 CHAR 和 LONGCHAR 列是 CREATE 语句中指定的宽度。
