---
title: "コンパイラ エラー C2975 | Microsoft Docs"
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
  - "C2975"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2975"
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2975
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : '型' の無効なテンプレート引数です。コンパイル時の定数式が必要です  
  
 テンプレートの引数がテンプレート宣言と一致していません。山かっこの中に定数式を指定する必要があります。  変数をテンプレートの実引数にすることはできません。  テンプレートの宣言を調べて、正しい型を確認してください。  
  
 次の例では警告 C2975 が生成されます。  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 C2975 は、[\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) を指定したコンパイル時定数として \_\_LINE\_\_ を使用する場合にも発生します。  1 つの解決法として、**\/ZI** ではなく [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) でコンパイルするという方法もあります。  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```