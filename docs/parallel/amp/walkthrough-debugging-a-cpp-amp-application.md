---
title: "チュートリアル : C++ AMP アプリケーションのデバッグ | Microsoft Docs"
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
  - "デバッグ (C++ Accelerated Massive Parallelism)"
  - "C++ AMP、デバッグ"
  - "C++ Accelerated Massive Parallelism、デバッグ"
  - "デバッグ、C++ AMP"
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
caps.latest.revision: 35
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル : C++ AMP アプリケーションのデバッグ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、グラフィックスの演算処理装置 \(GPU\) を利用するには、C\+\+ Accelerated Massive Parallelism \(C\+\+ AMP\) を使用してアプリケーションをデバッグする方法について説明します。  これは整数の大きな配列をまとめるリダクション並列プログラムを使用します。  このチュートリアルでは、次の作業について説明します。  
  
-   GPU デバッガーを起動する。  
  
-   GPU をチェックすると、GPU スレッド ウィンドウに適用されます。  
  
-   並列スタック ウィンドウを使用して、同時に複数の GPU の呼び出し履歴を確認することです。  
  
-   複数のスレッドで一つの式の値を同時にチェック アウトする並列ウォッチ ウィンドウを使用します。  
  
-   GPU スレッドにフラグを設定して、固定し、分解し、グループ化します。  
  
-   コードの特定の位置にタイルのすべてのスレッドが実行されます。  
  
## 必須コンポーネント  
 このチュートリアルを開始する前に:  
  
-   [C\+\+ AMP の概要](../../parallel/amp/cpp-amp-overview.md) を読み取りました。  
  
-   行番号がテキスト エディターに表示されることを確認します。  詳細については、「[方法 : エディターで行番号を表示する](../Topic/How%20to:%20Display%20Line%20Numbers%20in%20the%20Editor.md)」を参照してください。  
  
-   ソフトウェア エミュレーターのデバッグをサポートするために [!INCLUDE[win8](../../build/includes/win8_md.md)] または [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] が実行されていることを確認します。  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### サンプル プロジェクトを作成するには  
  
1.  Visual Studio を起動します。  
  
2.  メニュー バーで **\[ファイル\]**、**\[新規\]**、**\[プロジェクト\]** の順にクリックします。  
  
3.  テンプレート ペインの **\[インストール済み\]** で、**\[Visual C\+\+\]** をクリックします。  
  
4.  **\[Win32 コンソール アプリケーション\]** をクリックします、**\[名前\]** ボックスの `AMPMapReduce` を入力し、**\[OK\]** ボタンをクリックします。  
  
5.  **\[次へ\]** ボタンをクリックします。  
  
6.  **\[プリコンパイル済みヘッダー\]** のチェック ボックスをオフに **\[完了\]** ボタンをクリックします。  
  
7.  **\[ソリューション エクスプローラー\]**、プロジェクトから削除 targetver.h、stdafx.h と stdafx.cpp で。  
  
