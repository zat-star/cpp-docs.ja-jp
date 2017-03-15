---
title: "コンパイラ エラー C3060 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3060"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3060"
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3060
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member' : フレンド関数は、限定名を使用するクラス内では定義できません \(宣言することのみ可能です\)  
  
 修飾名を使用してフレンド関数が定義されました。これは許可されていません。  
  
 次の例では C3060 が生成されます。  
  
```  
// C3060.cpp class A { public: void func(); }; class C { public: friend void A::func() { }   // C3060 // Try the following line and the out of class definition: // friend void A::func(); }; // void A::func(){}  
```