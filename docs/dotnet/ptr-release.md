---
title: "ptr::Release |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.Release
- ptr::Release
- msclr.com.ptr.Release
- msclr::com::ptr::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method
ms.assetid: 7855781e-e4f6-4ad5-86a5-a81e2c3d90db
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3959ea6f1c48c22af15272a768cb73923911829a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ptrrelease"></a>ptr::Release
COM オブジェクトのすべての所有されている参照を解放します。  
  
## <a name="syntax"></a>構文  
  
```  
void Release();  
```  
  
## <a name="remarks"></a>コメント  
 この関数を呼び出す COM オブジェクトを所有しているすべての参照を解放し、内部ハンドルを COM オブジェクトを設定`nullptr`です。  COM オブジェクトの他の参照が存在しない場合は破棄されます。  
  
## <a name="example"></a>例  
 この例を使用して CLR クラスを実装して、`com::ptr`をそのプライベート メンバーをラップする`IXMLDOMDocument`オブジェクト。  `ReplaceDocument`メンバー関数を使用して`Release`オブジェクトを解放する、前のドキュメントによって新しいドキュメントをアタッチする前にします。  
  
```  
// comptr_release.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   // replace currently held COM object with another one  
   void ReplaceDocument(IXMLDOMDocument* pDoc) {  
      // release current document object  
      m_ptrDoc.Release();  
      // attach the new document object  
      m_ptrDoc.Attach(pDoc);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// unmanaged function that creates a raw XML DOM Document object  
IXMLDOMDocument* CreateDocument() {  
   IXMLDOMDocument* pDoc = NULL;  
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,  
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));  
   return pDoc;  
}  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // get another document object from unmanaged function and  
      // store it in place of the one held by our ref class  
      pDoc = CreateDocument();  
      doc.ReplaceDocument(pDoc);  
      // no further need for raw object reference  
      pDoc->Release();  
      pDoc = NULL;  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
   finally {  
      if (NULL != pDoc) {  
         pDoc->Release();  
      }  
   }  
}  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル** \<msclr\com\ptr.h >  
  
 **Namespace** msclr::com  
  
## <a name="see-also"></a>参照  
 [ptr メンバー](../dotnet/ptr-members.md)   
 [ptr::Detach](../dotnet/ptr-detach.md)