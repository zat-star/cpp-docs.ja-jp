---
title: "コンパイラ エラー C3480 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3480"
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': ラムダ キャプチャ変数は、外側の関数スコープの変数である必要があります  
  
 ラムダ キャプチャ変数が外側の関数スコープの変数ではありません。  
  
### このエラーを解決するには  
  
-   ラムダ式のキャプチャ リストから変数を削除します。  
  
## 使用例  
 変数 `global` が外側の関数スコープではないため、次の例では C3480 が生成されます。  
  
```  
// C3480a.cpp int global = 0; int main() { [&global] { global = 5; }(); // C3480 }  
```  
  
## 使用例  
 次の例では、ラムダ式のキャプチャ リストから変数 `global` を削除することによって C3480 を解決しています。  
  
```  
// C3480b.cpp int global = 0; int main() { [] { global = 5; }(); }  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)