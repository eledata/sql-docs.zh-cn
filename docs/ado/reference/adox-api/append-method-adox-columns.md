---
title: "Append 方法 （ADOX 列） |Microsoft 文档"
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
- Columns::raw_Append
- Columns::Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: 7a46d23c-efef-4ec7-815d-cd3ac86787dd
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 3e67dc9f6240e94dea2e4494906453ba8e4cfad1
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="append-method-adox-columns"></a>Append 方法 （ADOX 列）
添加新[列](../../../ado/reference/adox-api/column-object-adox.md)对象传递给[列](../../../ado/reference/adox-api/columns-collection-adox.md)集合。  
  
## <a name="syntax"></a>语法  
  
```  
  
Columns.Append Column [,Type] [,DefinedSize]  
```  
  
#### <a name="parameters"></a>Parameters  
 *列*  
 **列**要追加的对象或要创建并追加的列的名称。  
  
 *类型*  
 選擇性。 A**长**值，该值指定列的数据类型。 *类型*参数对应于[类型](../../../ado/reference/adox-api/type-property-column-adox.md)属性**列**对象。  
  
 *DefinedSize*  
 選擇性。 A**长**值，该值指定列的大小。 *DefinedSize*参数对应于[DefinedSize](../../../ado/reference/adox-api/definedsize-property-adox.md)属性**列**对象。  
  
> [!NOTE]
>  在追加时，将发生错误**列**到**列**集合[索引](../../../ado/reference/adox-api/index-object-adox.md)如果**列**中不存在[表](../../../ado/reference/adox-api/table-object-adox.md)已追加到[表](../../../ado/reference/adox-api/tables-collection-adox.md)集合。  
  
## <a name="applies-to"></a>适用范围  
 [列集合 (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)  
  
## <a name="see-also"></a>另请参阅  
 [列和表追加方法名称的属性示例 (VB)](../../../ado/reference/adox-api/columns-and-tables-append-methods-name-property-example-vb.md)   
 [密钥追加方法、 密钥类型、 RelatedColumn、 RelatedTable 和 UpdateRule 属性示例 (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [ParentCatalog 属性示例 (VB)](../../../ado/reference/adox-api/parentcatalog-property-example-vb.md)   
 [Append 方法 （ADOX 组）](../../../ado/reference/adox-api/append-method-adox-groups.md)   
 [Append 方法 （ADOX 索引）](../../../ado/reference/adox-api/append-method-adox-indexes.md)   
 [Append 方法 （ADOX 键）](../../../ado/reference/adox-api/append-method-adox-keys.md)   
 [Append 方法 （ADOX 过程）](../../../ado/reference/adox-api/append-method-adox-procedures.md)   
 [Append 方法 （ADOX 表）](../../../ado/reference/adox-api/append-method-adox-tables.md)   
 [Append 方法 （ADOX 用户）](../../../ado/reference/adox-api/append-method-adox-users.md)   
 [Append 方法（ADOX 视图）](../../../ado/reference/adox-api/append-method-adox-views.md)
