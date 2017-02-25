---
title: "コンパイラ エラー C3704 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3704"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3704"
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3704
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : vararg メソッドはイベントを発生させることができません。  
  
 vararg メソッドに [\_\_event](../../cpp/event.md) を使用しようとしました。  このエラーを解決するには、`fireEvent(int i, ...)` の呼び出しを次のサンプル コードのように `fireEvent(int i)` の呼び出しに置き換えます。  
  
 次の例では警告 C3704 が生成されます。  
  
```  
// C3704.cpp  
[ event_source(native) ]  
class CEventSrc {  
   public:  
      __event void fireEvent(int i, ...);   // C3704  
      // try the following line instead:  
      // __event void fireEvent(int i);  
};  
  
int main() {  
}  
```