---
title: "コンパイラ エラー C3482 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3482"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3482"
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3482
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this' は非静的メンバー関数内でのラムダ キャプチャとしてのみ使用できます  
  
 静的メソッドまたはグローバル関数で宣言されているラムダ式のキャプチャ リストに `this` を渡すことはできません。  
  
### このエラーを解決するには  
  
-   外側の関数を静的でないメソッドに変換します。または、  
  
-   ラムダ式のキャプチャ リストから `this` ポインターを削除します。  
  
## 使用例  
 次の例では、C3482 が生成されます。  
  
```  
// C3482.cpp // compile with: /c class C { public: static void staticMethod() { [this] {}(); // C3482 } };  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)