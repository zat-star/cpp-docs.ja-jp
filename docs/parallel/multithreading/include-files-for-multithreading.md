---
title: "マルチスレッドのためのインクルード ファイル | Microsoft Docs"
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
  - "インクルード ファイル, マルチスレッド"
  - "マルチスレッド処理 [C++], インクルード ファイル"
  - "スレッド処理 [C++], インクルード ファイル"
ms.assetid: 98d764f9-71f4-4da5-8f3a-8d2d26e96799
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# マルチスレッドのためのインクルード ファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

標準のインクルード ファイルでは、C ランタイム ライブラリ関数がライブラリに実装されていると宣言します。  [最大限の最適化](../../build/reference/ox-full-optimization.md) \(\/Ox\) オプションまたは[レジスタ呼び出し規約](../../build/reference/gd-gr-gv-gz-calling-convention.md) \(\/Gr\) オプションを指定している場合、コンパイラは、レジスタ呼び出し規約を使ってすべての関数を呼び出すものと見なします。  ランタイム ライブラリ関数は、C の呼び出し規約でコンパイルされているので、標準のインクルード ファイルの宣言では、これらの関数に対する正しい外部参照を生成するようにコンパイラに指示します。  
  
## 参照  
 [C と Win32 を使用するマルチスレッド](../../parallel/multithreading-with-c-and-win32.md)