8.  AMPMapReduce.cpp を開き、次のコードの内容を置き換えます。  
  
    ```cpp  
  
    // AMPMapReduce.cpp defines the entry point for the program.  
    // The program performs a parallel-sum reduction that computes the sum of an array of integers.   
  
    #include <stdio.h>  
    #include <tchar.h>  
    #include <amp.h>  
  
    const int BLOCK_DIM = 32;  
  
    using namespace concurrency;  
  
    void sum_kernel_tiled(tiled_index<BLOCK_DIM> t_idx, array<int, 1> &A, int stride_size) restrict(amp)  
    {  
        tile_static int localA[BLOCK_DIM];  
  
        index<1> globalIdx = t_idx.global * stride_size;  
        index<1> localIdx = t_idx.local;  
  
        localA[localIdx[0]] =  A[globalIdx];  
  
        t_idx.barrier.wait();  
  
        // Aggregate all elements in one tile into the first element.  
        for (int i = BLOCK_DIM / 2; i > 0; i /= 2)   
        {  
            if (localIdx[0] < i)   
            {  
  
                localA[localIdx[0]] += localA[localIdx[0] + i];  
            }  
  
            t_idx.barrier.wait();  
        }  
  
        if (localIdx[0] == 0)  
        {  
            A[globalIdx] = localA[0];  
        }  
    }  
  
    int size_after_padding(int n)  
    {  
        // The extent might have to be slightly bigger than num_stride to   
        // be evenly divisible by BLOCK_DIM. You can do this by padding with zeros.  
        // The calculation to do this is BLOCK_DIM * ceil(n / BLOCK_DIM)  
        return ((n - 1) / BLOCK_DIM + 1) * BLOCK_DIM;  
    }  
  
    int reduction_sum_gpu_kernel(array<int, 1> input)   
    {  
        int len = input.extent[0];  
  
        //Tree-based reduction control that uses the CPU.  
        for (int stride_size = 1; stride_size < len; stride_size *= BLOCK_DIM)   
        {  
            // Number of useful values in the array, given the current  
            // stride size.  
            int num_strides = len / stride_size;    
  
            extent<1> e(size_after_padding(num_strides));  
  
            // The sum kernel that uses the GPU.  
            parallel_for_each(extent<1>(e).tile<BLOCK_DIM>(), [&input, stride_size] (tiled_index<BLOCK_DIM> idx) restrict(amp)  
            {  
                sum_kernel_tiled(idx, input, stride_size);  
            });  
        }  
  
        array_view<int, 1> output = input.section(extent<1>(1));  
        return output[0];  
    }  
  
    int cpu_sum(const std::vector<int> &arr) {  
        int sum = 0;  
        for (size_t i = 0; i < arr.size(); i++) {  
            sum += arr[i];  
        }  
        return sum;  
    }  
  
    std::vector<int> rand_vector(unsigned int size) {  
        srand(2011);  
  
        std::vector<int> vec(size);  
        for (size_t i = 0; i < size; i++) {  
            vec[i] = rand();  
        }  
        return vec;  
    }  
  
    array<int, 1> vector_to_array(const std::vector<int> &vec) {  
        array<int, 1> arr(vec.size());  
        copy(vec.begin(), vec.end(), arr);  
        return arr;  
    }  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
        std::vector<int> vec = rand_vector(10000);  
        array<int, 1> arr = vector_to_array(vec);  
  
        int expected = cpu_sum(vec);  
        int actual = reduction_sum_gpu_kernel(arr);  
  
        bool passed = (expected == actual);  
        if (!passed) {  
            printf("Actual (GPU): %d, Expected (CPU): %d", actual, expected);  
        }  
        printf("sum: %s\n", passed ? "Passed!" : "Failed!");   
  
        getchar();  
  
        return 0;  
    }  
  
    ```  
  
9. メニュー バーで、**\[ファイル\]**、**\[すべてを保存\]** の順に選択します。  
  
10. **\[ソリューション エクスプローラー\]** で、**\[AMPMapReduce\]** のショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
11. **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]** では、**\[プリコンパイル済みヘッダー\]\[C\/C\+\+\]** をクリックします。  
  
12. **\[プリコンパイル済みヘッダー\]** のプロパティについては、**\[プリコンパイル済みヘッダーを使用しない\]** を選択します、**\[OK\]** ボタンをクリックします。  
  
13. メニュー バーの **\[ビルド\]**、**\[ソリューションのビルド\]** の順にクリックします。  
  
## CPU コードのデバッグ  
 この手順では、このアプリケーションの CPU コードが正しいことを確認するために、ローカル Windows デバッガーを使用します。  特に重要このアプリケーションの CPU コード セグメントは `reduction_sum_gpu_kernel` 関数の `for` ループです。  これは、GPU で実行するツリー ベースの並列リダクションを制御します。  
  
### CPU コードをデバッグするには  
  
