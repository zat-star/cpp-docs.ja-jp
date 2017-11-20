---
title: "コンパイラ エラー C3712 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3712
dev_langs: C++
helpviewer_keywords: C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 69f23d7192bc72f5f287a3a5b84b7840f9d25310
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3712"></a>コンパイラ エラー C3712
'method': イベント ハンドラー メソッドが 'method' には、ソースと同じ型の返す必要があります  
  
 ソース イベントのメソッドと同じ型が返されませんでしたするイベント ハンドラー メソッドを定義したとします。 このエラーを解決するには、イベント ハンドラーのメソッドに、ソース イベントのメソッドと同じ戻り値の型を指定します。  
  
 次の例では、C3712 が生成されます。  
  
```  
// C3712.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   int handler1() { return 0; }  
   // try the following line instead  
   // void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712  
   }  
};  
```