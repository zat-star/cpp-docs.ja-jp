---
title: "C++ AMP (C++ Accelerated Massive Parallelism) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "C++ Accelerated Massive Parallelism, はじめに"
  - "C++ AMP (C++ Accelerated Massive Parallelism を参照)"
ms.assetid: e27824cb-3167-409b-8c3f-a0e476d8f349
caps.latest.revision: 22
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ AMP (C++ Accelerated Massive Parallelism)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\) は、独立したグラフィックス カードの GPU \(graphics processing unit\) などの一般的なデータ並列ハードウェアを活用して、C\+\+ コードの実行を高速化します。  C\+\+ AMP のプログラミング モデルには、多次元配列、インデックス作成、メモリ転送、およびタイルのサポートが含まれています。  また、数学関数ライブラリも含まれています。  C\+\+ AMP の言語拡張機能を使用して、データを CPU から GPU へ、また GPU から CPU へどのように移動するかを制御できます。  
  
## 関連トピック  
  
|タイトル|説明|  
|----------|--------|  
|[C\+\+ AMP の概要](../../parallel/amp/cpp-amp-overview.md)|C\+\+ AMP および数値演算ライブラリの主な機能について説明します。|  
|[ラムダ、関数オブジェクト、および制限関数の使用](../../parallel/amp/using-lambdas-function-objects-and-restricted-functions.md)|[parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) メソッドの呼び出しで、ラムダ式、関数オブジェクト、および制限関数を使用する方法について説明します。|  
|[タイルの使用](../../parallel/amp/using-tiles.md)|タイルを使用して C\+\+ AMP コードを高速化する方法について説明します。|  
|[アクセラレータおよび accelerator\_view オブジェクトの使用](../../parallel/amp/using-accelerator-and-accelerator-view-objects.md)|アクセラレータを使用して GPU でのコードの実行をカスタマイズする方法について説明します。|  
|[Windows ストア アプリでの C\+\+ AMP の使用](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)|Windows ランタイム型を使用する [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで C\+\+ AMP を使用する方法について説明します。|  
|[グラフィックス \(C\+\+ AMP\)](../../parallel/amp/graphics-cpp-amp.md)|C\+\+ AMP のグラフィックス ライブラリを使用する方法について説明します。|  
|[チュートリアル : 行列乗算](../../parallel/amp/walkthrough-matrix-multiplication.md)|C\+\+ AMP コードとタイルを使用した行列乗算を示します。|  
|[チュートリアル : C\+\+ AMP アプリケーションのデバッグ](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)|並列リダクションを使用して整数の大きな配列を合計するアプリケーションを作成してデバッグする方法について説明します。|  
  
## 参照  
 [リファレンス \(C\+\+ AMP\)](../../parallel/amp/reference/reference-cpp-amp.md)  
  
 [tile\_static キーワード](../Topic/tile_static%20Keyword.md)  
  
 [restrict \(C\+\+ AMP\)](../../cpp/restrict-cpp-amp.md)  
  
## その他のリソース  
 [Parallel Programming in Native Code blog \(ネイティブ コードでの並列プログラミング ブログ\)](http://go.microsoft.com/fwlink/p/?LinkId=238472)  
  
 [C\+\+ AMP sample projects for download \(ダウンロード用の C\+\+ AMP サンプル プロジェクト\)](http://go.microsoft.com/fwlink/p/?LinkId=248508)  
  
 [Analyzing C\+\+ AMP Code with the Concurrency Visualizer \(同時実行ビジュアライザーによる C\+\+ AMP コードの分析\)](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)