1.  **\[ソリューション エクスプローラー\]** で、**\[AMPMapReduce\]** のショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
2.  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]** で、**\[デバッグ\]** をクリックします。  **\[ローカル Windows デバッガー\]** が **\[起動するデバッガー\]** の一覧で選択されていることを確認します。  
  
3.  コード エディターに戻ります。  
  
4.  次の図で示されているコード行にブレークポイントを設定します \(約 67 行 70\) を配置します。  
  
     ![CPU ブレークポイント](../../parallel/amp/media/campcpubreakpoints.png "CampCpuBreakpoints")  
CPU のブレークポイント  
  
5.  メニュー バーで、**\[デバッグ\]**、**\[デバッグ開始\]** の順に選択します。  
  
6.  **\[ローカル\]** ウィンドウには、70 行のブレークポイントに達するまで `stride_size` の値を確認します。  
  
7.  メニュー バーで、**\[デバッグ\]**、**\[デバッグの停止\]** の順に選択します。  
  
## GPU コードのデバッグ  
 ここでは `sum_kernel_tiled` 関数に含まれるコードである GPU コードをデバッグする方法について説明します。  GPU コードは、「ブロック」の整数の合計を並列に計算します。  
  
### GPU コードをデバッグするには  
  
1.  **\[ソリューション エクスプローラー\]** で、**\[AMPMapReduce\]** のショートカット メニューを開き、**\[プロパティ\]** をクリックします。  
  
2.  **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]** で、**\[デバッグ\]** をクリックします。  
  
3.  **\[起動するデバッガー\]** の一覧で、**\[ローカル Windows デバッガー\]** を選択します。  
  
4.  **\[デバッガーの種類\]** の一覧で、**\[GPU のみ\]** を選択します。  
  
5.  **\[OK\]** を選択します。  
  
6.  次の図に示すように、30 行にブレークポイントを設定します。  
  
     ![GPU ブレークポイント](../../parallel/amp/media/campgpubreakpoints.png "CampGpuBreakpoints")  
GPU のブレークポイント  
  
7.  メニュー バーで、**\[デバッグ\]**、**\[デバッグ開始\]** の順に選択します。  行の 67 および 70 CPU コードのブレークポイントは GPU のデバッグ中にこれらのコード行で CPU で実行されるため、実行されません。  
  
### GPU スレッド ウィンドウを使用する  
  
1.  GPU スレッド ウィンドウのメニュー バーで開くには、**\[ウィンドウ\]**、**\[GPU スレッド\]\[デバッグ\]** をクリックします。  
  
     GPU が表示される GPU スレッド ウィンドウでスレッドの状態を確認できます。  
  
