---
title: "&lt;ccomplex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<ccomplex>"
dev_langs: 
  - "C++"
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ccomplex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL ヘッダー [\<complex\>](../Topic/%3Ccomplex%3E.md) をインクルードします。これは、標準 C ライブラリ ヘッダー \<complex.h\> を効果的にインクルードし、関連する名前を `std` 名前空間に追加します。  
  
## 構文  
  
```cpp  
  
#include <ccomplex>  
  
```  
  
## 解説  
 このヘッダーをインクルードすると、標準 C ライブラリ ヘッダーの外部リンケージで宣言された名前が、`std` 名前空間でも宣言されます。  
  
 \<complex.h\> で宣言される名前 `clog` は `std` 名前空間に定義されていません。これは、[\<iostream\>](../standard-library/iostream.md) で宣言されている `clog` と競合する可能性があるためです。  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [STL の概要](../standard-library/cpp-standard-library-overview.md)