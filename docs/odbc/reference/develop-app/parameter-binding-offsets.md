---
title: 参数绑定偏移量 |Microsoft 文档
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
- offsets of parameters [ODBC]
- binding offsets of parameters [ODBC]
ms.assetid: 309339e9-9ccd-4a58-8aa4-b6dc88f4eb7c
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 2d5228c7ce920eb56b0b947784b3d5a7bb2d6266
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="parameter-binding-offsets"></a>参数绑定偏移量
应用程序可以指定偏移量添加绑定参数的缓冲区地址和相应的长度/指示器缓冲区地址时**SQLExecDirect**或**SQLExecute**调用。 这些添加的结果确定这些操作中使用的地址。  
  
 绑定偏移量允许应用程序更改而不调用绑定**SQLBindParameter**以前绑定参数。 调用**SQLBindParameter**重新绑定参数更改的缓冲区地址和长度/指示器指针。 重新绑定相对的偏移量，另一方面，只需将偏移量添加到现有的绑定的参数的缓冲区地址和长度/指示器缓冲区地址。 偏移量使用时，提供的绑定是如何布局应用程序缓冲区的"模板"和应用程序可以通过将移动此"模板"到不同区域的内存更改偏移量。 新的偏移量可以在任何时指定，并且始终会将其添加到最初绑定值。  
  
 若要指定绑定偏移量，应用程序 SQL_ATTR_PARAM_BIND_OFFSET_PTR 语句将该属性设置 SQLINTEGER 缓冲区的地址。 应用程序调用一个函数，使用的绑定之前，它会偏移量的此缓冲区中的字节，只要参数缓冲区地址和长度/指示器缓冲区地址都不为 0，并且绑定的参数为 SQL 语句中。 地址和偏移量之和必须是有效的地址。 （这意味着，一个或两个偏移量和偏移量添加到的地址可以是无效的只要其总和是有效的地址。）  
  
> [!NOTE]  
>  绑定偏移量不受 ODBC 2。*x*驱动程序。
