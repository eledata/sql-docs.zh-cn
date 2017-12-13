---
title: "SQLCancel |Microsoft 文档"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.service: 
ms.component: native-client-odbc-api
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: SQLCancel function
ms.assetid: d4c965ae-c1ac-4e9d-b4b9-32b561401106
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 5b7417ac3020b3d8d578631df9c52c415fb76af6
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2017
---
# <a name="sqlcancel"></a>SQLCancel
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]
[!INCLUDE[SNAC_Deprecated](../../includes/snac-deprecated.md)]

  [SQLCancel](http://go.microsoft.com/fwlink/?LinkId=203516)主题指出在 ODBC 2.x，如果应用程序调用**SQLCancel**语句上进行任何处理时**SQLCancel**具有相同的效果**SQLFreeStmt**与**SQL_CLOSE**选项; 此行为定义仅出于完整性考虑和应用程序应调用**SQLFreeStmt**或**SQLCloseCursor**关闭游标。 但即使你[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]本机客户端应用程序设置为 3.5.x 的 ODBC API 版本或更高版本， **SQLCancel**函数将使用 ODBC 2.x 行为。  
  
## <a name="see-also"></a>另请参阅  
 [SQLCancel](http://go.microsoft.com/fwlink/?LinkId=203516)   
 [ODBC API 实现细节](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  