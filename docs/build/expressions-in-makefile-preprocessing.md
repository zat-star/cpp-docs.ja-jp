---
title: "メイクファイル プリプロセスの式 | Microsoft Docs"
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
  - "式 [C++], メイクファイル処理"
  - "メイクファイル, プリプロセス"
  - "プリプロセス (メイクファイルを)"
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# メイクファイル プリプロセスの式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\!IF** または **\!ELSE IF** の `constantexpression` は、整数定数 \(10 進表記または C 言語表記\)、文字列定数、またはコマンドで構成されます。  かっこを使用すると、式をグループ化できます。  式では、C スタイルの符号付き長整数演算が使用されます。数値は、32 ビットの 2 の補数形式であり、– 2147483648 から 2147483647 までの範囲です。  
  
 式では、定数値、コマンドからの終了コード、文字列、マクロ、およびファイル システムのパスに適用可能な演算子を使用できます。  
  
## さらに詳しくは次のトピックをクリックしてください  
 [メイクファイルのプリプロセッサ演算子](../Topic/Makefile%20Preprocessing%20Operators.md)  
  
 [プリプロセスでのプログラムの実行](../build/executing-a-program-in-preprocessing.md)  
  
## 参照  
 [メイクファイルのプリプロセス](../Topic/Makefile%20Preprocessing.md)