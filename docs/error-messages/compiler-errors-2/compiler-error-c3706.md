---
title: "コンパイラ エラー C3706 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3706
dev_langs:
- C++
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 20f7e14d22e1994213624d88ccab098844aa6ac4
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3706"></a>コンパイラ エラー C3706
'function': COM イベントを起動する COM インターフェイスでなければなりません  
  
 COM イベントを発生させるを使用するイベント インターフェイスには、COM インターフェイスを使用する必要があります。 このような状況で、インターフェイス、Visual C 属性を使用して定義する必要がありますか、またはを使用してインポート[#import](../../preprocessor/hash-import-directive-cpp.md) #import の embedded_idl 属性を持つタイプ ライブラリからです。  
  
 なお、`#include`以下のサンプルに示すように、ATL ヘッダー ファイルの行が COM イベントを使用するために必要です。 このエラーを修正するように`IEvents`(イベントのインターフェイス)、次のいずれかの操作を適用することにより、COM インターフェイスのインターフェイス定義に属性:[オブジェクト](../../windows/object-cpp.md)、[デュアル](../../windows/dual.md)、または[dispinterface](../../windows/dispinterface.md)です。  
  
 MIDL によって生成されたヘッダー ファイルからのインターフェイスの場合は、コンパイラが認識しないこと、COM インターフェイスとして。  
  
 次の例では、C3706 が生成されます。  
  
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
