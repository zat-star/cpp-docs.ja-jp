---
title: "MxCsr | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MxCsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

レジスタ状態には MxCsr も含まれています。  呼び出し規約では、このレジスタは揮発性部分と不揮発性部分に分類されます。  揮発性部分は 6 つの状態フラグ MXCSR\[0:5\] から構成され、残りのレジスタ MXCSR\[6:15\] は不揮発性と見なされます。  
  
 不揮発性部分は、プログラムの実行の開始時点で次の標準値に設定されます。  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 MXCSR 内の任意の不揮発性フィールドを変更した呼び出し先は、呼び出し元に戻す前にそのフィールドを復元する必要があります。  さらに、これらのフィールドのいずれかを変更した呼び出し元は、呼び出し先が変更された値を受け入れることに同意しない限り、呼び出し先を呼び出す前にフィールドの標準値に戻す必要があります。  
  
 コントロール フラグの不揮発性に関する規則には、次の 2 つの例外があります。  
  
-   指定した関数のドキュメント化の目的が、不揮発性 MxCsr フラグを変更することにある関数の場合。  
  
-   これらの規則に違反した結果のプログラムが、これらの規則に違反していないプログラムと同じ動作または意味を持つことが、プログラム全体の解析などをとおして明らかになった場合。  
  
 関数についてのドキュメントに特に記載されない限り、関数の境界を超える MXCSR の揮発性部分の状態についての前提条件はありません。  
  
## 参照  
 [呼び出し規約](../build/calling-convention.md)