---
title: "テクニカル ノート 29: 分割ウィンドウ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.windows.splitter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "分割ウィンドウ, 分割ウィンドウの概要"
  - "TN029"
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 29: 分割ウィンドウ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、ウィンドウの分割を提供し、他のペインがウィンドウのサイズ変更を管理する MFC [CSplitterWnd クラス](../mfc/reference/csplitterwnd-class.md)について説明します。  
  
## 分割線のスタイル  
 `CSplitterWnd` は、分割ウィンドウの 2 種類のスタイルをサポートします。  
  
 「静的分割では」、分割ウィンドウが作成されたときにペインを作成します。  ペインの順序と数は変化しません。  分割バーがペインのサイズを変更するために使用されます。  各ペインの異なるビュー クラスを表示するために、このスタイルを使用できます。  Visual C\+\+ のグラフィックス エディターおよび Windows のファイル マネージャーは、この分割ウィンドウ スタイルを使用するプログラムの例です。  分割ウィンドウのこのスタイルは分割ボックスを使用しません。  
  
 「動的な分割では」、add ペインは、ユーザーや、新しい分割ビューで分割すると同時に作成され、破棄されます。  この分割は一つのビューからユーザーが分割線を開始できるように開始し、分割ボックスが用意されています。  分割ウィンドウが動的にビューが 1 方向に分割されている場合、新しいビュー オブジェクトを作成します。  この新しいビュー オブジェクトは、新しいペインを表します。  ビューが 2 方向でキーボード インターフェイスを使用して、分割されている場合、分割ウィンドウは、3 種類の新しいペインの 3 種類の新しいビュー オブジェクトを作成します。  分割がアクティブな間、Windows はペイン間の分割バーとして分割ボックスが表示されます。  Windows は、分割ウィンドウ自体が破棄されるまでユーザーが分割線を削除し、元のビューはそのままと追加ビュー オブジェクトを破棄します。  Microsoft Excel と Microsoft Word は動的な分割のスタイルを使用するアプリケーションの例です。  
  
 分割ウィンドウの種類のいずれかを作成するときに分割が管理する列と行の最大数を指定する必要があります。  静的分割はすべての行と列のサイズにペインを作成します。  動的な分割は `CSplitterWnd` が作成されるときに、最初のペインが作成されます。  
  
 、静的分割に指定できるペインの最大数は 16 列で 16 行です。  推奨構成は、次の操作:  
  
-   1 行 2 列: X 通常、ペインと  
  
-   2 行 1 列: X 通常、ペインと  
  
-   2 行 2 列: X 通常と同じようなペイン  
  
 、動的な分割に指定できるペインの最大数は 2 列を基準にして 2 行です。  推奨構成は、次の操作:  
  
-   1 行 2 列: X 役立つデータ用  
  
-   2 行 1 列: X また、他のデータ  
  
-   2 行 2 列: X Grid またはテーブルのデータをづけました方向  
  
## 分割線の例  
 MFC のサンプル プログラムの多くは、分割ウィンドウを直接的または間接的に使用します。  MFC の一般的なサンプル [VIEWEX](../top/visual-cpp-samples.md) を含む静的分割の使用を分割分割を配置する方法について説明します。  
  
 、分割ウィンドウを含む新しいマルチ ドキュメント インターフェイス \(MDI\) の子フレーム ウィンドウ クラスを作成するために ClassWizard を使用できます。  分割ウィンドウの詳細については、「[複数のドキュメントの種類、ビュー、およびフレーム ウィンドウ](../mfc/multiple-document-types-views-and-frame-windows.md)」を参照してください。  
  
