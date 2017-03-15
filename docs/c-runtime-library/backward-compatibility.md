---
title: "下位互換性 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "下位互換性"
  - "下位互換性, C ランタイム ライブラリ"
  - "互換性, C ランタイム ライブラリ"
  - "CRT, 互換性"
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 下位互換性
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

製品バージョンとの互換性のために、ライブラリ OLDNAMES.LIB で新しい名前が古い名前を割り当てます。  たとえば、`_open`への `open` の対応マップです。  コマンド ライン オプションの組み合わせを指定している場合にのみ OLDNAMES.LIB と明示的にリンクする必要があります:  
  
-   `/Zl` \(オブジェクト ファイルから既定のライブラリ名を省略\) と `/Ze` \(既定— Microsoft 拡張機能\) を使用できます。  
  
-   `/link` \(リンカ コントロール\)、`/NOD` \(既定のライブラリを検索しない\)、および `/Ze`  
  
 コマンド ライン コンパイラ オプションの詳細については、「[コンパイラ参照](../build/reference/compiler-options.md)」を参照してください。  
  
## 参照  
 [互換性](../c-runtime-library/compatibility.md)