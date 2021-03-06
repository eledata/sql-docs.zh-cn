---
title: SQLDriverConnect （Visual FoxPro ODBC 驱动程序） |Microsoft 文档
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
- SQLDriverConnect function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 10492c8f-3a18-4971-9db8-879e878083b9
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: f463f7c1c71ef120c7fb5446e3edd1f77c791137
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sqldriverconnect-visual-foxpro-odbc-driver"></a>SQLDriverConnect （Visual FoxPro ODBC 驱动程序）
> [!NOTE]  
>  本主题包含 Visual FoxPro ODBC 驱动程序相关的信息。 有关此函数的常规信息，请参阅下的相应主题[ODBC API 参考](../../odbc/reference/syntax/odbc-api-reference.md)。  
  
 支持： 完整  
  
 ODBC API 一致性： 级别 1  
  
 连接到现有的数据源，可以是[数据库](../../odbc/microsoft/visual-foxpro-terminology.md)或目录的[释放表](../../odbc/microsoft/visual-foxpro-terminology.md)。 ODBC 属性关键字 UID 和 PWD 将被忽略。 下表列出的其他受支持的属性关键字。  
  
|ODBC 属性关键字|属性值|  
|----------------------------|---------------------|  
|DSN||  
|UID|Visual FoxPro ODBC 驱动程序被忽略，但不会生成错误。|  
|PWD|Visual FoxPro ODBC 驱动程序被忽略，但不会生成错误。|  
|驱动程序|名称和位置的 Visual FoxPro ODBC 驱动程序;由驱动程序管理器中实现。|  
  
|Visual FoxPro ODBC 驱动程序属性关键字|属性值|  
|-------------------------------------------------|---------------------|  
|BackgroundFetch|"是"或者"否"|  
|逐份打印|"计算机"或其他排序序列。 有关支持的排序规则序列的列表，请参阅[设置 COLLATE](../../odbc/microsoft/set-collate-command.md)。|  
|Description||  
|排他|"是"或者"否"|  
|SourceDB|完全限定的路径的目录包含零个或多个[释放表](../../odbc/microsoft/visual-foxpro-terminology.md)，或为绝对路径和文件名称[数据库](../../odbc/microsoft/visual-foxpro-terminology.md)。|  
|SourceType|"DBC"或者"DBF"|  
|版本||  
  
 如果未指定数据源名称，驱动程序管理器会提示用户输入的信息 (具体取决于的设置*fDriverCompletion*自变量)，然后继续。 如果需要详细信息，Visual FoxPro ODBC 驱动程序将显示提示对话框。  
  
 有关详细信息，请参阅[SQLDriverConnect](../../odbc/reference/syntax/sqldriverconnect-function.md)中*ODBC 程序员参考*。
