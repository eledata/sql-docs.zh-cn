---
title: 事务支持 |Microsoft 文档
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
- transactions [ODBC], degree of support
ms.assetid: d56e1458-8da2-4d73-a777-09e045c30a33
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 87749f1401ebd435e32537bee2d721d013339ad7
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="transaction-support"></a>事务支持
对事务的程度是支持的驱动程序定义的。 ODBC 旨在在具有无需管理其数据的多个更新的单用户或桌面数据库上实现。 此外，某些支持事务的数据库执行因此仅对 SQL; 的数据操作语言 (DML) 语句没有限制或特殊事务语义与使用的数据定义语言 (DDL) 事务处于活动状态时。 也就是说，可能有对表的多个同时进行更新，但不是能为更改的数量和事务处理期间定义的表的事务支持。  
  
 应用程序确定是否支持事务，是否 DDL 可以包含在一个事务，并包括 DDL 在事务中，通过调用任何特殊影响**SQLGetInfo** SQL_TXN_CAPABLE 选项。 有关详细信息，请参阅[SQLGetInfo](../../../odbc/reference/syntax/sqlgetinfo-function.md)函数说明。  
  
 如果该驱动程序不支持事务，但应用程序 （使用 API 以外 ODBC） 的能力锁定和解锁数据，应用程序可以实现锁定和解锁的记录和表根据需要的事务的支持。 若要实现帐户传输示例，应用程序将锁定这两个帐户的记录、 将复制的当前值、 借方的第一个帐户，信用额度第二个帐户和解锁记录。 如果任何步骤失败，则应用程序将重置使用副本的帐户。  
  
 支持事务的甚至数据源可能不能以支持多个事务在特定环境中一次。 应用程序调用**SQLGetInfo** SQL_MULTIPLE_ACTIVE_TXN 选项，以确定数据源是否可以在同一环境中的多个连接上支持同时进行的活动事务。 因为每个连接的一个事务，这是仅有趣的应用程序有多个连接到同一数据源。
