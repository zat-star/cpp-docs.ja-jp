---
title: "チュートリアル: ユーザー インターフェイス スレッドからの処理の除去 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "除去 (ユーザー インターフェイス スレッドから処理を) [同時実行ランタイム]"
  - "ユーザー インターフェイス スレッド, 除去 (処理を) [同時実行ランタイム]"
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
caps.latest.revision: 14
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル: ユーザー インターフェイス スレッドからの処理の除去
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このドキュメントでは、Microsoft Foundation Classes \(MFC\) アプリケーションのユーザー インターフェイス \(UI\) スレッドによって実行される処理を、同時実行ランタイムを使用してワーカー スレッドに移動する方法について説明します。  また、時間のかかる描画操作のパフォーマンスを向上させる方法についても説明します。  
  
 描画のような他の処理の妨げになる操作をワーカー スレッドにオフロードすることで UI スレッドから処理を除去すると、アプリケーションの応答性を向上させることができます。  このチュートリアルでは、マンデルブロ フラクタルを生成する描画ルーチンを使用して、時間のかかるブロック操作を示します。  また、マンデルブロ フラクタルの生成は、各ピクセルの計算が他のすべての計算とは無関係に行われるので、並列化に適した候補でもあります。  
  
## 必須コンポーネント  
 このチュートリアルを開始する前に、次のトピックを参照してください。  
  
-   [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)  
  
-   [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)  
  
-   [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)  
  
 また、このチュートリアルを始める前に、MFC アプリケーションの開発および [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] の基礎について理解しておくことをお勧めします。  MFC の詳細については、「[MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)」を参照してください。  [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] の詳細については、「[GDI\+](_gdiplus_GDI_start_cpp)」を参照してください。  
  
##  <a name="top"></a> セクション  
 このチュートリアルは、次のセクションで構成されています。  
  
