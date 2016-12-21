---
title: "コンパイラ エラー C3861 | Microsoft Docs"
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
  - "C3861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3861"
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 識別子が見つかりませんでした  
  
 コンパイラでは、引数依存の検索を使用しても、識別子への参照を解決できませんでした。  
  
 このエラーを修正するには、識別子の宣言で大文字小文字とスペルを確認します。  [スコープ解決演算子](../../cpp/scope-resolution-operator.md)と、名前空間の [using ディレクティブ](../../misc/using-directive-cpp.md)が正しく使用されていることを確認します。  識別子がヘッダー ファイルで宣言されている場合は、識別子の参照前にこのヘッダー ファイルがインクルードされていることを確認します。  また、この識別子が[条件付きコンパイル ディレクティブ](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)によって除外されていないことも確認します。  
  
## 使用例  
 次の例では C3861 が生成されます。  
  
```  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## 使用例  
 現在、C\+\+ 標準ライブラリの例外クラスは `std` 名前空間にあります。  
  
```  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```