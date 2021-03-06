---
title: 游标库缓存 |Microsoft 文档
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
- ODBC cursor library [ODBC], cache
- cursor library [ODBC], cache
- cache [ODBC]
ms.assetid: d6a91cd6-3905-4e3a-98ab-37fce893dbe1
caps.latest.revision: 8
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4558289d76343993511bd03e3f85a76fd8ce2bf8
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="cursor-library-cache"></a>游标库缓存
> [!IMPORTANT]  
>  将 Windows 的未来版本中删除该功能。 避免在新的开发工作中使用此功能，并计划修改当前使用此功能的应用程序。 Microsoft 建议使用驱动程序的游标功能。  
  
 在结果集中的数据的每一行，光标库将数据缓存以每个绑定的列中，每个绑定的列中的数据的长度和行的状态。 游标库使用这两个缓存中的值来返回通过**SQLFetch**和**SQLFetchScroll**和构造搜索定位操作语句。 有关详细信息，请参阅[构造搜索语句](../../../odbc/reference/appendixes/constructing-searched-statements.md)。  
  
 本部分包含以下主题。  
  
-   [列数据](../../../odbc/reference/appendixes/column-data.md)  
  
-   [列数据的长度](../../../odbc/reference/appendixes/length-of-column-data.md)  
  
-   [行状态](../../../odbc/reference/appendixes/row-status.md)  
  
-   [缓存的位置](../../../odbc/reference/appendixes/location-of-cache.md)