2.  Visual Studio で GPU スレッド ウィンドウをドッキングしてください。  タイル、スレッド ボックスを表示するに **\[スレッドのスイッチを展開します。\]** ボタンをクリックします。  GPU を次の図に示すように、ウィンドウは、アクティブとブロックされた GPU スレッドの総数、されます。  
  
     ![4 つのアクティブ スレッドがある &#91;GPU スレッド&#93; ウィンドウ](../../parallel/amp/media/campc.png "CampC")  
GPU スレッド ウィンドウには  
  
     この演算に割り当てられている 313 枚のタイルがあります。  各タイルは 32 のスレッドが含まれます。  ローカル GPU のデバッグがソフトウェア エミュレーターで発生するため、4 回の実行中 GPU スレッドがあります。  " 4 個のスレッド"、手順を同時に実行し、次の手順に進みます。  
  
     GPU スレッド ウィンドウで、実行する 4 種類の GPU スレッドと 21 \(`t_idx.barrier.wait();`\) で定義されている [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md) のステートメントでブロックされた 28 の GPU スレッドが行になります。  32 の GPU スレッドはすべて最初のタイル、`tile[0]`に属しています。  矢印は、現在のスレッドが含まれている行を指します。  別のスレッドをに切り替えるには、次のメソッドの 1 つを使用する:  
  
    -   GPU スレッド ウィンドウにに切り替えるするスレッドの行でショートカット メニューを開き、**\[スレッドに切り替え\]** をクリックします。  行に複数のスレッドを表す場合、スレッドの座標に従って最初のスレッドをに切り替えます。  
  
    -   スレッドのタイルとスレッド値に対応するテキスト ボックスに入力し、**\[スレッドの切り替え\]** ボタンをクリックします。  
  
     呼び出し履歴ウィンドウには、現在の GPU スレッドの呼び出し履歴を表示します。  
  
### 並列スタック ウィンドウを使用します。  
  
1.  並列スタック ウィンドウのメニュー バーで開くには、**\[ウィンドウ\]**、**\[並列スタック\]\[デバッグ\]** をクリックします。  
  
     同時に複数の GPU スレッドのスタック フレームを検査するために、並列スタック ウィンドウを使用できます。  
  
2.  Visual Studio で並列スタック ウィンドウをドッキングしてください。  
  
3.  **\[スレッド\]** が左上隅の一覧で選択されていることを確認します。  次の図では、並列スタック ウィンドウが GPU スレッド ウィンドウで参照した、GPU スレッドの呼び出し履歴を集中するビューが表示されます。  
  
     ![4 つのアクティブ スレッドがある &#91;並列スタック&#93; ウィンドウ](../../parallel/amp/media/campd.png "CampD")  
\[並列スタック\] ウィンドウ  
  
     次に 32 のスレッドから `parallel_for_each` 関数呼び出しのラムダ ステートメントと並列リダクションが発生 `sum_kernel_tiled` 関数に `_kernel_stub` 順。32 のスレッドから 28 は [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md) のステートメントに他の 4 種類のスレッドが `sum_kernel_tiled` 関数に 30 行でアクティブなままのに対し、進行して、行 22 ブロックです。  
  
     並列スタック ウィンドウの豊富なデータヒントの GPU スレッド ウィンドウで使用できる GPU スレッドのプロパティを確認できます。  これを行うには、**\[sum\_kernel\_tiled\]** のスタック フレームにマウス ポインターを置きます。  次の図は、データヒントを示します。  
  
     ![&#91;並列スタック&#93; ウィンドウのデータヒント](../../parallel/amp/media/campe.png "CampE")  
GPU スレッドのデータヒント  
  
     並列スタック ウィンドウの詳細については、「[\[並列スタック\] ウィンドウの使用](../Topic/Using%20the%20Parallel%20Stacks%20Window.md)」を参照してください。  
  
### 並列ウォッチ ウィンドウを使用するには  
  
1.  並列ウォッチ ウィンドウのメニュー バーで開くには、**\[ウィンドウ\]**、**\[並列ウォッチ\]**、**\[並列ウォッチ 1\]\[デバッグ\]** をクリックします。  
  
     複数のスレッド間での式の値をチェックするために並列ウォッチ ウィンドウを使用できます。  
  
2.  Visual Studio の下に並列ウォッチ 1 ウィンドウをドッキングしてください。  並列ウォッチ ウィンドウのテーブルに 32 行があります。  それぞれが GPU スレッド ウィンドウと並列スタック ウィンドウの両方で示される GPU スレッドに対応します。  次に、値はすべて 32 の GPU スレッド間でチェックする式を入力できます。  
  
3.  **\[ウォッチ式の追加\]** の列ヘッダーを選択し、`localIdx`"と入力し、Enter キーを押します。  
  
4.  **\[ウォッチ式の追加\]** の列ヘッダーをもう一度選択し、`globalIdx`"と入力し、Enter キーを押します。  
  
5.  **\[ウォッチ式の追加\]** の列ヘッダーをもう一度選択し、`localA[localIdx[0]]`"と入力し、Enter キーを押します。  
  
     指定された式によって対応する列のヘッダーを選択して並べ替えることができます。  
  
     列を並べ替えるに **\[localA\[localIdx\[0\]\]\]** の列ヘッダーを選択します。  次の図は **\[localA\[localIdx\[0\]\]\]**で並べ替えた結果を示します。  
  
     ![結果が並べ替えられている &#91;並列ウォッチ&#93; ウィンドウ](../../parallel/amp/media/campf.png "CampF")  
 並べ替え結果  
  
     Excel にデータを Excel にエクスポート ボタンをクリックすると **\[Excel で開く\]** をクリックしますで並列ウォッチ ウィンドウの内容をエクスポートできます。  開発用コンピューターにインストールされている Excel がある場合は、コンテンツを含む Excel ワークシートが表示されます。  
  
6.  並列ウォッチ ウィンドウの右上隅に、ブール式を使用してコンテンツをフィルター処理するために使用できるフィルター コントロールがあります。  `localA[localIdx[0]] > 20000` をフィルター コントロールのテキスト ボックスに入力し、Enter キーを押します。  
  
     ウィンドウは、`localA[localIdx[0]]` 値が 20000 より大きいスレッドのみが含まれます。  コンテンツは、先ほど行った並べ替える操作である `localA[localIdx[0]]` の列で並べ替えられます。  
  
## GPU スレッドに対するフラグの設定  
 並列スタック ウィンドウで GPU スレッド ウィンドウ、並列ウォッチ ウィンドウ、またはそれらのデータヒントにフラグを設定することによって特定の GPU スレッドをマークできます。  GPU スレッド ウィンドウの行に複数のスレッドが含まれる場合は、行が行に含まれるすべてのスレッドに対するフラグの設定フラグを設定します。  
  
### GPU スレッドにフラグを設定するには  
  
1.  並列ウォッチ 1 ウィンドウに **\[\[スレッド\]\]** の列ヘッダーを並べ替えにタイルのインデックスにし、インデックスに実行します。  
  
2.  次のバリアと 4 種類のスレッドを発生させるメニュー バーで、**\[続行\]\[デバッグ\]** をクリックします \(AMPMapReduce.cpp の行 32 定義\) の進行状況は、アクティブ。  
  
3.  現在アクティブな" 4 個のスレッド"を含む行の左側のフラグのシンボルをクリックします。  
  
     次の図は、GPU スレッド ウィンドウに 4 個のアクティブなフラグが設定されたスレッドを示しています。  
  
     ![スレッドにフラグが設定されている &#91;GPU スレッド&#93; ウィンドウ](../../parallel/amp/media/campg.png "CampG")  
GPU のアクティブなスレッドはウィンドウとスレッド  
  
     並列スタック ウィンドウの並列ウォッチ ウィンドウとデータヒントは、フラグが設定されたスレッドを示しています。  
  
4.  、フラグを付けた" 4 個のスレッド"に重点を置く場合、GPU スレッド、並列化のウォッチ ウィンドウと並列スタック ウィンドウ、フラグが設定されたスレッドのみを表示することもできます。  
  
     次に、フラグが設定されたウィンドウのいずれかまたは **\[デバッグの場所\]** ツール バーのボタンをクリックします。  次の図では、フラグが設定 **\[デバッグの場所\]** ツール バーのボタンだけが表示されます。  
  
     ![&#91;フラグが設定されたもののみを表示&#93; アイコンがある &#91;デバッグの場所&#93; ツール バー](../../parallel/amp/media/camph.png "CampH")  
フラグが設定されたもののみを表示ボタンを表示します。  
  
     これで、GPU スレッド、並列ウォッチ ウィンドウと並列スタック ウィンドウでは、フラグが設定されたスレッドのみが表示されます。  
  
## 固定し、GPU スレッドの分解  
 \(中断\) 固定し、再開\) \(GPU スレッド ウィンドウまたは並列ウォッチ ウィンドウから GPU スレッドを分解できます。  同じ方法で CPU のスレッドを固定し、分解できます; 詳細については、「[方法 : \[スレッド\] ウィンドウを使用する](../Topic/How%20to:%20Use%20the%20Threads%20Window.md)」を参照してください。  
  
### GPU スレッドを分解する固定し、  
  
1.  すべてのスレッドを表示するに **\[フラグが設定されたのみ表示します。\]** ボタンをクリックします。  
  
2.  メニュー バーで、**\[続行\]\[デバッグ\]** をクリックします。  
  
3.  実行中の行のショートカット メニューを開き、**\[凍結\]** をクリックします。  
  
     GPU スレッド ウィンドウを次の図に、4 種類のすべてのスレッドが固定されることを示します。  
  
     ![凍結されたスレッドを示す &#91;GPU スレッド&#93; ウィンドウ](../../parallel/amp/media/campk.png "CampK")  
GPU の固定されたスレッド ウィンドウにはスレッド  
  
     同様に、並列ウォッチ ウィンドウは 4 個のすべてのスレッドが固定されることを示します。  
  
4.  メニュー バーで、次の 4 種類の GPU スレッドがバリアを含む行 22 進行して、行 30 にブレークポイントに到達すると、**\[続行\]\[デバッグ\]** をクリックします。  GPU スレッド ウィンドウは 4 個の前に固定されたスレッドで固定し、アクティブ状態になることを示します。  
  
5.  メニュー バーで、**\[続行\]\[デバッグ\]** をクリックします。  
  
6.  並列ウォッチ ウィンドウから、または複数の各 GPU スレッドを分解できます。  
  
### GPU スレッドをグループ化するには  
  
1.  **\[GPU スレッド\]** ウィンドウのスレッドの 1 種類のショートカット メニューで、**\[アドレス\]\[グループ化\]** をクリックします。  
  
     GPU スレッド ウィンドウでスレッドにアドレスにグループ化されます。  アドレスはスレッドの各グループにある構成の手順に対応します。24 のスレッドは 22 行 [tile\_barrier::wait メソッド](../Topic/tile_barrier::wait%20Method.md) が実行された位置にあります。12 のスレッドは 32 行バリアの手順です。  これらのスレッドの 4 つがフラグが設定されます。  " 8 個のスレッド"は 30 行ブレークポイントにあります。  これらのスレッドの 4 つが固定されます。  次の図は、GPU スレッド ウィンドウでグループ化されたスレッドを示しています。  
  
     ![スレッドがアドレスごとにグループ化されている &#91;GPU スレッド&#93; ウィンドウ](../../parallel/amp/media/campl.png "CampL")  
GPU のグループ化されたスレッドはウィンドウとスレッド  
  
2.  、並列ウォッチ ウィンドウのデータ グリッドのショートカット メニューを開いて、次のスレッドをどのようにグループ化するか、対応するメニュー項目を選択する **\[グループ化\]** 操作を実行 **\[グループ化\]** をクリックします場合があります。  
  
## コードの特定の位置にすべてのスレッドを実行できます。  
 **\[現在の Tile をカーソル行の前まで実行\]** を使用してカーソルを含む行に特定のタイルのすべてのスレッドを実行します。  
  
### すべてのスレッドをカーソルで示された位置から実行します。  
  
1.  固定されたスレッドのショートカット メニューで、**\[凍結解除\]** をクリックします。  
  
2.  コード エディターで、30 行にカーソルを置きます。  
  
3.  コード エディターのショートカット メニューを開き、**\[現在の Tile をカーソル行の前まで実行\]** をクリックします。  
  
     行の 21 バリアにブロックされた 24 のスレッドは 32 をキューに先に進んでいます。  これは **\[GPU スレッド\]** のウィンドウに表示されます。  
  
## 参照  
 [C\+\+ AMP の概要](../../parallel/amp/cpp-amp-overview.md)   
 [GPU コードのデバッグ](../Topic/Debugging%20GPU%20Code.md)   
 [方法: GPU スレッド ウィンドウを使用する](../Topic/How%20to:%20Use%20the%20GPU%20Threads%20Window.md)   
 [方法: 並列ウォッチ ウィンドウを使用する](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md)   
 [同時実行ビジュアライザーで C\+\+ AMP コードの分析](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)