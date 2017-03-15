---
title: "コンパイラ エラー C3909 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3909"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3909"
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3909
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

WinRT またはマネージ イベント宣言は WinRT 型またはマネージ型内で行わなければなりません  
  
 Windows ランタイム イベントまたはマネージ イベントがネイティブ型内で宣言されました。  このエラーを修正するには、Windows ランタイム型またはマネージ型内でイベントを宣言します。  
  
 詳細については、「[event](../../windows/event-cpp-component-extensions.md)」を参照してください。  
  
 次の例では、C3909 を生成し、その修正方法を示しています。  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```