---
title: "コンパイラの警告 (レベル 1) C4401 | Microsoft Docs"
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
  - "C4401"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4401"
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4401
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bitfield' : メンバーがビット フィールドです。  
  
 インライン アセンブラーのコードがビット フィールド メンバーへのアクセスを試みています。  インライン アセンブラーはビット フィールド メンバーにアクセスできないため、ビット フィールド メンバーより前にある、一番近いパッキング境界が使用されます。  
  
 この警告を回避するには、インライン アセンブラー コードでビット フィールドを参照する前に、ビット フィールドを適切な型にキャストします。  次の例では警告 C4401 が生成されます。  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```