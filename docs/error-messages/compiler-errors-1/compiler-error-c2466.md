---
title: "コンパイラ エラー C2466 | Microsoft Docs"
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
  - "C2466"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2466"
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2466
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

サイズが 0 の配列を割り当てようとしました。  
  
 サイズが 0 の配列の割り当てまたは宣言が行われています。  配列サイズの定数式は、0 より大きい整数である必要があります。  添字が 0 の配列宣言が有効なのは、Microsoft 拡張機能が有効 \([\/Ze](../../build/reference/za-ze-disable-language-extensions.md) オプション指定時\) で、クラス、構造体、または共用体のメンバーに対して使用する場合だけです。  
  
 次の例では警告 C2466 が生成されます。  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```