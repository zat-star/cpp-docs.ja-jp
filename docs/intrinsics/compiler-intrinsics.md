---
title: "コンパイラ組み込み | Microsoft Docs"
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
  - "cl.exe コンパイラ, 組み込み"
  - "cl.exe コンパイラ, パフォーマンス"
  - "コンパイラ組み込み"
  - "組み込み, コンパイラ"
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ組み込み
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ほとんどの関数はライブラリに含まれますが、関数によっては、コンパイラに組み込まれているものもあります。  これらは、組み込み関数または組み込みと呼ばれます。  
  
## 解説  
 関数が組み込みの場合、その関数のコードは通常、インラインで挿入されます。これにより、関数呼び出しのオーバーヘッドを回避し、その関数の非常に効率的なマシン語命令が生成されるようにします。  組み込みは通常、同等のインライン アセンブリよりも高速です。これは、オプティマイザーに組み込み関数の動作数に関する組み込まれた知識があるため、インライン アセンブリが使用できない最適化を使用できるためです。  また、オプティマイザーは、組み込みの展開、バッファーの配置、その他の調節を、呼び出しのコンテキストと引数に応じて行うことができます。  
  
 組み込みの使用はコードの移植性に影響します。これは、Visual C\+\+ で使用できる組み込み関数が、コードが他のコンパイラでコンパイルされた場合には利用できない場合があったり、また、あるターゲット アーキテクチャで使用できる組み込みが、すべてのアーキテクチャで使用できるとは限らないためです。  ただし、組み込みは通常、インライン アセンブリよりも移植性があります。  組み込みはインライン アセンブリがサポートされていない 64 ビット アーキテクチャに必要です。  
  
 `__assume` や `__ReadWriteBarrier` などの組み込みは、オプティマイザーの動作に影響を与える情報をコンパイラを提供します。  
  
 組み込み関数としてのみ使用できる組み込みもあり、また関数および組み込み実装の両方で使用できる組み込みもあります。  特定の関数のみを有効化するか、またはすべての組み込みを有効化するかによって、2 つのうちの 1 つの方法で組み込みの実装を使用するようにコンパイラに指示を与えることができます。  最初の方法は `#pragma intrinsic(``intrinsic-function-name-list``)` を使用することです。  プラグマを使用して、コンマで区切った 1 つの組み込みまたは複数の組み込みを指定することができます。  もう 1 つの方法は、特定のプラットフォームのすべての組み込みを利用可能にする [\/Oi \(組み込み関数の生成\)](../Topic/-Oi%20\(Generate%20Intrinsic%20Functions\).md) のコンパイラ オプションを使用することです。  **\/Oi** の下で、`#pragma function(``intrinsic-function-name-list``)` を使用すると、組み込み関数ではなく、強制的に関数呼び出しを使用します。  ある特定の組み込みのためのドキュメントが、そのルーチンは組み込みとしてのみ利用できることを記述している場合、**\/Oi** または `#pragma intrinsic`  が指定されているかどうかにかかわらず、その組み込みの実装が使用されます。  いずれの場合も、**\/Oi** または `#pragma intrinsic` により、オプティマイザーは組み込みを使用することができますが、その使用を強制されることはありません。  オプティマイザーは、関数を呼び出すことも可能です。  
  
 いくつかの標準 C\/C\+\+ ライブラリ関数は、いくつかのアーキテクチャの組み込み実装で使用できます。  CRT 関数を呼び出すと、コマンド ラインで **\/Oi** が指定された場合に、組み込み実装が使用されます。  
  
 共通組み込み関数のプロトタイプを宣言するヘッダー ファイルである \<intrin.h\> を使用できます。  製造元固有の組み込みは、\<immintrin.h\> および \<ammintrin.h\> の各ヘッダー ファイルです。  さらに、特定の Windows ヘッダーは、コンパイラの組み込みにマップする関数を宣言します。  
  
 次のセクションでは、さまざまなアーキテクチャで使用できるすべての組み込みを示します。  特定のターゲット プロセッサでの組み込みの動作の詳細については、開発元のリファレンス ドキュメントを参照してください。  
  
-   [ARM 組み込み](../intrinsics/arm-intrinsics.md)  
  
-   [x86 組み込み一覧](../Topic/x86%20Intrinsics%20List.md)  
  
-   [x64 \(amd64\) 組み込み一覧](../Topic/x64%20\(amd64\)%20Intrinsics%20List.md)  
  
-   [すべてのアーキテクチャで使用できる組み込み](../intrinsics/intrinsics-available-on-all-architectures.md)  
  
-   [組み込み関数のアルファベット順の一覧](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)  
  
## 参照  
 [ARM Assembler Reference](../Topic/ARM%20Assembler%20Reference.md)   
 [Microsoft Macro Assembler Reference](../assembler/masm/microsoft-macro-assembler-reference.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [C ランタイム ライブラリ リファレンス](../c-runtime-library/c-run-time-library-reference.md)