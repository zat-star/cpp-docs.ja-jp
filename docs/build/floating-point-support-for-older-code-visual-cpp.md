---
title: "旧形式のコードのための浮動小数点サポート (Visual C++) | Microsoft Docs"
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
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 旧形式のコードのための浮動小数点サポート (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MMX および浮動小数点スタック レジスタ \(MM0\-MM7\/ST0\-ST7\) は、コンテキスト スイッチ全体で保持されます。  これらのレジスタに対する明示的な呼び出し規約はありません。  これらのレジスタの使用は、カーネル モード コードで厳密に禁止されています。  
  
## 参照  
 [呼び出し規約](../build/calling-convention.md)