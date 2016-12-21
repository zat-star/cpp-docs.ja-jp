---
title: "ptr::Release | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr.Release"
  - "ptr::Release"
  - "msclr.com.ptr.Release"
  - "msclr::com::ptr::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Release メソッド"
ms.assetid: 7855781e-e4f6-4ad5-86a5-a81e2c3d90db
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::Release
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM オブジェクトのすべての所有されている参照を解放します。  
  
## 構文  
  
```  
void Release();  
```  
  
## 解説  
 この関数を呼び出すと、COM オブジェクトのすべての所有されている参照を解放し、`nullptr`に COM オブジェクト内のハンドルを設定します。COM オブジェクトのそのほかの参照がないと、破棄されます。  
  
## 使用例  
 この例では、プライベート メンバー `IXMLDOMDocument` オブジェクトをラップするために `com::ptr` を使用する CLR クラスを実装します。`ReplaceDocument` のメンバー関数では新しいドキュメントを接続するには、前のドキュメント オブジェクトを解放するに `Release` を使用します。  
  
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
  
## 必要条件  
 **ヘッダー ファイル** \<msclr\\com\\ptr.h\>  
  
 **名前空間** msclr::com  
  
## 参照  
 [ptr Members](../dotnet/ptr-members.md)   
 [ptr::Detach](../Topic/ptr::Detach.md)