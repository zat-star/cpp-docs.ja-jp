---
title: "Visual C++ の 64 ビットへの移行に関する一般的な問題 | Microsoft Docs"
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
helpviewer_keywords: 
  - "32 ビット コードの移植 [C++]"
  - "64 ビット アプリケーション [C++]"
  - "64 ビット コンパイラ [C++], 移行"
  - "64 ビット コンパイラ [C++], 移植 (32 ビット コードの)"
  - "64 ビット プログラミング [C++], 移行"
  - "移行 [C++], 64 ビット コードの問題"
  - "移植 (32 ビット コードを 64 ビット コードに)"
  - "アップグレード (Visual C++ アプリケーションの), 32 ビット コード"
  - "Win64 [C++]"
ms.assetid: d17fb838-7513-4e2d-8b27-a1666f17ad76
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ の 64 ビットへの移行に関する一般的な問題
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ を使用して、64 ビット Windows オペレーティング システムで実行するアプリケーションを作成する場合は、以下の点を考慮する必要があります。  
  
-   `int` と `long` は、64 ビット Windows オペレーティング システム上で 32 ビット値です。  64 ビット プラットフォーム用にコンパイルする必要があるプログラムでは、ポインターを 32 ビット変数に割り当てないように注意してください。  ポインターは、64 ビットのプラットフォームでは 64 ビットなので、ポインターを 32 ビット変数に割り当てると、ポインター値を切り捨てることになります。  
  
-   `size_t`、`time_t`、および  `ptrdiff_t` は、64 ビット Windows オペレーティング システム上で 64 ビット値です。  
  
-   `time_t` は、Visual C\+\+ 2005 以前の Visual C\+\+ バージョンの 32 ビット Windows オペレーティング システムでは 32 ビット値です。  現在は、`time_t` は既定で 64 ビット整数です。  詳細については、「[時間管理](../c-runtime-library/time-management.md)」を参照してください。  
  
     コード内で `int` 値を使用する場所について、およびその値を `size_t` または `time_t` のどちらの値として処理するかについて考慮する必要があります。  32 ビットよりも大きくなると、`int` ストレージに返されるときにデータが切り捨てられます。  
  
 %x \(16 進数 `int` 形式\) `printf` 修飾子は、64 ビット Windows オペレーティング システム上では期待どおりに動作しません。  この修飾子は、渡された値の最初の 32 ビットしか操作しません。  
  
-   32 ビット整数型を 16 進数形式で表示するには、%I32x を使用します。  
  
-   64 ビット整数型を 16 進数形式で表示するには、%I64x を使用します。  
  
-   %p \(ポインターに対応する 16 進数形式\) は、64 ビット Windows オペレーティング システム上で期待どおりに動作します。  
  
 詳細については次を参照してください:  
  
-   [コンパイラ オプション](../build/reference/compiler-options.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="8228b16e9fef41dbba1af1d78bf0cc87" class\="tgtSentence"\>移行に関するヒント\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/aa384214)  
  
## 参照  
 [64 ビット用プログラムの構成](../build/configuring-programs-for-64-bit-visual-cpp.md)   
 [プログラムの移植](http://msdn.microsoft.com/ja-jp/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)