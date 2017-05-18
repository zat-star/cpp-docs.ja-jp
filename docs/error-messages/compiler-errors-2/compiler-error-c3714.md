---
title: "コンパイラ エラー C3714 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3714
dev_langs:
- C++
helpviewer_keywords:
- C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 44caee95ba84535f5b34f1bae1e69d02deccdf48
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3714"></a>コンパイラ エラー C3714
'method': イベント ハンドラー メソッドが必要、同じ呼び出し規約、ソースとして 'メソッド'  
  
 ソース イベントのメソッドと同じ呼び出し規約を使用していないイベント ハンドラー メソッドが定義されます。 このエラーを修正するのには、ソースのイベント メソッドと同じ呼び出し規約 イベント ハンドラー メソッドを指定します。 たとえば、次のコードでの呼び出し規約は、`handler1`と`event1`一致 ([_ _cdecl](../../cpp/cdecl.md)または[_ _stdcall](../../cpp/stdcall.md)や他のユーザー)。 削除する規約キーワードを両方の宣言から呼び出すことによっても、問題を解決され、発生する`event1`と`handler1`に既定値に、 [thiscall](../../cpp/thiscall.md)呼び出し規約です。 参照してください[呼び出し規約](../../cpp/calling-conventions.md)の詳細。  
  
 次の例では、c3714 エラーが生成されます。  
  
```  
// C3714.cpp  
// compile with: /c  
// processor: x86  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void __cdecl event1();  
   // try the following line instead  
   // __event void __stdcall event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void __stdcall handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714  
   }  
};  
```
