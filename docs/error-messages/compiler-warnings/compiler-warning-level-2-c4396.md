---
title: "コンパイラの警告 (レベル 2) C4396 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4396"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4396"
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラの警告 (レベル 2) C4396
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"name": フレンド宣言が関数の特殊化を参照している場合、テンプレートのインライン指定子を使用できません  
  
 関数テンプレートの特殊化では、いずれの [インライン](../../misc/inline-inline-forceinline.md) 指定子も指定できません。 コンパイラは、警告 C4396 を発行し、インライン指定子を無視します。  
  
### このエラーを解決するには  
  
-   フレンド関数の宣言から `inline`、`__inline`、`__forceinline` の指定子を削除します。  
  
## 使用例  
 次のコード例では、`inline` 指定子のある無効なフレンド関数の宣言を示します。  
  
```  
// C4396.cpp // compile with: /W2 /c class X; template<class T> void Func(T t, int i); class X { friend inline void Func<char>(char t, int i);  //C4396 // try the following line instead //    friend void Func<char>(char t, int i); int i; };  
```