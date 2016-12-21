---
title: "コンパイラ エラー C2715 | Microsoft Docs"
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
  - "C2715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2715"
ms.assetid: c81567a7-5b65-468f-aaf9-835f91e468e4
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : この型をスローまたはキャッチできません  
  
 値型は、マネージ コードで例外処理を使用する場合には無効な引数です。詳細については、「[Exception Handling](../../windows/exception-handling-cpp-component-extensions.md)」を参照してください。  
  
```  
// C2715a.cpp  
// compile with: /clr  
using namespace System;  
  
value struct V {  
   int i;  
};  
  
void f1() {  
   V v;  
   v.i = 10;  
   throw v;   // C2715  
   // try the following line instead  
   // throw ((V^)v);  
}  
  
int main() {  
   try {  
      f1();  
   }  
  
   catch(V v) { if ( v.i == 10 ) {   // C2715  
   // try the following line instead  
   // catch(V^ pv) { if ( pv->i == 10 ) {  
         Console::WriteLine("caught 10 - looks OK");  
      }   
      else {  
         Console::WriteLine("catch looks bad");  
      }  
   }  
   catch(...) {  
      Console::WriteLine("catch looks REALLY bad");  
   }  
}  
```  
  
 [\_\_value](../../misc/value.md) 型または [\_\_gc](../Topic/__gc.md) ポインターは、C\+\+ マネージ拡張で例外処理を使用する場合には無効な引数です。  このエラーを解決するには、[\_\_box](../../misc/box.md) キーワードを使用して引数をボックスで囲みます。  
  
 次の例では警告 C2715 が生成されます。  
  
```  
// C2715b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
  
__value struct V {  
   int i;  
};  
  
void f1() {  
   V v;  
   v.i = 10;  
   throw v;   // C2715  
   // try the following line instead  
   // throw __box(v);  
}  
  
int main() {  
   try {  
      f1();  
   }  
  
   catch(V v) { if ( v.i == 10 ) {   // C2715  
   // try the following line instead  
   // catch(__box V *pv) { if ( pv->i == 10 ) {  
         Console::WriteLine(S"caught 10 - looks OK");  
      }   
      else {  
         Console::WriteLine(S"catch looks bad");  
      }  
   }  
   catch(...) {  
      Console::WriteLine(S"catch looks REALLY bad");  
   }  
}  
```