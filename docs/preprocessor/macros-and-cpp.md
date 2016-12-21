---
title: "マクロと C++ | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "マクロ"
  - "マクロ, C++"
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# マクロと C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ にはいくつかの新機能がありますが、その一部は ANSI C プリプロセッサが提供する機能に代替します。  これらの新機能によって、次のように言語のタイプ セーフと予測可能性が向上します。  
  
-   C\+\+ では、**const** として宣言されたオブジェクトを定数式で使用できます。  これによりプログラム内で、型と値の情報を持つ定数と、デバッガーによって記号で表示できる列挙体を宣言できます。  これに比べて、プリプロセッサの `#define` ディレクティブを使用して定数を定義する方法は、あまり正確ではありません。  アドレスを取得する式がプログラムに存在しない場合、**const** オブジェクトに記憶領域が割り当てられません。  
  
-   C\+\+ のインライン関数の機能が、関数型マクロに代わって提供されています。  マクロよりもインライン関数を使用することの利点は次のとおりです。  
  
    -   インライン関数はタイプ セーフです。  インライン関数には、通常の関数と同じ型チェックが実行されます。  マクロは、タイプ セーフではありません。  
  
    -   インライン関数では、副作用のある引数の処理が修正されます。  インライン関数は、関数本体を入力する前に、引数として渡された式を評価します。  したがって、副作用のある式が安全でない状態のまま使用される可能性はありません。  
  
 インライン関数の詳細については、「[inline、\_\_inline、\_\_forceinline](../misc/inline-inline-forceinline.md)」を参照してください。  
  
 下位互換性を維持するため、ANSI C と以前の C\+\+ 仕様にあるすべてのプリプロセッサ機能は Microsoft C\+\+ で保持されています。  
  
## 参照  
 [定義済みマクロ](../preprocessor/predefined-macros.md)   
 [マクロ](../Topic/Macros%20\(C-C++\).md)