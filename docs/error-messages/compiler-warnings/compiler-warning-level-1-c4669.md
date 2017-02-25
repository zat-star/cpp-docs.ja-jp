---
title: "Compiler Warning (level 1) C4669 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4669"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4669"
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compiler Warning (level 1) C4669
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'cast' : 変換が安全ではありません: 'class' はマネージ型または WinRT 型のオブジェクトです  
  
 キャストに Windows ランタイム型またはマネージ型が含まれています。  コンパイラは、ポインター間でビット単位のコピーを実行してキャストを完了しますが、他のチェックは行われません。  この警告を解決するには、マネージ メンバーまたは Windows ランタイム型を含むクラスをキャストしないでください。  
  
 次の例では、C4669 を生成し、その修正方法を示しています。  
  
```  
// C4669.cpp  
// compile with: /clr /W1  
ref struct A {  
   int i;  
   Object ^ pObj;   // remove the managed member to fix the warning  
};  
  
ref struct B {  
   int j;  
};  
  
int main() {  
   A ^ a = gcnew A;  
   B ^ b = reinterpret_cast<B ^>(a);   // C4669  
}  
```