-   [MFC アプリケーションの作成](#application)  
  
-   [マンデルブロ アプリケーションのシリアル バージョンの実装](#serial)  
  
-   [ユーザー インターフェイス スレッドからの処理の除去](#removing-work)  
  
-   [描画パフォーマンスの向上](#performance)  
  
-   [取り消し処理のサポートの追加](#cancellation)  
  
##  <a name="application"></a> MFC アプリケーションの作成  
 ここでは、基本的な MFC アプリケーションを作成する方法について説明します。  
  
### Visual C\# MFC アプリケーションを作成するには  
  
1.  **\[ファイル\]** メニューの **\[新規作成\]** をポイントし、**\[プロジェクト\]** をクリックします。  
  
2.  **\[新しいプロジェクト\]** ダイアログ ボックスで、**\[インストールされたテンプレート\]** ペインの **\[Visual C\+\+\]** をクリックし、**\[テンプレート\]** ペインの **\[MFC アプリケーション\]** をクリックします。  プロジェクトの名前 \(`Mandelbrot` など\) を入力し、**\[OK\]** をクリックして、**MFC アプリケーション ウィザード**を表示します。  
  
3.  **\[アプリケーションの種類\]** ペインで **\[シングル ドキュメント\]** をクリックします。  **\[ドキュメント\/ビュー アーキテクチャのサポート\]** チェック ボックスがオフになっていることを確認します。  
  
4.  **\[完了\]** をクリックしてプロジェクトを作成し、**MFC アプリケーション ウィザード**を閉じます。  
  
     アプリケーションをビルドして実行することにより、アプリケーションが正常に作成されたことを確認します。  アプリケーションをビルドするには、**\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  アプリケーションが正常にビルドされたら、**\[デバッグ\]** メニューの **\[デバッグ開始\]** をクリックして、アプリケーションを実行します。  
  
##  <a name="serial"></a> マンデルブロ アプリケーションのシリアル バージョンの実装  
 ここでは、マンデルブロ フラクタルを描画する方法について説明します。  このバージョンは、マンデルブロ フラクタルを [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [Bitmap](https://msdn.microsoft.com/en-us/library/ms534420.aspx) オブジェクトに描画した後、そのビットマップの内容をクライアント ウィンドウにコピーします。  
  
#### マンデルブロ アプリケーションのシリアル バージョンを実装するには  
  
1.  stdafx.h に次の `#include` ディレクティブを追加します。  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  ChildView.h の `pragma` ディレクティブの後で、`BitmapPtr` 型を定義します。  `BitmapPtr` 型は、`Bitmap` オブジェクトへのポインターを複数のコンポーネントで共有できるようにします。  `Bitmap` オブジェクトは、どのコンポーネントからも参照されなくなると削除されます。  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  ChildView.h で、`CChildView` クラスの `protected` セクションに次のコードを追加します。  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  ChildView.cpp で、次の行をコメント アウトまたは削除します。  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     この手順により、デバッグ ビルドでアプリケーションが `DEBUG_NEW` アロケーターを使用しないようにします。このアロケーターは [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] と互換性がありません。  
  
5.  ChildView.cpp で、`using` ディレクティブを `Gdiplus` 名前空間に追加します。  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] の初期化とシャットダウンを行うために、次のコードを `CChildView`  クラスのコンストラクターとデストラクターに追加します。  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  `CChildView::DrawMandelbrot` メソッドを実装します。  このメソッドは、マンデルブロ フラクタルを指定した `Bitmap` オブジェクトに描画します。  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  `CChildView::OnPaint` メソッドを実装します。  このメソッドは、`CChildView::DrawMandelbrot` を呼び出した後、`Bitmap` オブジェクトの内容をウィンドウにコピーします。  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. アプリケーションをビルドして実行することにより、アプリケーションが正常に更新されたことを確認します。  
  
 次の図は、マンデルブロ アプリケーションの結果を示しています。  
  
 ![マンデルブロ アプリケーション](../../parallel/concrt/media/mandelbrot.png "Mandelbrot")  
  
 各ピクセルの計算には負荷がかかるので、すべての計算が終了するまで UI スレッドは新しいメッセージを処理できません。  これにより、アプリケーションの応答性が低下します。  ただし、UI スレッドから処理を除去することでこの問題を軽減できます。  
  
 \[[トップ](#top)\]  
  
##  <a name="removing-work"></a> UI スレッドからの処理の除去  
 ここでは、マンデルブロ アプリケーションの UI スレッドから描画処理を除去する方法について説明します。  描画処理を UI スレッドからワーカー スレッドに移動すると、イメージの生成はワーカー スレッドによってバックグラウンドで行われるので、UI スレッドでメッセージを処理できるようになります。  
  
 同時実行ランタイムには、タスクを実行する方法として、[タスク グループ](../../parallel/concrt/task-parallelism-concurrency-runtime.md)、[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)、および[軽量タスク](../../parallel/concrt/task-scheduler-concurrency-runtime.md)の 3 つが用意されています。  UI スレッドから処理を除去するには、これらの機能を使用できますが、タスク グループがキャンセルをサポートするため、この例では [concurrency::task\_group](../Topic/task_group%20Class.md) オブジェクト。  このチュートリアルの後半では、取り消し処理を使用して、クライアント ウィンドウがサイズ変更されるときに実行される処理の量を減らし、ウィンドウが破棄されるときにクリーンアップを実行します。  
  
 この例では、UI スレッドとワーカー スレッドが互いに通信できるようにするために [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) オブジェクトを使用します。  ワーカー スレッドは、イメージの生成が終了すると、`Bitmap` オブジェクトへのポインターを `unbounded_buffer` オブジェクトに送信した後、描画メッセージを UI スレッドにポストします。  UI スレッドは `unbounded_buffer` オブジェクトから `Bitmap` オブジェクトを受け取り、それをクライアント ウィンドウに描画します。  
  
#### 描画処理を UI スレッドから除去するには  
  
1.  stdafx.h に次の `#include` ディレクティブを追加します。  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  ChildView.h で、`task_group` および `unbounded_buffer` メンバー変数を、`CChildView` クラスの `protected` セクションに追加します。  `task_group` オブジェクトは、描画を実行するタスクを保持します。`unbounded_buffer` オブジェクトは、完成したマンデルブロ イメージを保持します。  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  ChildView.cpp で、`using` ディレクティブを `concurrency` 名前空間に追加します。  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  
4.  `CChildView::DrawMandelbrot` のメソッドでは、後 `Bitmap::UnlockBits`の呼び出しは、UI スレッドへの `Bitmap` オブジェクトを渡すに [concurrency::send](../Topic/send%20Function.md) 関数を呼び出しました。  その後、描画メッセージを UI スレッドにポストし、クライアント領域を無効にします。  
  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  更新された `Bitmap` オブジェクトを受け取ってイメージをクライアント ウィンドウに描画するように、`CChildView::OnPaint` メソッドを更新します。  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     `CChildView::OnPaint` メソッドは、マンデルブロ イメージがメッセージ バッファーに存在しない場合に、イメージを生成するタスクを作成します。  最初の描画メッセージの場合や、別のウィンドウがクライアント ウィンドウの前面に移動されている場合などは、メッセージ バッファーに `Bitmap` オブジェクトが含まれません。  
  
6.  アプリケーションをビルドして実行することにより、アプリケーションが正常に更新されたことを確認します。  
  
 描画処理がバックグラウンドで実行されるようになったため、UI の応答性が向上しています。  
  
 \[[トップ](#top)\]  
  
##  <a name="performance"></a> 描画パフォーマンスの向上  
 マンデルブロ フラクタルの生成は、各ピクセルの計算が他のすべての計算とは無関係に行われるので、並列化に適した候補です。  描画処理を並列化するには、[concurrency::parallel\_for](../Topic/parallel_for%20Function.md) アルゴリズムの呼び出しに `CChildView::DrawMandelbrot` のメソッドの `for` の外側のループを次のように変換します。  
  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 各ビットマップ要素の計算は独立しているので、ビットマップ メモリにアクセスする描画操作を同期する必要はありません。  これにより、使用できるプロセッサの数が増えると、パフォーマンスが向上します。  
  
 \[[トップ](#top)\]  
  
##  <a name="cancellation"></a> 取り消し処理のサポートの追加  
 ここでは、ウィンドウのサイズ変更を処理する方法、およびウィンドウが破棄されるときにアクティブな描画タスクを取り消す方法について説明します。  
  
 ドキュメント「[キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)」では、ランタイムで取り消し処理がどのように動作するかについて説明します。  取り消し処理は他の処理と連携して行われます。このため、すぐに実行される訳ではありません。  取り消されたタスクを停止するため、ランタイムは、そのタスクからランタイムへの以降の呼び出しの間に内部例外をスローします。  前のセクションでは、`parallel_for` アルゴリズムを使用して描画タスクのパフォーマンスを向上させる方法について説明しました。  ランタイムは `parallel_for` の呼び出しによってタスクの停止を有効にし、その結果取り消し処理の動作を有効にします。  
  
### アクティブなタスクの取り消し  
 マンデルブロ アプリケーションは、クライアント ウィンドウのサイズと等しい寸法の  `Bitmap` オブジェクトを作成します。  クライアント ウィンドウのサイズが変更されるたびに、アプリケーションは新しいバックグラウンド タスクを作成して、新しいウィンドウ サイズのイメージを生成します。  アプリケーションでは、このような中間的なイメージは必要ありません。最終的なウィンドウ サイズのイメージのみが必要です。  アプリケーションがこの余分な処理を実行しなくて済むように、`WM_SIZE` メッセージおよび `WM_SIZING` メッセージのメッセージ ハンドラーでアクティブな描画タスクを取り消し、ウィンドウのサイズが変更された後で描画処理を再スケジュールできます。  
  
 ウィンドウのサイズが変更されたときにアクティブな描画タスクを取り消すには、アプリケーションに `WM_SIZING` と `WM_SIZE` メッセージのハンドラーの [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) のメソッドを呼び出します。  `WM_SIZE` メッセージのハンドラーは、完了するすべてのアクティブ タスクが待機状態に [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md) のメソッドを呼び出して更新されたウィンドウ サイズの描画タスクを再スケジュールします。  
  
 クライアント ウィンドウが破棄されるときは、アクティブな描画タスクをすべて取り消すことをお勧めします。  アクティブな描画タスクをすべて取り消すことで、クライアント ウィンドウが破棄された後でワーカー スレッドが UI スレッドにメッセージをポストしないことが保証されます。  アプリケーションは、`WM_DESTROY` メッセージのハンドラー内でアクティブな描画タスクをすべて取り消します。  
  
### 取り消しへの応答  
 描画タスクを実行する `CChildView::DrawMandelbrot` メソッドは、取り消しに応答する必要があります。  ランタイムは例外処理を使用してタスクを取り消すので、`CChildView::DrawMandelbrot` メソッドは例外セーフな方法を使用して、すべてのリソースが正しくクリーンアップされることを保証する必要があります。  この例では、*Resource Acquisition Is Initialization* \(RAII\) パターンを使用して、タスクを取り消すときにビットマップのビットがロックされていないことを保証します。  
  
##### マンデルブロ アプリケーションに取り消し処理のサポートを追加するには  
  
1.  ChildView.h で、`CChildView` クラスの `protected` セクションに、`OnSize`、`OnSizing`、および `OnDestroy` のメッセージ マップ関数の宣言を追加します。  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  ChildView.cpp で、`WM_SIZE`、`WM_SIZING`、および `WM_DESTROY` メッセージのハンドラーを含むようにメッセージ マップを変更します。  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  `CChildView::OnSizing` メソッドを実装します。  このメソッドは既存の描画タスクをすべて取り消します。  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  `CChildView::OnSize` メソッドを実装します。  このメソッドは、既存の描画タスクをすべて取り消し、更新されたクライアント ウィンドウ サイズに対する新しい描画タスクを作成します。  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  `CChildView::OnDestroy` メソッドを実装します。  このメソッドは既存の描画タスクをすべて取り消します。  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  ChildView.cpp で、RAII パターンを実装する `scope_guard` クラスを定義します。  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  `CChildView::DrawMandelbrot` メソッドで、`Bitmap::LockBits` の呼び出しの後に次のコードを追加します。  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     このコードは、`scope_guard` オブジェクトを作成することで取り消しを処理します。  オブジェクトがスコープから外れたら、ビットマップのビットをロック解除します。  
  
8.  `CChildView::DrawMandelbrot` メソッドの最後を変更し、ビットマップのビットがロック解除された後で、メッセージが UI スレッドに送信される前に、`scope_guard` オブジェクトを終了します。  これにより、ビットマップのビットがロック解除される前に UI スレッドが更新されることがなくなります。  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. アプリケーションをビルドして実行することにより、アプリケーションが正常に更新されたことを確認します。  
  
 ウィンドウのサイズを変更すると、最終的なウィンドウ サイズに対してのみ描画処理が実行されます。  ウィンドウが破棄されると、アクティブな描画タスクもすべて取り消されます。  
  
 \[[トップ](#top)\]  
  
## 参照  
 [同時実行ランタイムのチュートリアル](../Topic/Concurrency%20Runtime%20Walkthroughs.md)   
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)   
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)   
 [キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [MFC デスクトップ アプリケーション](../../mfc/mfc-desktop-applications.md)