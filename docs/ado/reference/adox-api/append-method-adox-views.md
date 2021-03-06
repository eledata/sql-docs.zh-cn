---
title: "Append 方法 (ADOX Views) |Microsoft 文档"
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
- Views::raw_Append
- Views::Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: 6070fd58-3237-4c77-a966-5b39ce5d57e4
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: a5db1507f6574567cc6acd54e9ede053e36f1552
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="append-method-adox-views"></a>Append 方法 （ADOX 视图）
创建一个新[视图](../../../ado/reference/adox-api/view-object-adox.md)对象，并将其附加到[视图](../../../ado/reference/adox-api/views-collection-adox.md)集合。  
  
## <a name="syntax"></a>语法  
  
```  
  
Views.Append Name, Command  
```  
  
#### <a name="parameters"></a>Parameters  
 *名称*  
 A**字符串**值，该值指定要创建的视图的名称。  
  
 *Command*  
 ADO[命令](../../../ado/reference/ado-api/command-object-ado.md)对象，表示要创建的视图。  
  
## <a name="remarks"></a>注释  
 在具有名称和特性中指定的数据源中创建新视图**命令**对象。  
  
 如果用户指定的命令文本表示一个过程，而不是一个视图，则行为将取决于提供程序。 **追加**如果提供程序不支持保留命令将失败。  
  
> [!NOTE]
>  使用用于 Microsoft Jet 的 OLE DB 提供程序时**视图**集合**追加**方法将允许你指定**过程**而不是**视图**中*命令*参数。 **过程**将添加到数据源，将添加到**视图**集合。 后**追加**，如果**过程**和**视图**刷新集合，**过程**将不再在**视图**集合并将显示在**过程**集合。  
  
## <a name="applies-to"></a>适用范围  
 [视图集合 (ADOX)](../../../ado/reference/adox-api/views-collection-adox.md)  
  
## <a name="see-also"></a>另请参阅  
 [视图追加方法示例 (VB)](../../../ado/reference/adox-api/views-append-method-example-vb.md)   
 [Append 方法 （ADOX 列）](../../../ado/reference/adox-api/append-method-adox-columns.md)   
 [Append 方法 （ADOX 组）](../../../ado/reference/adox-api/append-method-adox-groups.md)   
 [Append 方法 （ADOX 索引）](../../../ado/reference/adox-api/append-method-adox-indexes.md)   
 [Append 方法 （ADOX 键）](../../../ado/reference/adox-api/append-method-adox-keys.md)   
 [Append 方法 （ADOX 过程）](../../../ado/reference/adox-api/append-method-adox-procedures.md)   
 [Append 方法 （ADOX 表）](../../../ado/reference/adox-api/append-method-adox-tables.md)   
 [Append 方法（ADOX 用户）](../../../ado/reference/adox-api/append-method-adox-users.md)
