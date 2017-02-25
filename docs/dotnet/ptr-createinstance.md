---
title: "ptr::CreateInstance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr.CreateInstance"
  - "msclr::com::ptr::CreateInstance"
  - "msclr.com.ptr.CreateInstance"
  - "ptr::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::CreateInstance"
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# ptr::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`com::ptr` 内で COM オブジェクトのインスタンスを作成します。  
  
## 構文  
  
```  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   System::String ^ progid  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   const wchar_t * progid  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   REFCLSID rclsid  
);  
```  
  
#### パラメーター  
 `progid`  
 `ProgID` 文字列。  
  
 `pouter`  
 集約オブジェクトの IUnknown インターフェイス \(制御元の IUnknown\) へのポインター。  `pouter` を指定しない場合は、`NULL` が使用されます。  
  
 `cls_context`  
 新規作成されたオブジェクトを管理するコードが実行されるコンテキスト。  `CLSCTX` 列挙型の値の、いずれかが値として使用されます。  `cls_context` を指定しない場合は、値 CLSCTX\_ALL が使用されます。  
  
 `rclsid`  
 オブジェクトの作成に使用されるデータとコードに関連付けられている `CLSID`。  
  
## 例外  
 `com::ptr` が COM オブジェクトへの参照を既に所有する場合、`CreateInstance` は <xref:System.InvalidOperationException> をスローします。  
  
 この関数は、`CoCreateInstance` を呼び出し、エラー `HRESULT` を適切な例外に変換するために <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> を使用します。  
  
## 解説  
 `CreateInstance` は、`CoCreateInstance` を使用することにより、ProgID または CLSID のいずれかから識別された指定のオブジェクトの新しいインスタンスを作成します。  `com::ptr` は、新しく作成されたオブジェクトを参照し、消滅時に所有されている参照をすべて自動的に解放します。  
  
## 使用例  
 この例では、プライベート メンバー `IXMLDOMDocument` オブジェクトをラップするために `com::ptr` を使用する CLR クラスを実装します。  クラス コンストラクターは、ProgID から、または CLSCTX と CLSID からドキュメント オブジェクトを作成するために、`CreateInstance` の 2 つの異なる形式を使用します。  
  
```  
// comptr_createinstance.cpp  
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
   XmlDocument(REFCLSID clsid, DWORD clsctx) {  
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc1("Msxml2.DOMDocument.3.0");  
  
      // or from a clsid with specific CLSCTX  
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
## 必要条件  
 **ヘッダー ファイル** \<msclr\\com\\ptr.h\>  
  
 **名前空間** msclr::com  
  
## 参照  
 [ptr Members](../dotnet/ptr-members.md)