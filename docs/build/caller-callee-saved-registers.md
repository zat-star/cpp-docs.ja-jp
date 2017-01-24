---
title: "呼び出し元または呼び出し先保存済みレジスタ | Microsoft Docs"
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
ms.assetid: 0533bd4b-d6bb-4ce1-8201-495e16870cbb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 呼び出し元または呼び出し先保存済みレジスタ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

RAX、RCX、RDX、R8、R9、R10、R11 の各レジスタは、揮発性と考えられるため、プログラム全体の最適化などの分析によって安全が証明可能な場合以外は、関数の呼び出し時に破棄されると見なす必要があります。  
  
 RBX、RBP、RDI、RSI、RSP、R12、R13、R14、および R15 の各レジスタは、不揮発性と考えられるため、これらのレジスタを使用する関数によって保存や復元が行われる必要があります。  
  
## 参照  
 [呼び出し規約](../build/calling-convention.md)