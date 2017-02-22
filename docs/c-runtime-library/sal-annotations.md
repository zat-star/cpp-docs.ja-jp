---
title: "SAL 注釈 | Microsoft Docs"
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
helpviewer_keywords: 
  - "__bcount 注釈"
  - "__checkreturn 注釈"
  - "__deref 注釈"
  - "__deref_opt 注釈"
  - "__ecount 注釈"
  - "__full 注釈"
  - "__in 注釈"
  - "__inout 注釈"
  - "__nz 注釈"
  - "__opt 注釈"
  - "__out 注釈"
  - "__part 注釈"
  - "__ref 注釈"
  - "__z 注釈"
  - "_bcount 注釈"
  - "_CA_SHOULD_CHECK_RETURN"
  - "_deref 注釈"
  - "_deref_opt 注釈"
  - "_ecount 注釈"
  - "_full 注釈"
  - "_in 注釈"
  - "_inout 注釈"
  - "_nz 注釈"
  - "_opt 注釈"
  - "_out 注釈"
  - "_part 注釈"
  - "_ref 注釈"
  - "_z 注釈"
  - "注釈 [C++]"
  - "bcount 注釈"
  - "deref 注釈"
  - "deref_opt 注釈"
  - "ecount 注釈"
  - "full 注釈"
  - "in 注釈"
  - "inout 注釈"
  - "nz 注釈"
  - "opt 注釈"
  - "out 注釈"
  - "part 注釈"
  - "ref 注釈"
  - "SAL 注釈"
  - "SAL 注釈, _CA_SHOULD_CHECK_RETURN"
  - "z 注釈"
ms.assetid: 81893638-010c-41a0-9cb3-666fe360f3e0
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# SAL 注釈
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ライブラリ ヘッダー ファイルを調べると、`_In_z` や `_Out_z_cap_(_Size)` など、通常とは異なる注釈がいくつかあることに気付く場合があります。  これらは、Microsoft のソース コード注釈言語 \(SAL\) の例です。SAL は、関数が自身のパラメーターをどのように使用するかを記述する注釈のセットを提供します。つまり、これらの注釈は、たとえば関数がそのパラメーターについて何を前提としているか、または関数が終了時に何を保証するかを示します。  これらの注釈はヘッダー ファイル \<sal.h\> で定義されています。  
  
 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] での SAL 注釈の使用の詳細については、「[SAL 注釈を使って C\/C\+\+ のコード障害を減らす方法](../Topic/Using%20SAL%20Annotations%20to%20Reduce%20C-C++%20Code%20Defects.md)」を参照してください。  
  
## 参照  
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)