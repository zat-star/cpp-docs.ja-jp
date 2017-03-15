---
title: "コンパイラ エラー C3491 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3491"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3491"
ms.assetid: 7f0e71b2-46a0-4d25-bd09-6158a280f509
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C3491
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': 変更できないラムダでは値キャプチャは変更できません  
  
 変更できないラムダ式では、値によってキャプチャされる変数の値を変更できません。  
  
### このエラーを解決するには  
  
-   `mutable` キーワードでラムダ式を宣言します。または、  
  
-   ラムダ式のキャプチャ リストへの参照によって変数を渡します。  
  
## 使用例  
 次の例では、変更できないラムダ式の本体がキャプチャ変数 `m` を変更するため、C3491 が生成されます。  
  
```  
// C3491a.cpp int main() { int m = 55; [m](int n) { m = n; }(99); // C3491 }  
```  
  
## 使用例  
 次の例では、ラムダ式を `mutable` キーワードで宣言することで C3491 を解決しています。  
  
```  
// C3491b.cpp int main() { int m = 55; [m](int n) mutable { m = n; }(99); }  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)