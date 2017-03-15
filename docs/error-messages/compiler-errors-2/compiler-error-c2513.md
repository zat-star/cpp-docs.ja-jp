---
title: "コンパイラ エラー C2513 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2513"
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 指定された型は、識別子の名前を指定せずに宣言されています。  
  
 型指定子が、変数識別子のない宣言で使用されています。  
  
 次の例では警告 C2513 が生成されます。  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 このエラーは、typedef の初期化が許可されなくなった Visual Studio .NET 2003 で行った、コンパイラ準拠作業の結果として生成されることもあります。  typedef の初期化は、標準では許可されていないため、現在はコンパイラ エラーになります。  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 `typedef` を削除して変数を初期化子の集約リストで定義する方法もありますが、これは型と同じ名前の変数を作成して型名を隠すためお勧めできません。