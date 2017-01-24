---
title: "ptr::ptr | Microsoft Docs"
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
  - "ptr::ptr"
  - "ptr.ptr"
  - "msclr.com.ptr.ptr"
  - "msclr::com::ptr::ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::ptr"
ms.assetid: 4f5883b4-7c0a-46c6-aa9f-4e49eed463eb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`com::ptr` を COM オブジェクトをラップするために構築します。  
  
## 構文  
  
```  
ptr();  
ptr(  
   _interface_type * p  
);  
```  
  
#### パラメーター  
 `P`  
 COM インターフェイス ポインター。  
  
## 解説  
 非引数のコンストラクターは、基になるオブジェクトのハンドルに `nullptr` を割り当てます。  `com::ptr` への後続の呼び出しで、オブジェクトが実際に添付または作成されるまで内部オブジェクトを使用すると、自動的に失敗します。  
  
 1 引数のコンストラクターでは、COM オブジェクトへの参照を追加しますが、呼び出し元の参照を解放しないため、呼び出し元は実際にはコントロールを中止できるように COM オブジェクト `Release` を呼び出す必要があります。  `com::ptr` のデストラクターが呼び出されるときに自動的に COM オブジェクトの参照を解放します。  
  
 このコンストラクターに `NULL` を渡すことで、引数バージョンを呼び出すことと同じです。  
  
## 使用例  
 この例では、プライベート メンバー `IXMLDOMDocument` オブジェクトをラップするために `com::ptr` を使用する CLR クラスを実装します。  これは、コンストラクターの両方のバージョンの使用方法を示します。  
  
```  
// comptr_ptr.cpp  
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
  
   // construct the internal com::ptr with a COM object  
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
  
   try {  
      // create an XML DOM document object  
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,   
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));  
      // construct the ref class with the COM object  
      XmlDocument doc1(pDoc);  
  
      // or create the class from a progid string  
      XmlDocument doc2("Msxml2.DOMDocument.3.0");  
   }  
   // doc1 and doc2 destructors are called when they go out of scope  
   // and the internal com::ptr releases its reference to the COM object  
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
 [ptr::CreateInstance](../dotnet/ptr-createinstance.md)   
 [ptr::~ptr](../dotnet/ptr-tilde-ptr.md)