---
title: "添加和修改线条 （报表生成器和 SSRS） |Microsoft 文档"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8dc4998b-a214-49b6-96e7-fbc179015209
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: ca5f80521b142435210737f2e6c971c8d6853510
ms.contentlocale: zh-cn
ms.lasthandoff: 08/09/2017

---
# <a name="add-and-modify-a-line-report-builder-and-ssrs"></a>添加和修改线条（报表生成器和 SSRS）
  如果希望图形元素分割报表的各部分，则可以在 [!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)] 分页报表中添加线条。 可以通过编辑线条属性（如颜色或样式）自定义线条的外观。 例如，您可能希望将公司颜色合并到报表中。    
    
> [!NOTE]    
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]    
    
## <a name="to-add-a-line"></a>添加线条    
    
1.  在 **“插入”** 选项卡上，单击 **“线条”**。    
    
2.  在设计图面上，单击希望线条一端所在的位置，然后单击希望线条另一端所在的位置。    
    
     请注意，当移动线条末端时，“对齐线”将以结束行的形式与其他对象一起显示在设计图面上。 如果您要使对象对齐，这些对齐线将对您很有帮助。    
    
3.  若要更改线条属性，请在设计图面上选择线条，然后在 **“主文件夹”** 选项卡的 **“边框”** 部分编辑该线条的属性。    
    
    > [!NOTE]    
    >  如果的线条样式设置为**Double**和线条宽度是 1 1/2 pt 或较窄，行可能不会出现双精度报表生成器中，报表设计器中运行报表时或[!INCLUDE[ssRSnoversion_md](../../includes/ssrsnoversion-md.md)]web 门户。 将报表导出为其他格式（例如 Microsoft Word 和 Acrobat PDF）后，线条会显示为双线。    
    
## <a name="see-also"></a>另请参阅    
 [矩形和线条（报表生成器和 SSRS）](../../reporting-services/report-design/rectangles-and-lines-report-builder-and-ssrs.md)    
    
  