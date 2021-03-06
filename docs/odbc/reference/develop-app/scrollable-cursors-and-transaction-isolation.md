---
title: 可滚动游标，事务隔离 |Microsoft 文档
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
- isolation levels [ODBC]
- scrollable cursors [ODBC]
- transaction isolation [ODBC]
- transactions [ODBC], isolation
ms.assetid: f0216f4a-46e3-48ae-be0a-e2625e8403a6
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 68517f733dcb10f75669341bdef861b035b79a72
ms.sourcegitcommit: 7a6df3fd5bea9282ecdeffa94d13ea1da6def80a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="scrollable-cursors-and-transaction-isolation"></a>可滚动游标，事务隔离
下表列出的因素控制的可见性更改。  
  
|所做的更改：|可见性取决于：|  
|----------------------|----------------------------|  
|游标|游标类型，游标实现|  
|同一事务中的其他语句|游标类型|  
|在其他事务中的语句|游标类型，事务隔离级别|  
  
 这些因素下图所示。  
  
 ![控制的可见性更改因素](../../../odbc/reference/develop-app/media/pr23.gif "pr23")  
  
 下表总结了每种游标类型能够检测通过本身、 其自己的事务中的其他操作以及由其他事务所做的更改。 后一种更改的可见性取决于游标类型和包含光标的事务的隔离级别。  
  
|光标 type\action|自己|拥有<br /><br /> Txn|其他<br /><br /> Txn<br /><br /> (RU[a])|其他<br /><br /> Txn<br /><br /> (RC[a])|其他<br /><br /> Txn<br /><br /> (RR[a])|其他<br /><br /> Txn<br /><br /> (S[a])|  
|-------------------------|----------|-----------------|----------------------------------|----------------------------------|----------------------------------|---------------------------------|  
|静态|||||||  
|Insert|Maybe [b]|否|“否”|“否”|“否”|否|  
|Update|Maybe [b]|否|“否”|“否”|“否”|否|  
|删除|Maybe [b]|否|“否”|“否”|“否”|否|  
|键集驱动|||||||  
|Insert|Maybe [b]|否|“否”|“否”|“否”|否|  
|Update|是|用户帐户控制|用户帐户控制|用户帐户控制|是|否|  
|删除|Maybe [b]|是|用户帐户控制|用户帐户控制|是|否|  
|Dynamic|||||||  
|Insert|是|用户帐户控制|用户帐户控制|用户帐户控制|用户帐户控制|否|  
|Update|是|用户帐户控制|用户帐户控制|用户帐户控制|是|否|  
|删除|是|用户帐户控制|用户帐户控制|用户帐户控制|是|否|  
  
 [a] 中括号的字母指示包含游标的事务的隔离级别（在其中进行了更改） 另一个事务的隔离级别是不相关。  
  
 未提交的 RU： 读取  
  
 RC： 读提交  
  
 RR: Repeatable read  
  
 可序列化的 s:  
  
 [b] 依赖于光标的实现方式。 通过中的 SQL_STATIC_SENSITIVITY 选项报告光标是否可以检测此类更改的是**SQLGetInfo**。
