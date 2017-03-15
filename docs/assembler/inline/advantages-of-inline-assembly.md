---
title: "インライン アセンブラーの長所 | Microsoft Docs"
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
  - "アセンブラー [C++], 利点"
  - "インライン アセンブラー [C++], インライン アセンブラーの概要"
  - "インライン アセンブラー [C++], 使用"
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# インライン アセンブラーの長所
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 インライン アセンブラーが別のアセンブリとリンク ステップを必要としないため別のアセンブラー方が便利です。  インライン アセンブラー コードでスコープ内にあるためプログラムの C コードと統合する方が簡単な C の変数や関数名を使用できます。  アセンブリ コードではC または C\+\+ のステートメントで混合インラインであるためC または C\+\+ で使いにくくまたは不可能なタスクを実行できます。  
  
 インライン アセンブリの使用は次のとおりです。:  
  
-   アセンブリ言語の書き込み関数。  
  
-   コードの速度クリティカル セクションの最適化スポット。  
  
-   デバイス ドライバーのハードウェアの直接アクセスを行います。  
  
-   「生の」呼び出しの記述のプロローグとエピローグ コード。  
  
 インライン アセンブラーは特殊な目的のツールです。  別のコンピューターにアプリケーションを移植する場合は別のモジュールに固有のマシン コードを配置します。  インライン アセンブラーで MASM \(Microsoft Macro Assembler\) マクロおよびデータ ディレクティブのすべてをサポートしないため便利な場合がこのようなモジュールで MASM を使用すると役立つ場合があります。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)