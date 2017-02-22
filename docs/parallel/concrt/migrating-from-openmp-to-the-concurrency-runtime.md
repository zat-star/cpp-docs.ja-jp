---
title: "OpenMP から同時実行ランタイムへの移行 | Microsoft Docs"
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
  - "同時実行ランタイム, 移行 (OpenMP から)"
  - "OpenMP, 移行 (同時実行ランタイムに)"
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# OpenMP から同時実行ランタイムへの移行
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

同時実行ランタイムでは、さまざまなプログラミング モデルを使用できます。  これらのモデルは、他のライブラリのモデルと重複する場合、または他のライブラリのモデルを補完する場合があります。  ここでは、[OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md) と同時実行ランタイムの違いについて説明し、既存の OpenMP コードから同時実行ランタイムの使用に移行する方法の例を示します。  
  
 OpenMP プログラミング モデルは、オープン標準により定義されており、Fortran および C\/C\+\+ プログラミング言語に正しく準拠しています。  Visual C\+\+ コンパイラでサポートされている OpenMP Version 2.0 および 2.5 は、反復処理の並列アルゴリズムに適しています。つまり、これらは、データの配列を並列に反復処理します。  OpenMP 3.0 では、反復タスクのほか、非反復タスクもサポートされています。  
  
 OpenMP は、並列化の度合いが事前に決定され、システムで使用可能なリソースと対応する場合に最も効果的です。  OpenMP モデルは、非常に大きい計算の問題が 1 台のコンピューターの処理リソース全体に分散される高パフォーマンスのコンピューティングに特に適しています。  このシナリオでは、ハードウェア環境は一般に固定されます。また、開発者は、このアルゴリズムの実行時に、すべてのコンピューティング リソースに排他的にアクセスできることを十分に期待できます。  
  
 ただし、制約が少ないコンピューティング環境は、OpenMP に適していない場合があります。  たとえば、OpenMP 2.0 や 2.5 を使用して、再帰の問題 \(クイック ソート アルゴリズム、データ ツリーの検索など\) を実装するのは比較的困難です。  同時実行ランタイムでは、[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)や[並列パターン ライブラリ](../../parallel/concrt/parallel-patterns-library-ppl.md) \(PPL\) を使用して、OpenMP の機能を補うことができます。  非同期エージェント ライブラリでは、粒度の粗いタスクの並列化がサポートされています。PPL では、より粒度の細かい並列タスクがサポートされています。  同時実行ランタイムには、アプリケーションのロジックを重視できるよう、操作を並列に実行するのに必要なインフラストラクチャが用意されています。  ただし、同時実行ランタイムはさまざまなプログラミング モデルに対応しているため、OpenMP などの他の同時実行ライブラリと比較して、スケジューリングのオーバーヘッドが大きくなります。  したがって、既存の OpenMP コードから同時実行ランタイムの使用に切り替える場合は、パフォーマンスを段階的にテストすることをお勧めします。  
  
## OpenMP から同時実行ランタイムへの移行に適した状況  
 次のような場合、既存の OpenMP コードから同時実行ランタイムの使用に移行すると効果的です。  
  
