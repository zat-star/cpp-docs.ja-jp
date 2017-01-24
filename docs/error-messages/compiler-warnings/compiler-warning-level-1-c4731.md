---
title: "コンパイラの警告 (レベル 1) C4731 | Microsoft Docs"
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
  - "C4731"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4731"
ms.assetid: 5658c24c-3e6f-4505-835b-1fb92d47cab0
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4731
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointer' : インライン アセンブラー コードにより変更されたフレーム ポインター レジスタ 'register' です。  
  
 フレーム ポインター レジスタが変更されています。  レジスタをインライン アセンブリ ブロックまたはフレーム変数 \(ローカルまたはパラメーター、変更されたレジスタによって異なります\) に保存して、復元する必要があります。この処理を行わないと、コードは正常に動作しません。  
  
 次の例では警告 C4731 が生成されます。  
  
```  
// C4731.cpp  
// compile with: /W1 /LD  
// processor: x86  
// C4731 expected  
void bad(int p) {  
   __asm  
   {  
      mov ebp, 1  
   }  
  
   if (p == 1)  
   {  
      // ...  
   }  
}  
```  
  
 EBP はフレーム ポインター \(FPO が無効\) であり、変更対象です。  `p` が後で参照される場合は、`EBP` に対して相対的に参照されます。  ただし、`EBP` はコードで上書きされているため、プログラムは正常に動作せず、違反になる場合もあります。