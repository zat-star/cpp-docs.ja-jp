---
title: "コンパイラ エラー C3532 | Microsoft Docs"
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
  - "C3532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3532"
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 'auto' の使用方法に誤りがあります  
  
 指定された型は、`auto` キーワードを使用して宣言できません。  たとえば、`auto` キーワードを使用して配列またはメソッドの戻り値の型を宣言することはできません。  
  
### このエラーを解決するには  
  
1.  初期化子式で有効な型が生成されることを確認します。  
  
2.  配列またはメソッドの戻り値の型を宣言していないことを確認します。  
  
## 使用例  
 次の例では、`auto` キーワードでメソッドの戻り値の型を宣言できないため、C3532 が発生します。  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## 使用例  
 次の例では、`auto` キーワードで配列を宣言できないため、C3532 が発生します。  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## 参照  
 [auto キーワード](../../cpp/auto-keyword.md)