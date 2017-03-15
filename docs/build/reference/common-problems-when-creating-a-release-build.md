---
title: "リリース ビルド作成時によくある問題 | Microsoft Docs"
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
  - "デバッグ ビルド, 相違点 (リリース ビルドの)"
  - "デバッグ メモリ アロケーター"
  - "デバッグ [MFC], リリース ビルド"
  - "ヒープ レイアウトの問題"
  - "メモリ [C++], 上書き"
  - "MFC [C++], リリース ビルド"
  - "最適化 [C++], コンパイラ"
  - "ポインター, 無効な"
  - "プロジェクト [C++], デバッグ構成"
  - "リリース ビルド, ビルド (アプリケーションを)"
  - "リリース ビルド, トラブルシューティング"
  - "無効なポインター"
  - "トラブルシューティング (リリース ビルド)"
  - "トラブルシューティング (Visual C++)"
  - "予測不可能なコード生成"
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# リリース ビルド作成時によくある問題
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プログラムの開発では、通常、プロジェクトのデバッグ ビルドを使用してビルドとテストを行います。  その後、リリース ビルドでアプリケーションをビルドすると、アクセス違反が発生する場合があります。  
  
 次は、デバッグ ビルドとリリース \(非デバッグ\) ビルドの主な相違点です。  このほかにも相違点がありますが、ここで説明する相違点は、アプリケーションがデバッグ ビルドでは動作してもリリース ビルドではエラーになるような、大きな相違点です。  
  
-   [ヒープ レイアウト](#_core_heap_layout)  
  
-   [コンパイル](#_core_compilation)  
  
-   [ポインター サポート](#_core_pointer_support)  
  
-   [最適化](#_core_optimizations)  
  
 リリース ビルドのエラーをデバッグ ビルドでキャッチする方法については、[\/GZ \(デバッグ ビルド時のリリース ビルド エラーのキャッチ\)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md) コンパイラ オプションを参照してください。  
  
##  <a name="_core_heap_layout"></a> ヒープ レイアウト  
 ヒープ レイアウトは、デバッグでは動作するアプリケーションがリリースではエラーとなる原因の約 90% を占めます。  
  
 プロジェクトをデバッグ ビルドする場合は、デバッグ メモリ アロケーターが使用されます。  このため、すべてのメモリ割り当ては、ガード バイトで囲まれます。  ガード バイトによって、メモリの上書きが検出されます。  リリース バージョンとデバッグ バージョンではヒープ レイアウトが異なるので、デバッグ ビルドではメモリの上書きによって問題が生じない場合でも、リリース ビルドでは致命的な問題が生じる場合があります。  
  
 詳細については、「[メモリ上書きのチェック](../../build/reference/checking-for-memory-overwrites.md)」および「[デバッグ ビルドを使用したメモリ上書きのチェック](../Topic/Using%20the%20Debug%20Build%20to%20Check%20for%20Memory%20Overwrite.md)」を参照してください。  
  
##  <a name="_core_compilation"></a> コンパイル  
 リリース用にビルドする場合、大半の MFC マクロと MFC 実装が変更されます。  特に、ASSERT マクロはリリース ビルドでは評価されないため、ASSERT にあるコードは実行されません。  詳細については、「[ASSERT ステートメントの確認](../../build/reference/using-verify-instead-of-assert.md)」を参照してください。  
  
 リリース ビルドでは、実行速度を上げるために一部の関数がインライン化されます。  通常、リリース ビルドでは最適化がオンになっています。  また、使用されるメモリ アロケーターも異なります。  
  
##  <a name="_core_pointer_support"></a> ポインター サポート  
 デバッグ情報がないと、アプリケーションから埋め込みが削除されます。  リリース ビルドでは、不正なポインターが、デバッグ情報ではなく初期化されていないメモリを指す可能性があります。  
  
##  <a name="_core_optimizations"></a> 最適化  
 最適化コンパイラは、特定のコード セグメントの内容に応じて、予期しないコードを生成することがあります。  これがリリース ビルドの問題を引き起こすことはまれですが、問題が発生する場合もあります。  解決方法については、「[コードの最適化](../../build/reference/optimizing-your-code.md)」を参照してください。  
  
## 参照  
 [リリース ビルド](../../build/reference/release-builds.md)   
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)