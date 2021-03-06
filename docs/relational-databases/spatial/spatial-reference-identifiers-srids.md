---
title: "空间引用标识符 (SRID) | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine, sql-database
ms.service: 
ms.component: spatial
ms.reviewer: 
ms.suite: sql
ms.technology:
- dbe-spatial
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Spatial Reference Identifiers (SRIDs)
- geodetic spatial data [SQL Server], identifiers
- SRID
ms.assetid: 0612658a-7d1b-4178-bdc2-42b914ea31a7
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: cf9bcd6bb6597530ab85057c12240217959db5e6
ms.sourcegitcommit: 37f0b59e648251be673389fa486b0a984ce22c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2018
---
# <a name="spatial-reference-identifiers-srids"></a>空间引用标识符 (SRID)
[!INCLUDE[appliesto-ss-asdb-xxxx-xxx-md](../../includes/appliesto-ss-asdb-xxxx-xxx-md.md)]
每个空间实例都有一个空间引用标识符 (SRID)。 SRID 对应于基于特定椭圆体的空间引用系统，可用于平面球体映射或圆球映射。  
  
> [!IMPORTANT]  
>  有关 [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]中引入的空间功能的详细说明和示例（包括新 SRID），请下载白皮书 [New Spatial Features in SQL Server 2012](http://go.microsoft.com/fwlink/?LinkId=226407)（SQL Server 2012 中的新空间功能）。  
  
 空间列可包含具有不同 SRID 的对象。 然而，在使用 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 空间数据方法对数据执行操作时，仅可使用具有相同 SRID 的空间实例。 从两个空间数据实例派生的任何空间方法的结果仅在这两个实例具有相同的 SRID（该 SRID 基于相同的用于确定实例坐标的度量单位、数据和投影）时才有效。 SRID 最常见的度量单位为米或平方米。  
  
 如果两个空间实例的 SRID 不相同，则对这两个实例使用 **geometry** 或 **geography** 数据类型方法后的结果将返回 NULL。 例如，若要以下谓词返回非 NULL 结果，两个 **geometry** 实例（ `geometry1` 和 `geometry2`）必须具有相同的 SRID：  
  
 `geometry1.STIntersects(geometry2) = 1`  
  
> [!NOTE]  
>  空间引用标识系统是由 [欧洲石油测绘组 (European Petroleum Survey Group, EPSG)](http://go.microsoft.com/fwlink/?LinkId=99349) 的标准定义的，它是为绘图、测绘以及大地测量数据存储而开发的一组标准。 该标准归石油天然气生产商 (OGP) 测绘和定位委员会所有。  
  
## <a name="see-also"></a>另请参阅  
 [空间数据类型概述](../../relational-databases/spatial/spatial-data-types-overview.md)  
  
  