|状況|同時実行ランタイムの利点|  
|--------|------------------|  
|拡張可能な同時実行プログラミング フレームワークが必要である。|同時実行ランタイムの機能の多くは拡張できます。  既存の機能を組み合わせて新しい機能を作成することもできます。  OpenMP はコンパイラ ディレクティブに依存しているため、簡単には拡張できません。|  
|アプリケーションが協調ブロッキングから恩恵を得る。|必要なリソースがまだ利用できないためにタスクがブロックされた場合、最初のタスクがリソースを待っている間、他のタスクを実行できます。|  
|アプリケーションが動的な負荷分散から恩恵を得る。|同時実行ランタイムでは、スケジューリング アルゴリズムを使用して、作業負荷が変化したときにコンピューティング リソースの割り当てを調整します。  OpenMP では、スケジューラが並列領域にコンピューティング リソースを割り当てると、そのリソース割り当てが計算全体で固定されます。|  
|例外処理のサポートが必要である。|PPL では、並列領域またはループの内側でも外側でも例外をキャッチできます。  OpenMP では、並列領域またはループの内側で例外を処理する必要があります。|  
|取り消し機構が必要である。|PPL では、アプリケーションは個々のタスクと並列処理ツリーの両方を取り消すことができます。  OpenMP では、アプリケーションは独自の取り消し機構を実装する必要があります。|  
|並列コードの開始と終了を別々のコンテキストで行う必要がある。|同時実行ランタイムでは、タスクを特定のコンテキストで開始し、そのタスクに対する待機や取り消しの操作を別のコンテキストで行うことができます。  OpenMP では、並列処理の開始と終了は常に同じコンテキストで行う必要があります。|  
|拡張デバッグのサポートが必要である。|Visual Studio では、**\[並列スタック\]** ウィンドウと **\[並列タスク\]** ウィンドウを使用して、マルチスレッド アプリケーションのデバッグをより簡単に行うことができます。<br /><br /> 同時実行ランタイムのデバッグのサポートの詳細については、「[\[タスク\] ウィンドウの使用](../Topic/Using%20the%20Tasks%20Window.md)」、「[\[並列スタック\] ウィンドウの使用](../Topic/Using%20the%20Parallel%20Stacks%20Window.md)」、および「[チュートリアル: 並行アプリケーションのデバッグ](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md)」を参照してください。|  
  
## OpenMP から同時実行ランタイムへの移行に適さない状況  
 次のような場合、既存の OpenMP コードから同時実行ランタイムの使用に移行するのは適切ではありません。  
  
|状況|説明|  
|--------|--------|  
|アプリケーションが既に要件を満たしている。|アプリケーションのパフォーマンスと現在のデバッグ サポートに満足している場合、移行は適切ではありません。|  
|並列ループ本体での処理量が少ない。|ループ本体の並列実行のメリットよりも、同時実行ランタイムのタスク スケジューラのオーバーヘッドの方が重視されることがあります \(特に、ループ本体が比較的小さい場合など\)。|  
|アプリケーションが C で記述されている。|同時実行ランタイムは多くの C\+\+ 機能を使用するため、C アプリケーションで最大限に活用できるコードを記述できない状況では適していません。|  
  
## 関連トピック  
 [方法: OpenMP の parallel for ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  
 OpenMP [並列](../../parallel/openmp/reference/parallel.md) と [for](../Topic/for%20\(OpenMP\).md) のディレクティブを使用する基本的なループを取り上げ、同時実行ランタイムの [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムを使用するように切り替える方法について説明します。  
  
 [方法: キャンセル処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 必ずしもすべての反復を実行する必要のない OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../Topic/for%20\(OpenMP\).md) ループを取り上げ、同時実行ランタイムの取り消し機構を使用するように切り替える方法について説明します。  
  
 [方法: 例外処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 例外処理を実行する OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../Topic/for%20\(OpenMP\).md) ループを取り上げ、同時実行ランタイムの例外処理機構を使用するように切り替える方法について説明します。  
  
 [方法: 減少変数を使用する OpenMP ループを変換し、同時実行ランタイムを使用する](../Topic/How%20to:%20Convert%20an%20OpenMP%20Loop%20that%20Uses%20a%20Reduction%20Variable%20to%20Use%20the%20Concurrency%20Runtime.md)  
 [reduction](../../parallel/openmp/reference/reduction.md) 句を使用する OpenMP [parallel](../../parallel/openmp/reference/parallel.md) [for](../Topic/for%20\(OpenMP\).md) ループを取り上げ、同時実行ランタイムを使用するように切り替える方法について説明します。  
  
## 参照  
 [同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/openmp/openmp-in-visual-cpp.md)   
 [並列パターン ライブラリ \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)