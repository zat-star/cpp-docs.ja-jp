---
title: "setjmp/longjump | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# setjmp/longjump
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

setjmpex.h または setjmp.h をインクルードすると、[setjmp](../c-runtime-library/reference/setjmp.md) または [longjmp](../c-runtime-library/reference/longjmp.md) への呼び出しはすべて、デストラクターを呼び出してから最後に呼び出しを行うアンワインドになります。  これは、setjmp.h をインクルードしても句とデストラクターを呼び出さない x86 の場合と異なります。  
  
 `setjmp` を呼び出すと、現在のスタック ポインター、不揮発性レジスタ、および MxCsr レジスタが保持されます。  `longjmp` を呼び出すと、直前の `setjmp` 呼び出しサイトに戻されます。また、スタック ポインター、不揮発性レジスタ、および MxCsr レジスタが、直前の `setjmp` 呼び出しによって保持された状態に戻されます。  
  
## 参照  
 [呼び出し規約](../build/calling-convention.md)