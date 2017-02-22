---
title: "描画コードの変更 (ATL チュートリアル、パート 4) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MIN_CRT マクロ"
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 描画コードの変更 (ATL チュートリアル、パート 4)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

既定では、コントロールの描画コードは、2 乗と **PolyCtl**テキストを表示します。  この手順では、よりも注意事項を表示するようにコードを変更します。  次のタスクは複雑です:  
  
-   ヘッダー ファイルの変更  
  
-   `OnDraw` 関数の変更  
  
-   メソッドを多角形の点が計算するコードの追加  
  
-   塗りつぶしの色の初期化  
  
## ヘッダー ファイルの変更  
 数値のサポートを追加しますが、位置を格納する配列を作成して計算される多角形の点を使用すると、`cos`作用、および `sin`。  
  
#### ヘッダー ファイルを変更するには  
  
1.  PolyCtl.h の上に行 `#include <math.h>` を追加します。  ファイルの先頭に、次のようになります。:  
  
     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]  
  
2.  多角形の点が計算されている場合、`POINT`型の配列に格納されるので、PolyCtl.h の `m_nSides` の定義の後に配列を追加します:  
  
     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_2.h)]  
  
## OnDraw のメソッドの変更  
 これで PolyCtl.h の `OnDraw` のメソッドを変更する必要があります。  追加するコードの多角形を描画するために、`Ellipse` と `Polygon` の Win32 API 関数の実際の描画を実行するために呼び出す新しいブラシ、ペンを作成します。  
  
#### OnDraw 関数を変更するには  
  
1.  次のコードで PolyCtl.h の `OnDraw` の既存のメソッドを置換します:  
  
     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]  
  
## メソッドを多角形の点が計算するコードの追加  
 多角形の周囲を構成する点の座標を計算する `CalcPoints`というメソッドを追加します。  これらの数は、関数に渡された RECT の変数に基づいています。  
  
#### CalcPoints のメソッドを追加するには  
  
1.  PolyCtl.h の `CPolyCtl` クラスの `IPolyCtl` のパブリック セクションに `CalcPoints` の宣言を追加します:  
  
     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_4.h)]  
  
     `CPolyCtl` のクラスのパブリック セクションの最後の部分は次のようになります。:  
  
     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_5.h)]  
  
2.  PolyCtl.cpp の最後に `CalcPoints` のこの関数の実装を追加します:  
  
     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]  
  
## 塗りつぶしの色の初期化  
 既定の色 `m_clrFillColor` を初期化します。  
  
#### 塗りつぶしの色を初期化します。  
  
1.  PolyCtl.h の `CPolyCtl` のコンストラクターに次の行を追加して、既定の色ように、緑の使用:  
  
     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_7.h)]  
  
 コンストラクターは次のようになります。:  
  
 [!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_8.h)]  
  
## コントロールのビルドとテスト  
 コントロールをビルドし直します。  まだ開いている場合は閉じてから **\[効果あり\]** の **\[多角形のビルド\]** メニューのをクリックし、を PolyCtl.htm ファイルに確認します。  ActiveX コントロール テスト コンテナーは PolyCtl.htm ページからコントロール、今回の使用をもう一度表示できます。  
  
#### ActiveX コントロール テスト コンテナーを使用します。  
  
1.  ActiveX コントロール テスト コンテナーを作成、開始します。  詳細については、[TSTCON サンプル: ActiveX コントロール テスト コンテナー](../top/visual-cpp-samples.md)を参照してください。  
  
2.  テスト コンテナーで、**\[編集\]** のメニューのをクリック **Insert New Control**。  
  
3.  `PolyCtl Class`と呼ばれる、をクリック **OK**、コントロールを検索します。  Circle 内の緑の三角形が表示されます。  
  
 次の手順に従って、辺の数を変更してみてください。  テスト コンテナー内からデュアル インターフェイスのプロパティを変更するには、**Invoke Methods**を使用します。  
  
#### テスト コンテナー内のコントロールのプロパティを変更するには  
  
1.  テスト コンテナーで、**コントロール** の **Invoke Methods** メニューのをクリックします。  
  
     **\[メソッドを呼び出します\]** のダイアログ ボックスが表示されます。  
  
2.  **\[メソッド名\]** のドロップダウン リスト ボックスで **Sides** のプロパティの **PropPut** のバージョンを選択します。  
  
3.  **\[パラメーター値\]** ボックスの `5` を入力し、**\[値の設定\]**をクリックし、**\[呼び出し\]**をクリックします。  
  
 コントロールが変更されないことに注意してください。  `m_nSides` の変数を設定して、辺の数を内部的に変更されますが、これにより、コントロールは再描画しませんいません。  別のアプリケーションに切り替えて、テスト コンテナーに戻った場合、コントロールは、正しい数の再描画およびがあることがわかります。  
  
 この問題を解決するには、`IViewObjectExImpl`で定義されている `FireViewChange` 関数の呼び出しを設定した後、追加の数。  コントロールが独自のウィンドウで実行されている場合、`FireViewChange` 直接 `InvalidateRect` のメソッドを呼び出します。  コントロールがウィンドウなし実行する場合は `InvalidateRect` のメソッドはコンテナーのインターフェイスで呼び出されます。  これは、それ自体を再描画するためにコントロールが強制されます。  
  
#### 呼び出しを FireViewChange に追加するには  
  
1.  `put_Sides` のメソッドに `FireViewChange` に呼び出しを追加して、PolyCtl.cpp を更新します。  完了したら、`put_Sides` のメソッドは次のようになります。:  
  
     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]  
  
 `FireViewChange`を追加したら、リビルドが ActiveX コントロール テスト コンテナーでコントロールをもう一度試します。  辺の数を変更し、`Invoke`をクリックすると、今度コントロールをすぐに確認する必要があります。  
  
 次の手順では、イベントを追加します。  
  
 [手順 3 に戻します](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [手順 5 ~](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## 参照  
 [チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)   
 [テスト コンテナーでのプロパティとイベントのテスト](../mfc/testing-properties-and-events-with-test-container.md)