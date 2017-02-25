---
title: "CScrollView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CScrollView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CScrollView クラス"
  - "スクロール可能なビュー"
  - "ビュー, スクロール"
ms.assetid: 4ba16dac-1acb-4be0-bb55-5fb695b6948d
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CScrollView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スクロール機能を [&#91;CW2CT&#93;](../Topic/CView%20Class.md)。  
  
## 構文  
  
```  
class CScrollView : public CView  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CScrollView::CScrollView](../Topic/CScrollView::CScrollView.md)|`CScrollView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CScrollView::CheckScrollBars](../Topic/CScrollView::CheckScrollBars.md)|スクロール ビューに水平および垂直スクロール バーがあるかどうかを示します。|  
|[CScrollView::FillOutsideRect](../Topic/CScrollView::FillOutsideRect.md)|スクロール領域外のビューで領域を塗りつぶします。|  
|[CScrollView::GetDeviceScrollPosition](../Topic/CScrollView::GetDeviceScrollPosition.md)|デバイス単位の現在のスクロール位置を取得します。|  
|[CScrollView::GetDeviceScrollSizes](../Topic/CScrollView::GetDeviceScrollSizes.md)|スクロール可能なビューの現在のマップ モード、合計サイズ、および線とページ サイズ取得します。  サイズは、デバイス単位にあります。|  
|[CScrollView::GetScrollPosition](../Topic/CScrollView::GetScrollPosition.md)|論理単位の現在のスクロール位置を取得します。|  
|[CScrollView::GetTotalSize](../Topic/CScrollView::GetTotalSize.md)|論理単位のスクロール ビューの合計サイズを取得します。|  
|[CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)|ビューのサイズをフレームのサイズを決定します。|  
|[CScrollView::ScrollToPosition](../Topic/CScrollView::ScrollToPosition.md)|論理単位で指定された点までビューをスクロールします。|  
|[CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md)|スケールに適合するモードにスクロール ビューを入力します。|  
|[CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md)|スクロール ビューのマップ モード、合計サイズを設定し、水平方向と垂直方向のスクロールになります。|  
  
## 解説  
 [OnHScroll](../Topic/CWnd::OnHScroll.md) と [OnVScroll](../Topic/CWnd::OnVScroll.md) のメッセージ マップされたメンバーをオーバーライドして `CView` から派生したすべてのクラスで独自関数標準のスクロールを処理できます。  ただし、`CScrollView` は `CView` の機能に次の機能を追加します:  
  
-   また、ウィンドウ、およびビューポートのサイズとマップ モードを管理します。  
  
-   これはスクロール バー メッセージに応じて自動的にスクロールします。  
  
