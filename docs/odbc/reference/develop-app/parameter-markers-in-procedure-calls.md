---
title: 在过程调用中的参数标记 |Microsoft 文档
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
- SQL statements [ODBC], interoperability
- parameter markers [ODBC]
- interoperability of SQL statements [ODBC], parameter markers
ms.assetid: cda56f2b-6eec-4cbc-8dbb-36d8fa9f9216
caps.latest.revision: 6
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 7d603c656e16cfc092d3c085092d427eb8a5c12e
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="parameter-markers-in-procedure-calls"></a>在过程调用中的参数标记
当调用接受参数的过程，可互操作的应用程序应使用参数标记，而不是文本的参数值。 某些数据源不支持在过程调用中使用的文字参数值。 有关参数的详细信息，请参阅[语句参数](../../../odbc/reference/develop-app/statement-parameters.md)。 有关调用过程的详细信息，请参阅[过程调用](../../../odbc/reference/develop-app/procedure-calls.md)，本部分中更高版本。