## 実装によって使用される用語  
 分割ウィンドウに特定の用語の一覧を次に示します。:  
  
 `CSplitterWnd`:  
 行内のすべてのペインまたは列の間で共有されるスクロール バー ペインと分割線のコントロールを表示するウィンドウ。  インデックス番号が 0 から始まる数を複数の行と列を指定します \(最初のペインは行と列 \= 0 \= 0 です。  
  
 ペイン:  
 `CSplitterWnd` が管理するアプリケーション固有のウィンドウ。  ペインは、通常 [CView クラス](../Topic/CView%20Class.md)から派生されるが、適切な子ウィンドウ ID を持つ [CWnd](../Topic/CWnd%20Class.md) オブジェクトでもかまいませんオブジェクト  
  
 `CView`を使用するように `CWnd`\-派生オブジェクトを使用するには、`CreateView` 関数へのオブジェクトの `RUNTIME_CLASS` を渡します。\-派生クラスです。  クラスは、フレームワークが実行時に動的生成を使用するため `DECLARE_DYNCREATE` と `IMPLEMENT_DYNCREATE` を使用する必要があります。  `CView` クラスに固有の `CSplitterWnd` に多くのコードがあるが、[CObject::IsKindOf](../Topic/CObject::IsKindOf.md) はこれらの操作が実行される前に、常に使用されます。  
  
 分割バー:  
 ペインの行と列の間にあるコントロール。  ペインの行または列のサイズを変更するために使用する可能性があります。  
  
 分割ボックス:  
 ペインの新しい行または列を作成するために使用できる動的な `CSplitterWnd` のコントロール。  これは垂直スクロール バーまたは水平スクロール バーの左側の上にあります。  
  
 分割線の交差部分:  
 垂直方向の分割バーと水平方向の分割バーの交差部分。  ペインの行と列のサイズを同時に変更するためにドラッグすることもできます。  
  
## 共有スクロール バー  
 `CSplitterWnd` クラスは、共有スクロール バーをサポートします。  これらのスクロール バー コントロールは `CSplitterWnd` の子で、分割のペインで共有されます。  
  
 たとえば、行 1 つ X で `CSplitterWnd`を作成するときに 2 列のウィンドウ、WS\_VSCROLL を指定できます。  Windows は 2 個のペイン間で共有される特別なスクロール バーを作成します。  
  
```  
[      ][      ][^]  
[pane00][pane01][|]  
[      ][      ][v]  
```  
  
 ユーザーがスクロール バーを移動すると、`WM_VSCROLL` メッセージは両方のビューに送信されます。  一方のビューがスクロール バーの位置を設定すると、共有スクロール バーが設定されます。  
  
 共有スクロール バーに似たビュー オブジェクトが最も有用であることに注意してください。  二つの異なる型のビューを混在させると、スクロール位置を調整するために特別なコードを記述する必要があります。  `CView`\-場合 `CWnd` のスクロール バーの API を使用する派生クラスは、共有スクロール バーに委任します。  `CScrollView` の実装は共有スクロール バーをサポートする `CView` クラスの 1 例です。  `CView`の非コントロールのスクロール バーには、標準の実装 \(\) を使用する `CEditView`クラスから派生されないクラスは `CSplitterWnd`の共有スクロール バー機能は使用しません。  
  
## 最小サイズ  
 各行の最小の行の高さがあり、各列に対して最小限の列の幅を示します。  ペインが完全な詳細に表示するには、小さいので、このことを保証します。  
  
 静的な分割ウィンドウの場合、最初の最小行数の列の高さと幅は 0 です。  動的な分割ウィンドウでは、最初の最小行の高さと列の幅は `CSplitterWnd::Create` 関数の `sizeMin` パラメーターによって設定されます。  
  
 [CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) と [CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) 関数を使用してこれらの最小サイズを変更できます。  
  
## 最適なサイズと実際  
 分割ウィンドウのペインのレイアウトが、それを含むフレームのサイズによって決まります。  ユーザーを含むフレームのサイズを変更すると、`CSplitterWnd` は、有効収まるようにペインの位置、サイズを変更します。  
  
 ユーザーが手動で行の高さと幅の列のサイズを設定できます。また、プログラムで `CSplitterWnd` クラスを使用して最適なサイズを設定できます。  実際のサイズは理想より小さな場合も大きな場合があります。  Windows は、最適なサイズを表示する十分な領域がないか、分割ウィンドウの右端または下端に大量の空の領域がある場合は、実際のサイズを調整します。  
  
## カスタム コントロール  
 カスタマイズした動作とカスタマイズされたインターフェイスを提供する複数の関数をオーバーライドできます。  分割ウィンドウのさまざまなグラフィカル コンポーネントに別のイメージを作成するには、この初期設定をオーバーライドできます。  
  
-   `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`  
  
-   `virtual void OnInvertTracker(const CRect& rect);`  
  
 共有スクロール バーを作成するには、この関数を呼び出します。  スクロール バーのすぐ横に余分なコントロールを作成するために、この関数をオーバーライドできます。  
  
-   `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`  
  
 これらの関数は動的な分割ウィンドウ ロジックを実装します。  高度な分割ロジックを提供するこれらをオーバーライドできます。  
  
-   `virtual void DeleteView(int row, int col);`  
  
-   `virtual BOOL SplitRow(int cyBefore);`  
  
-   `virtual BOOL SplitColumn(int cxBefore);`  
  
-   `virtual void DeleteRow(int rowDelete);`  
  
-   `virtual void DeleteColumn(int colDelete);`  
  
## CView の機能  
 `CView` クラスは `CSplitterWnd` に実装に代行させる次の高度なコマンドを使用します。  これらのコマンドが仮想であるため、`CView` の標準実装は `CSplitterWnd` の実装がリンクする必要はありません。  `CView`、`CSplitterWnd`を使用しますが、アプリケーションでは、`CSplitterWnd` の実装はアプリケーションにリンクされません。  
  
 `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`  
 ID\_NEXT\_PANE または ID\_PREV\_PANE が現在有効かどうかを確認します。  
  
 `virtual void ActivateNext(BOOL bPrev = FALSE);`  
 Next Pane」または「Previous Pane」コマンドを実行します。  
  
 `virtual BOOL DoKeyboardSplit();`  
 キーボード分割コマンドを、つまり「分割する」ウィンドウ実行します。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)