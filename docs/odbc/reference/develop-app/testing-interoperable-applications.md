---
title: 测试可互操作的应用程序 |Microsoft 文档
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
- interoperability [ODBC], testing interoperable applications
- testing interoperable applications [ODBC]
ms.assetid: 489083cb-8430-40be-9ef2-d75b9a2eea88
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 4cd98e6311d7d08b6faed0cb4759523642e70a5d
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="testing-interoperable-applications"></a>测试可互操作的应用程序
测试可互操作的应用程序是在最耗时业务，也在坏的情况下无法由于市场上不断显示新的驱动程序。 但是，可能会测试很合理程度。 仅需要针对这些驱动程序，可确保以支持测试具有有限或低的互操作性的应用程序。 但是，它们必须进行完全测试针对这些驱动程序。  
  
 高度可互操作的应用程序针对的所有驱动程序不能实际进行测试。 大多数应用程序开发人员可以执行操作的最佳是其完全针对少量的驱动程序和几个 cursorily 进行测试。 经过测试的驱动程序应为应用程序的市场; 中最受欢迎的 Dbms 包括最常用的驱动程序如果市场涵盖所有 Dbms，应测试台式机和服务器 Dbms 的驱动程序。  
  
 测试 ODBC 应用程序中的问题之一是涉及的组件数： 应用程序本身、 驱动程序管理器、 驱动程序、 DBMS，并可能是网络软件或网关。 应用程序可以更加轻松地通过发布通过 ODBC 函数返回的错误消息来跟踪错误**SQLGetDiagField**和**SQLGetDiagRec**。 这些消息标识的制造商和在其中发生错误的组件。 有关详细信息，请参阅[诊断](../../../odbc/reference/develop-app/diagnostics.md)。
