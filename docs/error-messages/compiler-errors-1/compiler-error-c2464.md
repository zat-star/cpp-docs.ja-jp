---
title: "コンパイラ エラー C2464 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2464"
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2464
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 参照識別名を割り当てるのに 'new' 演算子が使われています。  
  
 参照識別子は、`new` 演算子で割り当てられています。  参照はメモリ オブジェクトではないため、`new` は参照へのポインターを返すことができません。  標準的な変数宣言の構文を使って参照を宣言してください。  
  
 次の例では警告 C2464 が生成されます。  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```