---
title: "CSplitterWnd クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSplitterWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitterWnd クラス"
  - "動的分割ウィンドウ"
  - "マルチ ビュー"
  - "分割ウィンドウ"
  - "静的な分割ウィンドウ"
  - "ビュー, 複数 (フレームあたり)"
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitterWnd クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

分割ウィンドウの機能が用意されています。分割ウィンドウとは複数のペインを持つウィンドウです。  
  
## 構文  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSplitterWnd::CSplitterWnd](../Topic/CSplitterWnd::CSplitterWnd.md)|`CSplitterWnd` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSplitterWnd::ActivateNext](../Topic/CSplitterWnd::ActivateNext.md)|Next Pane コマンドまたは Previous Pane コマンドを実行します。|  
|[CSplitterWnd::CanActivateNext](../Topic/CSplitterWnd::CanActivateNext.md)|Next Pane コマンドまたは Previous Pane コマンドが現在実行できるかどうかを調べます。|  
|[CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)|動的分割ウィンドウを作成し、`CSplitterWnd` オブジェクトに関連付けます。|  
|[CSplitterWnd::CreateScrollBarCtrl](../Topic/CSplitterWnd::CreateScrollBarCtrl.md)|共有スクロール バーを作成します。|  
|[CSplitterWnd::CreateStatic](../Topic/CSplitterWnd::CreateStatic.md)|静的分割ウィンドウを作成し、`CSplitterWnd` オブジェクトに関連付けます。|  
|[CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)|分割ウィンドウのペインを作成します。|  
|[CSplitterWnd::DeleteColumn](../Topic/CSplitterWnd::DeleteColumn.md)|分割ウィンドウから列を削除します。|  
|[CSplitterWnd::DeleteRow](../Topic/CSplitterWnd::DeleteRow.md)|分割ウィンドウから行を削除します。|  
|[CSplitterWnd::DeleteView](../Topic/CSplitterWnd::DeleteView.md)|分割ウィンドウのビューを削除します。|  
|[CSplitterWnd::DoKeyboardSplit](../Topic/CSplitterWnd::DoKeyboardSplit.md)|キーボード分割コマンドを実行します。通常、"ウィンドウ分割" キーです。|  
|[CSplitterWnd::DoScroll](../Topic/CSplitterWnd::DoScroll.md)|分割ウィンドウの同期スクロールを実行します。|  
|[CSplitterWnd::DoScrollBy](../Topic/CSplitterWnd::DoScrollBy.md)|指定したピクセル数分、分割ウィンドウをスクロールします。|  
|[CSplitterWnd::GetActivePane](../Topic/CSplitterWnd::GetActivePane.md)|フレーム内でフォーカスを持つビュー、またはアクティブなビューのアクティブなペインを調べます。|  
|[CSplitterWnd::GetColumnCount](../Topic/CSplitterWnd::GetColumnCount.md)|現在のペインの列数を返します。|  
|[CSplitterWnd::GetColumnInfo](../Topic/CSplitterWnd::GetColumnInfo.md)|指定された列の情報を返します。|  
|[CSplitterWnd::GetPane](../Topic/CSplitterWnd::GetPane.md)|指定された行、列のペインを返します。|  
|[CSplitterWnd::GetRowCount](../Topic/CSplitterWnd::GetRowCount.md)|現在のペインの行数を返します。|  
|[CSplitterWnd::GetRowInfo](../Topic/CSplitterWnd::GetRowInfo.md)|指定された行の情報を返します。|  
|[CSplitterWnd::GetScrollStyle](../Topic/CSplitterWnd::GetScrollStyle.md)|共有されているスクロール バーのスタイルを返します。|  
|[CSplitterWnd::IdFromRowCol](../Topic/CSplitterWnd::IdFromRowCol.md)|指定された行、列のペインの子ウィンドウ ID を返します。|  
|[CSplitterWnd::IsChildPane](../Topic/CSplitterWnd::IsChildPane.md)|ウィンドウが、現在、分割ウィンドウの子ペインかどうかを調べます。|  
|[CSplitterWnd::IsTracking](../Topic/CSplitterWnd::IsTracking.md)|現在、分割バーが動いているかを取得します。|  
|[CSplitterWnd::RecalcLayout](../Topic/CSplitterWnd::RecalcLayout.md)|行や列のサイズを変更後、分割ウィンドウを再表示します。|  
|[CSplitterWnd::SetActivePane](../Topic/CSplitterWnd::SetActivePane.md)|フレーム内でアクティブになるペインを設定します。|  
|[CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md)|指定された列の情報を設定します。|  
|[CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md)|指定された行の情報を設定します。|  
|[CSplitterWnd::SetScrollStyle](../Topic/CSplitterWnd::SetScrollStyle.md)|分割ウィンドウの共有スクロール バーをサポートするために新しいスクロール バー スタイルを指定します。|  
|[CSplitterWnd::SplitColumn](../Topic/CSplitterWnd::SplitColumn.md)|フレーム ウィンドウを垂直に分割する位置を示します。|  
|[CSplitterWnd::SplitRow](../Topic/CSplitterWnd::SplitRow.md)|フレーム ウィンドウを水平に分割する位置を示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSplitterWnd::OnDraw](../Topic/CSplitterWnd::OnDraw.md)|分割ウィンドウを描画するために、フレームワークによって呼び出されます。|  
|[CSplitterWnd::OnDrawSplitter](../Topic/CSplitterWnd::OnDrawSplitter.md)|分割ウィンドウのイメージを表示します。|  
|[CSplitterWnd::OnInvertTracker](../Topic/CSplitterWnd::OnInvertTracker.md)|分割ウィンドウのイメージをフレーム ウィンドウと同じサイズと形状になるように表示します。|  
  
