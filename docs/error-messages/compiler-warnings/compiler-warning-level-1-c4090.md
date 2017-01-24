---
title: "コンパイラの警告 (レベル 1) C4090 | Microsoft Docs"
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
  - "C4090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4090"
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation' : 異なる 'modifier' 修飾子です。  
  
 演算に使用される変数の定義では、コンパイラが検出しなければ修飾されないようにする修飾子が指定されています。  この式は、変更されずにコンパイルされます。  
  
 この警告は、**const** アイテムまたは `volatile` アイテムへのポインターが、**const** または `volatile` を指すように宣言されていないポインターに代入されていることが原因で発生する場合があります。  
  
 この警告は C プログラムに対して生成されます。  C\+\+ プログラムの場合は、[C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md) エラーが生成されます。  
  
 次の例では警告 C4090 が生成されます。  
  
```  
// C4090.c  
// compile with: /W1  
int *volatile *p;  
int *const *q;  
int **r;  
  
int main() {  
   p = q;   // C4090  
   p = r;  
   q = p;   // C4090  
   q = r;  
   r = p;   // C4090  
   r = q;   // C4090  
}  
```