-   これは、キーボード、マウス、または IntelliMouse スクロール ホイールによるメッセージに応じて自動的にスクロールします。  
  
 キーボードからメッセージに応じて自動的にスクロールする場合、VK\_DOWN、VK\_PREV と呼び出し [SetScrollPos](http://msdn.microsoft.com/library/windows/desktop/bb787597)の WM\_KEYDOWN メッセージとテストを追加します。  
  
 マウスのスクロール ホイールの関数を独自 [OnMouseWheel](../Topic/CWnd::OnMouseWheel.md) と [OnRegisteredMouseWheel](../Topic/CWnd::OnRegisteredMouseWheel.md) のメッセージ マップされたメンバーをオーバーライドして処理できます。  これらは `CScrollView`用に応じて、これらのメンバー関数は [WM\_MOUSEWHEEL](http://msdn.microsoft.com/library/windows/desktop/ms645617)の推奨動作は、ホイールを回転のメッセージをサポートします。  
  
 自動スクロールを利用するには、`CView`の代わりに `CScrollView` から、からビュー クラスを派生します。  ビューを初めて作成するとき、は、ドキュメントのサイズに基づいてスクロール可能なビューのサイズを計算する場合は [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) または [CView::OnUpdate](../Topic/CView::OnUpdate.md)のオーバーライドの `SetScrollSizes` のメンバー関数を呼び出します。  ドキュメントのサイズを照会する独自のコードを記述する必要があります。  例については、[サンプルを Scribble します。](../../top/visual-cpp-samples.md)を参照してください\)。  
  
 `SetScrollSizes` のメンバー関数の呼び出しは、水平方向と垂直方向にスクロールするには、スクロール ビューのビューのマップ モード、合計サイズ、および量を設定します。  すべてのサイズは論理単位になります。  ビューの論理サイズは、通常、ドキュメントに格納されているデータに基づいて計算する場合として固定サイズを指定することもできます。  両方の方法の例については、[CScrollView::SetScrollSizes](../Topic/CScrollView::SetScrollSizes.md)を参照してください。  
  
 論理単位で垂直方向にスクロールするための量を指定します。  ユーザーがスクロール ボックスの外にスクロール バー シャフトをクリックすると既定では、`CScrollView` は「ページをスクロールします」。ユーザーがスクロール バーの端または右端にスクロール矢印をクリックすると、`CScrollView` は「行をスクロールします」。既定では、ページがビューの合計サイズの 1\/10。; 行は、ページ サイズの 1\/10 です。  `SetScrollSizes` のメンバー関数のカスタムのサイズを渡すことによってこれらの既定値をオーバーライドします。  たとえば、現在のフォントの行の高さに合計サイズと垂直方向のサイズの幅の一部に水平サイズを設定している可能性があります。  
  
 スクロールの代わりに、`CScrollView` は、現在のウィンドウ サイズに自動的にビューを縮小することができます。  このモードでは、ビューにスクロール バーがなく、まったくウィンドウのクライアント領域に合わせて論理ビューが拡大または縮小する。  このスケールに最適の機能を使用するには、[CScrollView::SetScaleToFitSize](../Topic/CScrollView::SetScaleToFitSize.md)を呼び出します。  \( `SetScaleToFitSize` か `SetScrollSizes`、との両方を呼び出すしないでください\)。  
  
 、派生ビュー クラスの `OnDraw` のメンバー関数を呼び出す前に、`CScrollView` は `OnDraw`に渡す `CPaintDC` のデバイス コンテキスト オブジェクトができるように自動的にビューポートの原点を調整します。  
  
 スクロール ウィンドウにビューポートの原点を調整するには、`CScrollView` は [CView::OnPrepareDC](../Topic/CView::OnPrepareDC.md)をオーバーライドします。  この変更は `CScrollView` が `OnDraw`に渡されますが、使用する `CClientDC`などのそのほかのデバイス コンテキストに対して、独自 **CScrollView::OnPrepareDC**、を呼び出す必要があります `CPaintDC` のデバイス コンテキストに自動です。  ペン、背景色、およびそのほかの描画の属性を設定するに **CScrollView::OnPrepareDC** をオーバーライドできますが、スケーリングを行うための基本クラスを呼び出します。  
  
 スクロール バーは次の場合に示すように、ビューに関連して 3 か所で表示できます:  
  
-   標準のウィンドウ スタイルのスクロール バーは **WS\_HSCROLL** と **WS\_VSCROLL**[Windows スタイル](../Topic/Window%20Styles.md)を使用してビューに対して設定できます。  
  
-   スクロール バー コントロールは、ビューを含むフレームにフレームワークによってフレーム ウィンドウから現在アクティブなビューに `WM_HSCROLL` と `WM_VSCROLL` のメッセージを転送追加できます。  
  
-   フレームワークは、`CSplitterWnd` の分割線のコントロールで現在アクティブな分割ウィンドウ \(ビュー\) にスクロール メッセージを転送します。  共有スクロール バーの [CSplitterWnd](../../mfc/reference/csplitterwnd-class.md) に設定すると、`CScrollView` のオブジェクトを使用して独自に作成するのではなく、共有ものも。  
  
 `CScrollView`の使用の詳細については、[ドキュメント\/ビュー アーキテクチャ](../Topic/Document-View%20Architecture.md) と [派生ビューは MFC で使用できるを並べ替えます。](../../mfc/derived-view-classes-available-in-mfc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 `CScrollView`  
  
## 必要条件  
 **ヘッダー:** afxwin.h  
  
## 参照  
 [MFC DIBLOOK サンプル](../../top/visual-cpp-samples.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../Topic/CView%20Class.md)   
 [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)