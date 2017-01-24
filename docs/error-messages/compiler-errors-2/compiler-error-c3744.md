---
title: "コンパイラ エラー C3744 | Microsoft Docs"
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
  - "C3744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3744"
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_unhook は最低 3 つのマネージ イベント引数を必要とします。  
  
 [\_\_unhook](../../cpp/unhook.md) 関数を C\+\+ マネージ拡張用にコンパイルするプログラムで使用する場合は、3 つのパラメーターが必要です。  
  
 `__hook` および `__unhook` は、\/clr プログラミングと互換性がありません。  代わりに、\+\= 演算子および \-\= 演算子を使用してください。  
  
 C3744 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では警告 C3744 が生成されます。  
  
```  
// C3744.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __delegate void delegate1();  
  
[ event_source(managed) ]  
public __gc class CPSource {  
public:  
   __event delegate1* event1;  
};  
  
[event_receiver(managed)]  
public __gc class CReceiver {  
public:  
   void Handler1() {  
   }  
  
   void UnhookAll1(CPSource* pSrc, CReceiver* pRec) {  
      pRec;  
      __unhook(pSrc);   // C3744  
      // The following line resolves the error.  
      // __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1);  
   }  
};  
  
int main() {  
}  
```