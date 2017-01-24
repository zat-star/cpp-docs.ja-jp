---
title: "コンパイラ エラー C3493 | Microsoft Docs"
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
  - "C3493"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3493"
ms.assetid: 734b4257-12a3-436f-8488-c8c55ec81634
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3493
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定のキャプチャ モードが指定されていないため、'var' を暗黙的にキャプチャできません  
  
 空のラムダ式のキャプチャである `[]` は、ラムダ式が明示的にも暗黙的にも変数をキャプチャしないことを指定します。  
  
### このエラーを解決するには  
  
-   既定のキャプチャ モードを指定するか、または  
  
-   1 つ以上の変数を明示的にキャプチャします。  
  
## 使用例  
 次の例では、外部変数を変更しているが、空のキャプチャ句を指定していないため、C3493 が生成されます。  
  
```  
// C3493a.cpp int main() { int m = 55; [](int n) { m = n; }(99); // C3493 }  
```  
  
## 使用例  
 次の例では、既定のキャプチャ モードとして参照渡しを指定することによって C3493 を解決しています。  
  
```  
// C3493b.cpp int main() { int m = 55; [&](int n) { m = n; }(99); }  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)