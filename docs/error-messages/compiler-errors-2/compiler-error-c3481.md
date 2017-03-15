---
title: "コンパイラ エラー C3481 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3481"
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': ラムダ キャプチャ変数が見つかりません  
  
 コンパイラはラムダ式のキャプチャ リストに渡された変数の定義を見つけられませんでした。  
  
### このエラーを解決するには  
  
-   ラムダ式のキャプチャ リストから変数を削除します。  
  
## 使用例  
 次の例では、変数 `n` が定義されていないため、C3481 が生成されます。  
  
```  
// C3481.cpp int main() { [n] {}(); // C3481 }  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)