## 解説  
 ウィンドウは、通常 [&#91;CW2CT&#93;](../Topic/CView%20Class.md)から派生したアプリケーション固有のオブジェクトですが適切な子ウィンドウ ID を持つ [CWnd](../Topic/CWnd%20Class.md) では任意のオブジェクトを指定できます。  
  
 `CSplitterWnd` のオブジェクトは、通常、親 [CFrameWnd](../../mfc/reference/cframewnd-class.md) か [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) のオブジェクトに埋め込まれます。  次の手順を使用して `CSplitterWnd` のオブジェクトを作成する:  
  
1.  親フレームの `CSplitterWnd` のメンバー変数を埋め込みます。  
  
2.  親フレームの [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md) のメンバー関数をオーバーライドします。  
  
3.  オーバーライドされた `OnCreateClient`では、`CSplitterWnd`の [&#91;作成&#93;](../Topic/CSplitterWnd::Create.md) または [CreateStatic](../Topic/CSplitterWnd::CreateStatic.md) のメンバー関数を呼び出します。  
  
 動的分割ウィンドウを作成するに **\[作成\]** のメンバー関数を呼び出します。  動的分割ウィンドウは、通常、同じドキュメントの一部の個別のペインまたはビューを作成し、スクロールするために使用されます。  フレームワークは、自動的に分割の最初のペインを作成します; フレームワークは、ユーザーが分割ウィンドウ コントロールを操作するときに、サイズ変更作成し、他のウィンドウを破棄します。  
  
 **\[作成\]**を呼び出すと、ウィンドウが完全に表示するには小さすぎるか、最小限の行の高さと幅列を指定します。  **\[作成\]**を呼び出した後、[SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) と [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) のメンバー関数を呼び出して、これらの最小を調整できます。  
  
 また、行の列および「最適な高さ」の「理想的な」幅を設定するに `SetColumnInfo` と `SetRowInfo` のメンバー関数を使用します。  フレームワークは、分割ウィンドウを表示するには、最初に親フレーム、分割ウィンドウを表示します。  フレームワークは、左上から分割ウィンドウのクライアント領域の右下隅に機能する最適なサイズに従って、ウィンドウの列と行のレイアウトを設定します。  
  
 動的分割ウィンドウのすべてのウィンドウは、同じクラスである必要があります。  動的分割ウィンドウをサポートする一般的なアプリケーションは、Microsoft Word および Microsoft Excel が含まれます。  
  
 静的な分割ウィンドウの作成に `CreateStatic` のメンバー関数を使用します。  ユーザーは、注文数または静的な分割ウィンドウのペインのサイズは変更できません。  
  
 静的な分割を作成すると、すべての静的な分割ウィンドウを作成する必要があります。  親フレームの `OnCreateClient` のメンバー関数が戻る前、またはフレームワークを作成するために正しく表示できません\]ウィンドウを確認する前にすべてのウィンドウ。  
  
 `CreateStatic` のメンバー関数は自動的に 0 の最小の行の高さと幅列の静的な分割を初期化します。  **\[作成\]**を呼び出した後、[SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) と [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) のメンバーを呼び出すことで、これらの関数を調整します。  また、目的の最適なウィンドウのサイズを示すために `CreateStatic` を呼び出した後 `SetColumnInfo` と `SetRowInfo` を使用します。  
  
 静的な分割の個別のウィンドウは、通常、異なるクラスに属しています。  静的な分割ウィンドウの例については、グラフィックス エディターおよび Windows のファイル マネージャーを参照してください。  
  
 分割ウィンドウは、スクロール バーをサポートします \(ウィンドウが表示される場合もあります\) スクロール バーとは。  これらのスクロール バーは `CSplitterWnd` のオブジェクトの子で、ウィンドウで共有されます。  
  
 分割ウィンドウを作成するときにこれらの特殊なスクロール バーを作成します。  たとえば、`CSplitterWnd` 1 行がある、2 列 **WS\_VSCROLL** のスタイルは 2\]ウィンドウで共有される垂直スクロール バーが表示されます。  ユーザーがスクロール バーを実行すると、`WM_VSCROLL` のメッセージは、両方のウィンドウに送られます。  ウィンドウがスクロール バーの位置を設定すると、共有スクロール バーが設定されます。  
  
 分割ウィンドウの詳細については、" "を参照してください:  
  
-   [テクニカル ノート 29](../../mfc/tn029-splitter-windows.md)  
  
-   サポート技術情報の文書 Q262024: " HOWTO: CSplitterWnd の子として CPropertySheet を使用します。  
  
 動的分割ウィンドウを作成する方法の詳細については、" "を参照してください:  
  
-   MFC のサンプル [&#91;フリーハンド&#93;](../../top/visual-cpp-samples.md)  
  
-   MFC のサンプル [VIEWEX](../../top/visual-cpp-samples.md)。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CSplitterWnd`  
  
## 必要条件  
 **Header:** afxext.h  
  
## 参照  
 [MFC VIEWEX サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)