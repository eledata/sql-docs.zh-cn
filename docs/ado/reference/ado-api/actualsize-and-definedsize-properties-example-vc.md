---
title: "ActualSize 和 DefinedSize 属性示例 （VC + +） |Microsoft 文档"
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
dev_langs:
- C++
helpviewer_keywords:
- ActualSize property [ADO], VC++ example
- DefinedSize property [ADO], VC++ example
ms.assetid: 05f7cc97-b806-41d2-939d-a955d10844c4
caps.latest.revision: 
author: MightyPen
ms.author: genemi
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 82c81e702bf1e3da1a0ab22416c8430c94f3534e
ms.sourcegitcommit: acab4bcab1385d645fafe2925130f102e114f122
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2018
---
# <a name="actualsize-and-definedsize-properties-example-vc"></a>ActualSize 和 DefinedSize 属性示例 （VC + +）
此示例使用[ActualSize](../../../ado/reference/ado-api/actualsize-property-ado.md)和[DefinedSize](../../../ado/reference/ado-api/definedsize-property.md)要显示的定义的大小和实际大小的字段的属性。  
  
## <a name="example"></a>示例  
  
```  
// BeginActualSizeCpp.cpp  
// compile with: /EHsc  
#import "msado15.dll" no_namespace rename("EOF", "EndOfFile")  
  
#include <ole2.h>  
#include <stdio.h>  
#include "conio.h"   
  
// Function declarations  
inline void TESTHR(HRESULT x) { if FAILED(x) _com_issue_error(x); };  
void ActualSizeX();  
void PrintProviderError(_ConnectionPtr pConnection);  
  
int main() {  
   if (FAILED(::CoInitialize(NULL)))  
      return -1;  
   ActualSizeX();  
   ::CoUninitialize();  
}  
  
void ActualSizeX() {  
   HRESULT hr = S_OK;  
  
   // Define ADO object pointers. Initialize pointers on define.  
   // These are in the ADODB::  namespace.  
   _RecordsetPtr pRstStores = NULL;  
  
   // Define Other variables  
   _bstr_t strMessage;  
   _bstr_t strCnn("Provider='sqloledb'; Data Source='My_Data_Source'; Initial Catalog='pubs'; Integrated Security='SSPI';");  
  
   try {  
      // Open a recordset for the stores table.  
      TESTHR(pRstStores.CreateInstance(__uuidof(Recordset)));  
  
      // You have to explicitly pass the Cursor type and LockType to the Recordset here.  
      hr = pRstStores->Open("stores", strCnn, adOpenForwardOnly, adLockReadOnly, adCmdTable);  
  
      // Loop through the recordset displaying the contents of the stor_name field,   
      // the field's defined size, and its actual size.  
      pRstStores->MoveFirst();  
  
      while (!(pRstStores->EndOfFile)) {  
         strMessage = "Store Name: ";  
         strMessage += (_bstr_t)pRstStores->Fields->Item["stor_name"]->Value + "\n";  
         strMessage += "Defined Size: ";   
         strMessage += (_bstr_t)pRstStores->Fields->Item["stor_name"]->DefinedSize + "\n";  
         strMessage += "Actual Size: ";  
         strMessage += (_bstr_t) pRstStores->Fields->Item["stor_name"]->ActualSize + "\n";   
  
         printf("%s\n",(LPCSTR)strMessage);  
         pRstStores->MoveNext();  
      }  
   }  
   catch(_com_error &e) {  
      _variant_t vtConnect = pRstStores->GetActiveConnection();  
  
      // GetActiveConnection returns connect string if connection  
      // is not open, else returns Connection object.  
      switch(vtConnect.vt) {  
         case VT_BSTR:  
            printf("Error:\n");  
            printf("Code = %08lx\n", e.Error());  
            printf("Message = %s\n", e.ErrorMessage());  
            printf("Source = %s\n", (LPCSTR) e.Source());  
            printf("Description = %s\n", (LPCSTR) e.Description());  
            break;  
         case VT_DISPATCH:  
            PrintProviderError(vtConnect);  
            break;  
         default:  
            printf("Errors occured.");  
            break;  
      }  
   }  
  
   // Clean up objects before exit.  
   if (pRstStores)  
      if (pRstStores->State == adStateOpen)  
         pRstStores->Close();  
}  
  
void PrintProviderError(_ConnectionPtr pConnection) {  
   // Print Provider Errors from Connection object.  
   // pErr is a record object in the Connection's Error collection.  
   ErrorPtr pErr = NULL;  
   long nCount = 0;      
   long i = 0;  
  
   if ( (pConnection->Errors->Count) > 0) {  
      nCount = pConnection->Errors->Count;  
      // Collection ranges from 0 to nCount -1.  
      for (i = 0 ; i < nCount ; i++) {  
         pErr = pConnection->Errors->GetItem(i);  
         printf("\t Error number: %x\t%s", pErr->Number,(LPCSTR ) pErr->Description);  
      }  
   }  
}  
```  
  
 **存储名称： Eric 读取丛书**  
**定义大小： 40**  
**实际大小： 19**  
**存储名称： Barnum**  
**定义大小： 40**  
**实际大小： 8**  
**存储名称： 新闻和 Brews**  
**定义大小： 40**  
**实际大小： 12**  
**存储名称： 文档-U-Mat： 质量细目和书籍**  
**定义大小： 40**  
**实际大小： 36**  
**存储名称： 音符书店**  
**定义大小： 40**  
**实际大小： 18**  
**存储名称： Bookbeat**  
**定义大小： 40**  
**实际大小： 8**   
## <a name="see-also"></a>另请参阅  
 [ActualSize 属性 (ADO)](../../../ado/reference/ado-api/actualsize-property-ado.md)   
 [DefinedSize 属性](../../../ado/reference/ado-api/definedsize-property.md)
