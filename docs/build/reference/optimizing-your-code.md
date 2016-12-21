---
title: "コードの最適化 | Microsoft Docs"
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
  - "cl.exe コンパイラ, パフォーマンス"
  - "コード, 最適化"
  - "最適化"
  - "最適化, C++ コード"
  - "パフォーマンス, コンパイラ"
  - "パフォーマンス, 最適化 (コードを)"
ms.assetid: 4f33e6c7-9870-43b3-9c2f-d7e44f764971
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コードの最適化
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

実行可能ファイルを最適化すると、実行速度の高速化とコード サイズの小型化のバランスを取ることができます。  ここでは、Visual C\+\+ に用意されている、コードの最適化に役立つ機構について説明します。  
  
## 言語機能  
 次のトピックでは、C\/C\+\+ 言語の最適化機能について説明します。  
  
 [最適化に影響するプラグマおよびキーワード](../../build/reference/optimization-pragmas-and-keywords.md)  
 パフォーマンスを向上させるためにコードで使用できるキーワードとプラグマの一覧。  
  
 [カテゴリ別のコンパイラ オプション](../../build/reference/compiler-options-listed-by-category.md)  
 実行速度やコード サイズに特に影響する **\/O** コンパイラ オプションの一覧。  
  
 [右辺値参照宣言子: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)  
 右辺値参照は、*移動セマンティクス*の実装をサポートします。  移動セマンティクスを使用してテンプレート ライブラリを実装すると、そのテンプレートを使用するアプリケーションのパフォーマンスが大幅に向上します。  
  
### optimize プラグマ  
 最適化したコード セクションでエラーまたは処理速度の低下が発生する場合は、[optimize](../../preprocessor/optimize.md) プラグマを使用して該当するセクションの最適化を無効にできます。  
  
 次のように、コードを 2 つのプラグマで囲みます。  
  
```  
#pragma optimize("", off)  
// some code here   
#pragma optimize("", on)  
```  
  
## プログラミング手法  
 最適化したコードをコンパイルすると、新たに警告メッセージが表示されることがあります。  多くの場合、このような警告は最適化されたコードだけに関連するものであり、これは予期された動作です。  これらの警告をよく確認すると、最適化に関する多くの問題を回避できます。  
  
 また、高速化のためにプログラムを最適化した結果、逆に速度が遅くなることもあります。  これは、最適化の方法によってはコード サイズが大きくなるためです。  たとえば、関数をインライン展開すると関数呼び出しのオーバーヘッドはなくなります。  しかし、インライン展開するコードが多すぎるとプログラムのサイズが大きくなり、仮想メモリのページ フォールトの回数が増えます。  したがって、関数の呼び出しをなくすことにより処理を高速化したとしても、メモリのスワップによってその効果が相殺されます。  
  
 次のトピックでは、推奨されるプログラミング方法について説明します。  
  
 [タイム クリティカルなコードを高速化するためのヒント](../../build/reference/tips-for-improving-time-critical-code.md)  
 適切なコーディング テクニックを使用することで、パフォーマンスを向上できます。  ここでは、コードのタイム クリティカルな部分のパフォーマンスを向上させるために役立つコーディング テクニックについて説明します。  
  
 [最適化の推奨事項](../../build/reference/optimization-best-practices.md)  
 アプリケーションの適切な最適化方法に関する一般的なガイドラインを示します。  
  
## 最適化されたコードのデバッグ  
 最適化を行うと、コンパイラによって生成されたコードが変更される可能性があります。そのため、アプリケーションをデバッグし、パフォーマンスを測定してから、コードを最適化することをお勧めします。  
  
 以下のトピックでは、デバッグ方法に関する基本情報について説明します。  
  
-   [Visual Studio でのデバッグ](../Topic/Debugging%20in%20Visual%20Studio.md)  
  
-   [リリース ビルド作成時によくある問題](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
 以下のトピックでは、デバッグ方法に関するより詳細な情報を提供します。  
  
-   [方法 : 最適化されたコードをデバッグする](../Topic/How%20to:%20Debug%20Optimized%20Code.md)  
  
-   [浮動小数点数の精度の低下](../../build/reference/why-floating-point-numbers-may-lose-precision.md)  
  
 次の各トピックでは、コードのビルド、読み込み、および実行を最適化する方法についての情報を示します。  
  
-   [コンパイラのスループットの向上](../../build/reference/improving-compiler-throughput.md)  
  
-   ["\(\)" のない関数名とコードの生成](../Topic/Using%20Function%20Name%20Without%20\(\)%20Produces%20No%20Code.md)  
  
-   [インライン アセンブリの最適化](../../assembler/inline/optimizing-inline-assembly.md)  
  
-   [ATL プロジェクトのコンパイラ最適化の指定](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)  
  
-   [読み込み時にクライアント アプリケーションのパフォーマンスを向上するための最適化手法](../../build/what-optimization-techniques-should-i-use.md)  
  
-   [!INCLUDE[crabout](../Token/crabout_md.md)]は DLL のメソッドを読み込む時間を単純化する方法「内部」の下に Web サイトの「MSDN Magazine」列「最適化 DLL の読み込み時パフォーマンス」[MSDN ライブラリ](http://go.microsoft.com/fwlink/?linkid=556) 参照します。  
  
-   [!INCLUDE[crabout](../Token/crabout_md.md)]はアプリケーションのページングを最小限に抑える方法を「Bugslayer 設定ツールで実行時のパフォーマンスを向上させる」と「Bugslayer 設定の一部とツールの実行時パフォーマンス Web サイトの「MSDN Magazine」Bugslayer」列の向上" 2 を参照[MSDN ライブラリ](http://go.microsoft.com/fwlink/?linkid=556) します。  
  
## 参照  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)