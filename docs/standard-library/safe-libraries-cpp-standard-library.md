---
title: "安全なライブラリ: C++ 標準ライブラリ | Microsoft Docs"
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
  - "_SCL_SECURE_NO_DEPRECATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "安全なライブラリ"
  - "安全なライブラリ、標準 C++ ライブラリ"
  - "安全な標準 C++ ライブラリ"
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 安全なライブラリ: C++ 標準ライブラリ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ に付属しているライブラリ \(標準 C\+\+ ライブラリを含む\) には、安全性を向上するためのいくつかの機能強化が加えられています。  
  
 標準 C\+\+ ライブラリに含まれる一部のメソッドは、バッファ オーバーランが発生する可能性のあるものや、コードに欠陥があることによる潜在的な危険性が確認されています。 こうしたメソッドの使用はお勧めできません。また、それらに置き換わる、新しい安全性の高いメソッドが作成されています。 これに該当する新しいメソッドのすべてには、末尾に `_s` が付いています。  
  
 反復子とアルゴリズムにも、安全性を向上するためのいくつかの機能強化が行われています。 詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」、「[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)」、および「[\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。  
  
## 解説  
 次の表に、潜在的な危険性のある標準 C\+\+ ライブラリのメソッドと、それと同等な安全なメソッドを示します。  
  
|潜在的に危険なメソッド|安全な同等のメソッド|  
|-----------------|----------------|  
|[basic\_string::copy](../Topic/basic_string::copy.md)|[basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md)|  
|[char\_traits::copy](../Topic/char_traits::copy.md)|[char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md)|  
  
 上記の潜在的に危険なメソッドのいずれかを呼び出したり、不適切に反復子を使用したりすると、コンパイラは [コンパイラの警告 \(レベル 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) を生成します。 これらの警告を無効にする方法の詳細については、「[\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。  
  
## このセクションの内容  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [チェックを行う反復子](../standard-library/checked-iterators.md)  
  
 [反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)  
  
## 参照  
 [STL の概要](../standard-library/cpp-standard-library-overview.md)