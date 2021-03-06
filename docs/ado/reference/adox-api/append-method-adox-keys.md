---
title: "Append 方法 （ADOX 键） |Microsoft 文档"
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
f1_keywords:
- Keys::Append
- Keys::raw_Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: 215a5391-f422-42ec-99ea-4e6fbb5d3d64
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 8d1f8938adf51ee1f38de29b85753095d55d7703
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="append-method-adox-keys"></a>Append 方法 （ADOX 键）
添加新[密钥](../../../ado/reference/adox-api/key-object-adox.md)对象传递给[密钥](../../../ado/reference/adox-api/keys-collection-adox.md)集合。  
  
## <a name="syntax"></a>语法  
  
```  
  
Keys.Append Key [,KeyType] [,Column] [,RelatedTable] [,RelatedColumn]  
```  
  
#### <a name="parameters"></a>Parameters  
 *Key*  
 **密钥**要追加的对象或创建并追加密钥的名称。  
  
 *KeyType*  
 選擇性。 A**长**值，该值指定键的类型。 *密钥*参数对应于[类型](../../../ado/reference/adox-api/type-property-key-adox.md)属性**密钥**对象。  
  
 *列*  
 選擇性。 A**字符串**值，该值指定要编制索引的列的名称。 *列*参数对应于值[名称](../../../ado/reference/adox-api/name-property-adox.md)属性[列](../../../ado/reference/adox-api/column-object-adox.md)对象。  
  
 *RelatedTable*  
 選擇性。 A**字符串**值，该值指定相关的表的名称。 *RelatedTable*参数对应于值**名称**属性[表](../../../ado/reference/adox-api/table-object-adox.md)对象。  
  
 *RelatedColumn*  
 選擇性。 A**字符串**值，该值指定外键的相关列的名称。 *RelatedColumn*参数对应于值**名称**属性[列](../../../ado/reference/adox-api/column-object-adox.md)对象。  
  
## <a name="remarks"></a>注释  
 *列*参数可以采用的列名称或列名称的数组。  
  
## <a name="applies-to"></a>适用范围  
 [项集合 (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)  
  
## <a name="see-also"></a>另请参阅  
 [密钥追加方法、 密钥类型、 RelatedColumn、 RelatedTable 和 UpdateRule 属性示例 (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Append 方法 （ADOX 列）](../../../ado/reference/adox-api/append-method-adox-columns.md)   
 [Append 方法 （ADOX 组）](../../../ado/reference/adox-api/append-method-adox-groups.md)   
 [Append 方法 （ADOX 索引）](../../../ado/reference/adox-api/append-method-adox-indexes.md)   
 [Append 方法 （ADOX 过程）](../../../ado/reference/adox-api/append-method-adox-procedures.md)   
 [Append 方法 （ADOX 表）](../../../ado/reference/adox-api/append-method-adox-tables.md)   
 [Append 方法 （ADOX 用户）](../../../ado/reference/adox-api/append-method-adox-users.md)   
 [Append 方法（ADOX 视图）](../../../ado/reference/adox-api/append-method-adox-views.md)
