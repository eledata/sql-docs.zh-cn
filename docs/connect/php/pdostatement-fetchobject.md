---
title: PDOStatement::fetchObject | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.prod_service: drivers
ms.service: ''
ms.component: php
ms.reviewer: ''
ms.suite: sql
ms.technology:
- drivers
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71ad1932-cab3-4c29-8950-f5e82547d3b5
caps.latest.revision: ''
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 8cd17e076c98a8ed9a14b388b1badb2330a9d68d
ms.sourcegitcommit: 2e130e9f3ce8a7ffe373d7fba8b09e937c216386
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="pdostatementfetchobject"></a>PDOStatement::fetchObject
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

以对象的形式检索下一行。  
  
## <a name="syntax"></a>语法  
  
```  
  
mixed PDOStatement::fetchObject([ $class_name[,$ctor_args ]] )  
```  
  
#### <a name="parameters"></a>Parameters  
$*class_name*： 一个可选的字符串，指定要创建的类的名称。 默认值为 stdClass。  
  
$*ctor_args*： 自定义类构造函数的参数个数的可选数组。  
  
## <a name="return-value"></a>返回值  
如果成功，则返回带有该类的实例的对象。 属性将映射到列。 如果失败，则返回 false。  
  
## <a name="remarks"></a>注释  
已在 [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)]的版本 2.0 中添加了对 PDO 的支持。  
  
## <a name="example"></a>示例  
  
```  
<?php  
   $server = "(local)";  
   $database = "AdventureWorks";  
   $conn = new PDO( "sqlsrv:server=$server ; Database = $database", "", "");  
  
   $stmt = $conn->query( "select * from Person.ContactType where ContactTypeID < 5 " );  
   $result = $stmt->fetchObject();  
   print $result->Name;  
?>  
```  
  
## <a name="see-also"></a>另请参阅  
[PDOStatement 类](../../connect/php/pdostatement-class.md)

[PDO](http://php.net/manual/book.pdo.php)  
  
