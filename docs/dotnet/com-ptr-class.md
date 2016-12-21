---
title: "com::ptr Class | Microsoft Docs"
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
  - "com::ptr"
  - "msclr::com::ptr"
  - "msclr.com.ptr"
  - "com.ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr クラス"
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# com::ptr Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパー。ラッパーは、デストラクターを呼び出すと、そのオブジェクトのすべての所有されている参照を解放する COM オブジェクトの有効期間管理を自動化します。  [CComPtr クラス](../atl/reference/ccomptr-class.md)と似ています。  
  
## 構文  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### パラメーター  
 `_interface_type`  
 COM 型はインターフェイスです。  
  
## 解説  
 さまざまな COM タスクを簡素化し、有効期間管理を自動化するには、`com::ptr` ようにローカル関数の変数を使用できます。  
  
 `com::ptr` は、関数のパラメーターとして直接使用できません; [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md) または [オブジェクト演算子 \(^\) へのハンドル](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) を代わりに使用します。  
  
 `com::ptr` は関数から直接返すできません; ハンドルを使用してください。  
  
## 使用例  
 この例では、プライベート メンバー `IXMLDOMDocument` オブジェクトをラップするために `com::ptr` を使用する CLR クラスを実装します。call クラスのパブリック メソッドが含まれている `IXMLDOMDocument` 呼び出しに使用します。サンプルでは、XML ドキュメント、塗りつぶしのインスタンスを簡単な XML で作成し、コンソールに XML を印刷するために解析されたドキュメント ツリーのノードのウォークを簡略化します。  
  
```  
// comptr.cpp  
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
  
   void LoadXml(String^ xml) {  
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);  
      BSTR bstr = NULL;  
  
      try {  
         // load some XML into the document  
         bstr = ::SysAllocString(pinnedXml);  
         if (NULL == bstr) {  
            throw gcnew OutOfMemoryException;  
         }  
         VARIANT_BOOL bIsSuccessful = false;  
         // use operator -> to call IXMODOMDocument member function  
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   // simplified function to write just the first xml node to the console  
   void WriteXml() {  
      IXMLDOMNode* pNode = NULL;  
  
      try {  
         // the first child of the document is the first real xml node  
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));  
         if (NULL != pNode) {  
            WriteNode(pNode);  
         }  
      }  
      finally {  
         if (NULL != pNode) {  
            pNode->Release();  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   // simplified function that only writes the node  
   void WriteNode(IXMLDOMNode* pNode) {  
      BSTR bstr = NULL;  
  
      try {  
         // write out the name and text properties  
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));  
         String^ strName = gcnew String(bstr);  
         Console::Write("<{0}>", strName);  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));  
         Console::Write(gcnew String(bstr));  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Console::WriteLine("</{0}>", strName);  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // stream some xml into the document  
      doc.LoadXml("<word>persnickety</word>");  
  
      // write the document to the console  
      doc.WriteXml();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **\<wordpersnickety\>\<または Word\>**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\com\\ptr.h\>  
  
 **名前空間** msclr::com  
  
## 参照  
 [C\+\+ のサポート ライブラリ](../dotnet/cpp-support-library.md)   
 [ptr Members](../dotnet/ptr-members.md)