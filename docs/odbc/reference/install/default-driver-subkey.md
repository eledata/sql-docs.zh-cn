---
title: 默认驱动程序子项 |Microsoft 文档
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
- default subkey [ODBC]
- registry entries for components [ODBC], default subkey
- subkeys [ODBC], default subkey
- drivers subkey [ODBC]
ms.assetid: 9e58b24f-ebfc-4286-a272-0843b4d6f2d5
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 64edd0f2a796c36b9c8a6efad971c7841b61a7ec
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="default-driver-subkey"></a>默认驱动程序子项
默认子项包含单个值，该值描述默认数据源使用的驱动程序。 下表中显示此值的格式。  
  
|名称|数据类型|Data|  
|----------|---------------|----------|  
|**驱动程序**|REG_SZ|*默认驱动程序说明*|  
  
 *默认驱动程序说明*名称是描述的驱动程序的 ODBC 驱动程序子项下的值的名称相同。  
  
 例如，如果默认数据源使用的 SQL Server 驱动程序，可能是默认子项下的值：  
  
```  
Driver : REG_SZ : SQL Server  
```  
  
> [!NOTE]  
>  包含在默认的子项的默认驱动程序可以引用默认用户 DSN 或默认系统 DSN。 如果默认用户 DSN 和默认系统 DSN 已创建，因此它可能不是有效条目首先创建 DSN DSN 最后，创建由确定默认驱动程序。
