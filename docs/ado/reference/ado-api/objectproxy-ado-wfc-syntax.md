---
title: "ObjectProxy (ADO-WFC 语法) |Microsoft 文档"
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: 
ms.component: ado
ms.technology:
- drivers
ms.custom: 
ms.date: 01/19/2017
ms.reviewer: 
ms.suite: sql
ms.tgt_pltfrm: 
ms.topic: article
apitype: COM
helpviewer_keywords:
- ObjectProxy collection [ADO]
ms.assetid: f68f58bc-ad28-46cc-9fb3-099e1a678397
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 19884e98de3a6ed8070dcd30d3965c7ad9e77a4c
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="objectproxy-ado---wfc-syntax"></a>ObjectProxy (ADO-WFC 语法)
**ObjectProxy**对象表示的服务器，并且由返回**createObject**方法[DataSpace](../../../ado/reference/rds-api/dataspace-object-rds.md)对象。 ObjectProxy 类具有一个方法，**调用**，其可以调用服务器上的方法并返回从该调用而产生的对象。  
  
 **package com.ms.wfc.data**  
  
## <a name="methods"></a>方法  
  
### <a name="call-method-adowfc-syntax"></a>调用方法 （ADO/WFC 语法）  
 调用由 ObjectProxy 所表示的服务器上的方法。 （可选） 可以作为对象的数组传递方法自变量。  
  
#### <a name="syntax"></a>语法  
  
```  
public Object ObjectProxy.( String method )  
public Object ObjectProxy.( String method, Object[] args)  
```  
  
#### <a name="returns"></a>返回  
 对象  
 从调用的方法而产生的对象。  
  
#### <a name="parameters"></a>Parameters  
 *ObjectProxy*  
 **ObjectProxy**表示服务器的对象。  
  
 *方法*  
 一个字符串，包含要在服务器上调用的方法的名称。  
  
 *参数*  
 選擇性。 在服务器上的方法参数的对象的数组。 Java 数据类型自动转换为适用于服务器上使用的数据类型。
