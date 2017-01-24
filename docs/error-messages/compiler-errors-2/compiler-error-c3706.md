---
title: "コンパイラ エラー C3706 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3706"
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : COM イベントを発生させるには、COM インターフェイスを使用しなければなりません。  
  
 COM イベントを発生させるために使用するイベント インターフェイスは、COM インターフェイスであることが必要です。  この場合、インターフェイスは、Visual C\+\+ 属性を使用して定義されているか、embedded\_idl 属性を指定した [\#import](../Topic/%23import%20Directive%20\(C++\).md) を使用してタイプ ライブラリからインポートされている必要があります。  
  
 COM イベントを使用するには、次の例に示す ATL ヘッダー ファイルの `#include` 行が必要です。  このエラーを解決するには、インターフェイスの定義に属性 [object](../Topic/object%20\(C++\).md)、[dual](../Topic/dual.md)、または [dispinterface](../../windows/dispinterface.md) を適用して、`IEvents` \(イベント インターフェイス\) を COM インターフェイスにします。  
  
 インターフェイスが MIDL で生成されたヘッダー ファイルからのものである場合、コンパイラはそれを COM インターフェイスと認識しません。  
  
 次の例では警告 C3706 が生成されます。  
  
```  
// C3706.cpp  
// compile with: /c  
// C3706 expected  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlctl.h>  
  
[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];  
  
// Uncomment the following line to resolve.  
// [object, uuid="12341234-1234-1234-1234-123412341237"]  
__interface IEvents : IUnknown {  
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]  
};  
  
[dual, uuid="12341234-1234-1234-1234-123412341235"]  
__interface IBase {  
   HRESULT fireEvents();  
};  
  
[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]  
class CEventSrc : public IBase {  
   public:  
   __event __interface IEvents;  
  
   HRESULT fireEvents() {  
      HRESULT hr = IEvents_event1(123);  
      return hr;  
   }  
};  
```