---
title: "CSplitterWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
dev_langs:
- C++
helpviewer_keywords:
- static splitter windows
- multiple views
- splitter windows
- views, multiple per frame
- dynamic splitter windows
- CSplitterWnd class
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: d015aa604c5394ccbe8c7471b70c84763cc00a5b
ms.lasthandoff: 02/24/2017

---
# <a name="csplitterwnd-class"></a>CSplitterWnd クラス
分割ウィンドウの機能が用意されています。分割ウィンドウとは複数のペインを持つウィンドウです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|構築する呼び出し、`CSplitterWnd`オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|次のペインまたは前のペインのコマンドを実行します。|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|次のペインまたは前のペインのコマンドが現在可能かどうかを確認します。|  
|[CSplitterWnd::Create](#create)|動的分割ウィンドウを作成し、接続への呼び出し、`CSplitterWnd`オブジェクトです。|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|共有のスクロール バー コントロールを作成します。|  
|[CSplitterWnd::CreateStatic](#createstatic)|静的な分割ウィンドウを作成し、接続するへの呼び出し、`CSplitterWnd`オブジェクトです。|  
|[CSplitterWnd::CreateView](#createview)|分割ウィンドウで、ウィンドウを作成する呼び出しです。|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|分割ウィンドウから列を削除します。|  
|[CSplitterWnd::DeleteRow](#deleterow)|分割ウィンドウから行を削除します。|  
|[CSplitterWnd::DeleteView](#deleteview)|分割ウィンドウのビューを削除します。|  
|[あると](#dokeyboardsplit)|キーボードの分割コマンド、通常「ウィンドウの分割です」の実行します。|  
|[CSplitterWnd::DoScroll](#doscroll)|分割ウィンドウのスクロールを同期を実行します。|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|指定された数のピクセル単位で分割ウィンドウをスクロールします。|  
|[CSplitterWnd::GetActivePane](#getactivepane)|フォーカスまたはアクティブなビュー、フレーム内のアクティブなペインを決定します。|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|現在のウィンドウの列数を返します。|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|指定された列に関する情報を返します。|  
|[CSplitterWnd::GetPane](#getpane)|指定した行と列にあるペインを返します。|  
|[CSplitterWnd::GetRowCount](#getrowcount)|現在のウィンドウの行の数を返します。|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|指定された行に関する情報を返します。|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|共有のスクロール バー スタイルを返します。|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|ウィンドウの ID を指定した行と列にあるウィンドウの子を返します。|  
|[CSplitterWnd::IsChildPane](#ischildpane)|ウィンドウが分割ウィンドウの子ウィンドウで現在あるかどうかを確認する呼び出しです。|  
|[CSplitterWnd::IsTracking](#istracking)|分割バーが移動中かどうかを判断します。|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|分割ウィンドウを表示し、行または列のサイズを調整した後の呼び出しです。|  
|[CSplitterWnd::SetActivePane](#setactivepane)|アクティブなフレーム内になるウィンドウを設定します。|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|指定した列の情報を設定する呼び出しです。|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|指定した行の情報を設定する呼び出しです。|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|分割ウィンドウの新しいスクロール バー スタイル スクロール バーのサポートの共有を指定します。|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|フレーム ウィンドウを垂直方向に分割する位置を示します。|  
|[CSplitterWnd::SplitRow](#splitrow)|フレーム ウィンドウを水平方向に分割する位置を示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|分割ウィンドウを描画するためにフレームワークによって呼び出されます。|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|分割ウィンドウのイメージをレンダリングします。|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|同じのサイズと形状、フレーム ウィンドウに分割ウィンドウの画像をレンダリングします。|  
  
## <a name="remarks"></a>コメント  
 ペインは、通常、アプリケーション固有のオブジェクトから派生した[CView](../../mfc/reference/cview-class.md)、いずれかのことができますが、 [CWnd](../../mfc/reference/cwnd-class.md)適切な子ウィンドウの ID を持つオブジェクト  
  
 A`CSplitterWnd`オブジェクトが親に埋め込まれた通常[CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)オブジェクトです。 作成、`CSplitterWnd`オブジェクトの次の手順を使用します。  
  
1.  埋め込む、`CSplitterWnd`親フレーム内のメンバー変数です。  
  
2.  親フレームの[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数。  
  
3.  オーバーライドされた内`OnCreateClient`を呼び出す、[作成](#create)または[CreateStatic](#createstatic)のメンバー関数`CSplitterWnd`します。  
  
 呼び出す、**作成**動的分割ウィンドウを作成します。 動的分割ウィンドウは通常を作成し、多数の個別のペインまたは同じドキュメントのビューのスクロールに使用されます。 フレームワークは、分割の最初のウィンドウを自動的に作成されます。フレームワークを作成を変更すると、分割ウィンドウのコントロールの操作とその他のウィンドウを破棄します。  
  
 呼び出すと**作成**ウィンドウが完全に表示するのには小さすぎる場合を決定する行の最小の高さと列の幅を指定します。 呼び出した後**作成**、最小値を調整するには呼び出すことによって、[ために使われます](#setcolumninfo)と[かどうか](#setrowinfo)メンバー関数。  
  
 使用しても、`SetColumnInfo`と`SetRowInfo`「最適」列の幅と行の高さを「理想的な」を設定するメンバー関数。 フレームワークには、分割ウィンドウが表示されたら、最初に、分割ウィンドウでは、親フレームを表示します。 分割ウィンドウのクライアント領域の右下隅から左上隅に向かってその最適な大きさに基づいて列と行でペイン、フレームワークを配置します。  
  
 動的分割ウィンドウ内のすべてのペインは、同じクラスでなければなりません。 動的分割ウィンドウをサポートするよく知られたアプリケーションには、Microsoft Word や Microsoft Excel が含まれます。  
  
 使用して、`CreateStatic`静的な分割ウィンドウを作成します。 ユーザーは、ウィンドウ、いない、番号や注文の静的な分割でウィンドウ枠のサイズだけを変更できます。  
  
 静的な分割を作成するときに、具体的にはすべて、静的な分割のウィンドウを作成する必要があります。 親フレームの前にすべてのペインを作成するかどうかを確認`OnCreateClient`メンバー関数から返される、または、フレームワークは、ウィンドウが正しく表示されません。  
  
 `CreateStatic`メンバー関数は、0 の行の最小の高さと列の幅と静的な分割を自動的に初期化します。 呼び出した後**作成**、呼び出すことによってこれらの最小値を調整する、[ために使われます](#setcolumninfo)と[小さ](#setrowinfo)メンバー関数。 使用しても`SetColumnInfo`と`SetRowInfo`を呼び出した後`CreateStatic`を示すために最適なウィンドウ サイズを必要に応じて。  
  
 静的な分割の各ペインは、多くの場合、さまざまなクラスに属しています。 静的な分割ウィンドウの例については、グラフィックス エディターと Windows ファイル マネージャーを参照してください。  
  
 分割ウィンドウには、(スクロール バー ペインが持っている) とは別の特殊なスクロール バーがサポートしています。 これらのスクロール バーの子である、`CSplitterWnd`オブジェクトし、は、ウィンドウと共有します。  
  
 分割ウィンドウを作成するときに、これらの特殊なスクロール バーを作成します。 など、 `CSplitterWnd`&1; つの行、2 つの列を含む、 **WS_VSCROLL**スタイルに&2; つのペインで共有される垂直スクロール バーが表示されます。 ユーザーがスクロール バーを移動すると`WM_VSCROLL`メッセージの両方のウィンドウに送信されます。 ペインには、スクロール バーの位置が設定されている場合、共有のスクロール バーを設定します。  
  
 分割ウィンドウの詳細については、以下を参照してください。  
  
- [テクニカル ノート 29](../../mfc/tn029-splitter-windows.md)  
  
-   サポート技術情報記事 Q262024: HOWTO: CSplitterWnd の子として使用する CPropertySheet  
  
 動的分割ウィンドウを作成する方法の詳細についてを参照してください。  
  
-   MFC サンプル[Scribble](../../visual-cpp-samples.md)  
  
-   MFC サンプル[VIEWEX](../../visual-cpp-samples.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="activatenext"></a>CSplitterWnd::ActivateNext  
 次のペインまたは前のペインのコマンドを実行するために、フレームワークによって呼び出されます。  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bPrev`  
 どのウィンドウをアクティブ化することを示します。 **TRUE**の前です。**FALSE**次です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は高レベルのコマンドで使用される、 [CView](../../mfc/reference/cview-class.md)に委任するクラス、`CSplitterWnd`実装します。  
  
##  <a name="canactivatenext"></a>CSplitterWnd::CanActivateNext  
 次のペインまたは前のペインのコマンドが現在可能かどうかを確認するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bPrev`  
 どのウィンドウをアクティブ化することを示します。 **TRUE**の前です。**FALSE**次です。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は高レベルのコマンドで使用される、 [CView](../../mfc/reference/cview-class.md)に委任するクラス、`CSplitterWnd`実装します。  
  
##  <a name="create"></a>CSplitterWnd::Create  
 動的分割ウィンドウを作成するには、**作成**メンバー関数。  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    int nMaxRows,  
    int nMaxCols,  
    SIZE sizeMin,  
    CCreateContext* pContext,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 分割ウィンドウの親フレーム ウィンドウです。  
  
 *nMaxRows*  
 分割ウィンドウ内の行の最大数。 この値は、2 を超えない必要があります。  
  
 *nMaxCols*  
 分割ウィンドウ内の列の最大数。 この値は、2 を超えない必要があります。  
  
 `sizeMin`  
 ペインが表示される最小サイズを指定します。  
  
 `pContext`  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 ほとんどの場合、これを指定できます、`pContext`親フレーム ウィンドウに渡されます。  
  
 `dwStyle`  
 ウィンドウ スタイルを指定します。  
  
 `nID`  
 ウィンドウの子ウィンドウの ID。 ID は、 **AFX_IDW_PANE_FIRST**分割ウィンドウがもう&1; つの分割ウィンドウ内に入れ子にしない限り、します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 埋め込むことができます、 `CSplitterWnd` 、親の[CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)次の手順を実行することでオブジェクト。  
  
1.  埋め込む、`CSplitterWnd`親フレーム内のメンバー変数です。  
  
2.  親フレームの[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)メンバー関数。  
  
3.  呼び出す、**作成**メンバー関数、オーバーライドされた内部から`OnCreateClient`します。  
  
 親フレーム内から分割ウィンドウを作成する場合は、親のフレームを渡す`pContext`分割ウィンドウへのパラメーターです。 それ以外の場合、このパラメーターを指定できます**NULL**します。  
  
 動的分割ウィンドウの最初の行の最小の高さと列の幅は設定、`sizeMin`パラメーター。 これらの最小値は、ペインが小さすぎて全体を表示するかどうかを確認してを変更できます、[小さ](#setrowinfo)と[ため](#setcolumninfo)メンバー関数。  
  
 動的分割ウィンドウの詳細は、資料の「分割ウィンドウ」を参照してください。[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`クラスの概要です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing #&125;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>CSplitterWnd::CreateScrollBarCtrl  
 共有のスクロール バー コントロールを作成するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 ウィンドウ スタイルを指定します。  
  
 `nID`  
 ウィンドウの子ウィンドウの ID。 ID は、 **AFX_IDW_PANE_FIRST**分割ウィンドウがもう&1; つの分割ウィンドウ内に入れ子にしない限り、します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オーバーライド`CreateScrollBarCtrl`にスクロール バーの横にあるコントロールを付加します。 既定の動作では、通常の Windows のスクロール バー コントロールを作成します。  
  
##  <a name="createstatic"></a>CSplitterWnd::CreateStatic  
 静的な分割ウィンドウを作成するには、`CreateStatic`メンバー関数。  
  
```  
virtual BOOL CreateStatic(
    CWnd* pParentWnd,  
    int nRows,  
    int nCols,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentWnd`  
 分割ウィンドウの親フレーム ウィンドウです。  
  
 `nRows`  
 行の番号。 この値は、16 を超えない必要があります。  
  
 *nCols*  
 列の番号。 この値は、16 を超えない必要があります。  
  
 `dwStyle`  
 ウィンドウ スタイルを指定します。  
  
 `nID`  
 ウィンドウの子ウィンドウの ID。 ID は、 **AFX_IDW_PANE_FIRST**分割ウィンドウがもう&1; つの分割ウィンドウ内に入れ子にしない限り、します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 A`CSplitterWnd`は通常、親に埋め込まれて`CFrameWnd`または[CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)次の手順を実行することでオブジェクト。  
  
1.  埋め込む、`CSplitterWnd`親フレーム内のメンバー変数です。  
  
2.  親フレームの`OnCreateClient`メンバー関数。  
  
3.  呼び出す、`CreateStatic`メンバー関数、オーバーライドされた内部から[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)します。  
  
 静的な分割ウィンドウには、一定の数異なるクラスから多くの場合、ペインにはが含まれています。  
  
 静的な分割ウィンドウを作成するときに作成する必要がある同時にすべてのペインです。 [CreateView](#createview)メンバー関数は通常、この目的で使用しても他の nonview クラスを作成することができます。  
  
 静的な分割ウィンドウの最初の行の最小の高さと列の幅は 0 です。 これらの最小値は、調べるには、ウィンドウが小さすぎて全体を表示するときを変更できます、[小さ](#setrowinfo)と[ため](#setcolumninfo)メンバー関数。  
  
 静的な分割ウィンドウには、スクロール バーを追加するには、追加、 **WS_HSCROLL**と**WS_VSCROLL**にスタイル`dwStyle`します。  
  
 アーティクルの「分割ウィンドウ」を参照してください[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`の詳細については、静的な分割ウィンドウ クラスの概要です。  
  
##  <a name="createview"></a>CSplitterWnd::CreateView  
 静的な分割ウィンドウの枠を作成します。  
  
```  
virtual BOOL CreateView(
    int row,  
    int col,  
    CRuntimeClass* pViewClass,  
    SIZE sizeInit,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>パラメーター  
 `row`  
 新しいビューを配置するための分割ウィンドウの行を指定します。  
  
 `col`  
 新しいビューを配置するための分割ウィンドウの列を指定します。  
  
 `pViewClass`  
 指定、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)新しいビューです。  
  
 *sizeInit*  
 新しいビューの初期サイズを指定します。  
  
 `pContext`  
 ビューの作成に使用されるコンテキストの作成へのポインター (通常、`pContext`オーバーライドされた親のフレームに渡される[CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)分割ウィンドウを作成するメンバー関数)。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、分割線を表示する前に、静的な分割ウィンドウのすべてのウィンドウを作成する必要があります。  
  
 フレームワークでは、動的分割ウィンドウのユーザーがウィンドウで、行、または列を分割時に、新しいウィンドウを作成するには、このメンバー関数も呼び出します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&4;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>CSplitterWnd::CSplitterWnd  
 構築する呼び出し、`CSplitterWnd`オブジェクトです。  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>コメント  
 構築、 `CSplitterWnd`&2; つのステップ内のオブジェクト。 最初に、作成するコンス トラクターを呼び出す、`CSplitterWnd`オブジェクトし、しを呼び出す、[作成](#create)分割ウィンドウを作成してそれにアタッチするメンバー関数、`CSplitterWnd`オブジェクトです。  
  
##  <a name="deletecolumn"></a>CSplitterWnd::DeleteColumn  
 分割ウィンドウから列を削除します。  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *colDelete*  
 削除する列を指定します。  
  
### <a name="remarks"></a>コメント  
 動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (分割ウィンドウがある場合に、 **SPLS_DYNAMIC_SPLIT**スタイル)。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="deleterow"></a>CSplitterWnd::DeleteRow  
 分割ウィンドウから行を削除します。  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>パラメーター  
 *行を削除します。*  
 削除する行を指定します。  
  
### <a name="remarks"></a>コメント  
 動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (分割ウィンドウがある場合に、 **SPLS_DYNAMIC_SPLIT**スタイル)。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="deleteview"></a>CSplitterWnd::DeleteView  
 分割ウィンドウのビューを削除します。  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>パラメーター  
 `row`  
 ビューを削除する、分割ウィンドウの行を指定します。  
  
 `col`  
 ビューを削除する、分割ウィンドウの列を指定します。  
  
### <a name="remarks"></a>コメント  
 アクティブなビューが削除される場合、次のビューがアクティブになります。 既定の実装は、ビューが自動的に前提としています。 削除[PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)します。  
  
 動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (分割ウィンドウがある場合に、 **SPLS_DYNAMIC_SPLIT**スタイル)。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="dokeyboardsplit"></a>あると  
 キーボードの分割コマンド、通常「ウィンドウの分割です」の実行します。  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は高レベルのコマンドで使用される、 [CView](../../mfc/reference/cview-class.md)に委任するクラス、`CSplitterWnd`実装します。  
  
##  <a name="doscroll"></a>CSplitterWnd::DoScroll  
 分割ウィンドウのスクロールを同期を実行します。  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pViewFrom`  
 スクロールのメッセージの発生元となるビューへのポインター。  
  
 `nScrollCode`  
 スクロール バーのコードをユーザーを示すには、要求のスクロールします。 このパラメーターは&2; つの部分で構成されます。 水平方向にスクロール発生の種類を決定する下位バイトと垂直方向にスクロール発生の型を決定する上位バイト。  
  
- **SB_BOTTOM**一番下までスクロールします。  
  
- **SB_LINEDOWN**が&1; 行下へスクロールします。  
  
- **SB_LINEUP**を&1; つの行にスクロールします。  
  
- **SB_PAGEDOWN**&1; つのページを下へスクロールします。  
  
- **SB_PAGEUP**を&1; つのページをスクロールします。  
  
- **SB_TOP**上部までスクロールします。  
  
 `bDoScroll`  
 指定されたスクロール動作が発生したかどうかを決定します。 場合`bDoScroll`は**TRUE** (子ウィンドウが存在する場合は、およびスクロールの範囲であれば、分割ウィンドウなど)、指定されたスクロール動作行うことができます。 場合、`bDoScroll`は**FALSE** (場合は、子ウィンドウが存在しないか、分割されたビューにスクロールの範囲がありません)、スクロールは発生しませんし、します。  
  
### <a name="return-value"></a>戻り値  
 同期されている場合は 0 以外のスクロールが発生します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、ビューは、スクロール メッセージを受け取ったときに、分割ウィンドウの同期スクロールを実行するためにフレームワークによって呼び出されます。 同期スクロールを許可する前に、ユーザーによる操作を必要とするためにオーバーライドします。  
  
##  <a name="doscrollby"></a>CSplitterWnd::DoScrollBy  
 指定された数のピクセル単位で分割ウィンドウをスクロールします。  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pViewFrom`  
 スクロールのメッセージの発生元となるビューへのポインター。  
  
 `sizeScroll`  
 水平および垂直方向にスクロールするピクセル数。  
  
 bDoScroll  
 指定されたスクロール動作が発生したかどうかを決定します。 場合`bDoScroll`は**TRUE** (子ウィンドウが存在する場合は、およびスクロールの範囲であれば、分割ウィンドウなど)、指定されたスクロール動作行うことができます。 場合、`bDoScroll`は**FALSE** (場合は、子ウィンドウが存在しないか、分割されたビューにスクロールの範囲がありません)、スクロールは発生しませんし、します。  
  
### <a name="return-value"></a>戻り値  
 同期されている場合は 0 以外のスクロールが発生します。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 スクロール メッセージへの応答として、フレームワークによって呼び出されます、同期を実行するにはピクセル単位で示されたの量で、分割ウィンドウのスクロール`sizeScroll`します。 正の値が右にスクロール ダウンを示します負の値を示すを左にスクロールします。  
  
 スクロールを許可する前に、ユーザーによる操作を必要とするためにオーバーライドします。  
  
##  <a name="getactivepane"></a>CSplitterWnd::GetActivePane  
 フォーカスまたはアクティブなビュー、フレーム内のアクティブなペインを決定します。  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRow`  
 ポインター、 **int**アクティブなペインの行番号を取得します。  
  
 `pCol`  
 ポインター、 **int**アクティブなペインの列番号を取得します。  
  
### <a name="return-value"></a>戻り値  
 アクティブなペインへのポインター。 **NULL**アクティブなペインが存在しない場合。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、分割ウィンドウのアクティブなペインを調べるためにフレームワークによって呼び出されます。 アクティブなペインを取得する前に、ユーザーによる操作を必要とするためにオーバーライドします。  
  
##  <a name="getcolumncount"></a>CSplitterWnd::GetColumnCount  
 現在のウィンドウの列数を返します。  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割ウィンドウの現在の列数を返します。 静的な分割では、列の最大数の場合はもします。  
  
##  <a name="getcolumninfo"></a>CSplitterWnd::GetColumnInfo  
 指定された列に関する情報を返します。  
  
```  
void GetColumnInfo(
    int col,  
    int& cxCur,  
    int& cxMin) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `col`  
 列を指定します。  
  
 *cxCur*  
 参照、`int`列の現在の幅に設定します。  
  
 `cxMin`  
 参照、`int`列の現在の最小幅に設定します。  
  
##  <a name="getpane"></a>CSplitterWnd::GetPane  
 指定した行と列にあるペインを返します。  
  
```  
CWnd* GetPane(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `row`  
 行を指定します。  
  
 `col`  
 列を指定します。  
  
### <a name="return-value"></a>戻り値  
 指定した行と列にあるペインを返します。 返されるペインは、通常、 [CView](../../mfc/reference/cview-class.md)-クラスを派生します。  
  
##  <a name="getrowcount"></a>CSplitterWnd::GetRowCount  
 現在のウィンドウの行の数を返します。  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割ウィンドウの行の現在の数を返します。 静的な分割ウィンドウでは、行の最大数の場合はもします。  
  
##  <a name="getrowinfo"></a>CSplitterWnd::GetRowInfo  
 指定された行に関する情報を返します。  
  
```  
void GetRowInfo(
    int row,  
    int& cyCur,  
    int& cyMin) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `row`  
 行を指定します。  
  
 `cyCur`  
 参照を`int`現在、行の高さ (ピクセル単位) に設定します。  
  
 `cyMin`  
 参照を`int`ピクセル単位で行の現在の最小の高さに設定します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を呼び出して、指定された行に関する情報を取得します。 `cyCur`パラメーターが指定された行の現在の高さが渡され、`cyMin`行の高さの最小値が入力されます。  
  
##  <a name="getscrollstyle"></a>CSplitterWnd::GetScrollStyle  
 分割ウィンドウで、共有のスクロール バー スタイルを返します。  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 1 つ以上の次の windows スタイル フラグの成功した場合。  
  
- **WS_HSCROLL**スプリッターが現在共有の水平スクロール バーを管理する場合。  
  
- **WS_VSCROLL**スプリッターが現在の共有の垂直スクロール バーを管理する場合。  
  
 0 の場合、分割ウィンドウは、共有スクロール バーを現在管理しません。  
  
##  <a name="idfromrowcol"></a>CSplitterWnd::IdFromRowCol  
 子の指定した行と列にあるウィンドウのウィンドウの ID を取得します。  
  
```  
int IdFromRowCol(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `row`  
 分割ウィンドウの行を指定します。  
  
 `col`  
 分割ウィンドウの列を指定します。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウの子ウィンドウの ID。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、ビューでないペインを作成するため使用され、ウィンドウが存在する前に呼び出すことができます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#5;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>CSplitterWnd::IsChildPane  
 指定するかどうか`pWnd`分割ウィンドウの子ウィンドウは、現在です。  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)をテストするオブジェクト。  
  
 `pRow`  
 ポインター、`int`行番号を格納します。  
  
 `pCol`  
 ポインター、`int`列番号を格納します。  
  
### <a name="return-value"></a>戻り値  
 ゼロ以外の場合`pWnd`が、現在この分割ウィンドウの子ペインと`pRow`と`pCol`分割ウィンドウのウィンドウの位置が格納されます。 場合`pWnd`子ウィンドウには、分割ウィンドウの 0 が返されます。  
  
### <a name="remarks"></a>コメント  
 6.0 より前のバージョンを Visual C では、この関数として定義されました。  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 このバージョンは廃止されており使用しないでください。  
  
##  <a name="istracking"></a>CSplitterWnd::IsTracking  
 ウィンドウでスプリッター バーが動いている現在かどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>戻り値  
 分割操作の実行中の場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="ondrawsplitter"></a>CSplitterWnd::OnDrawSplitter  
 分割ウィンドウのイメージをレンダリングします。  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 描画するためのデバイス コンテキストへのポインター。 場合`pDC`は**NULL**、し、 [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow)と呼ばれるフレームワークおよびない分割によってウィンドウが描画されます。  
  
 `nType`  
 値、 **enum ESplitType**次のいずれかを指定することができます。  
  
- **splitBox**スプリッター ボックスにドラッグします。  
  
- `splitBar`2 つの分割ウィンドウ間で表示されるバー。  
  
- **splitIntersection**分割ウィンドウの交差部分です。 Windows 95/98 で実行すると、この要素は呼び出されません。  
  
- **splitBorder**分割ウィンドウの境界線。  
  
 `rect`  
 参照、 [CRect](../../atl-mfc-shared/reference/crect-class.md)サイズと、分割ウィンドウの形状を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、描画し、分割ウィンドウの正確な特性を指定するためにフレームワークによって呼び出されます。 オーバーライド`OnDrawSplitter`された分割ウィンドウのさまざまなグラフィック要素の外観の高度にカスタマイズできます。 分割バーの交差部分が混ざり合うことで、既定の画像が Windows または Microsoft Windows 95/98 用 Microsoft works スプリッターに似ています。  
  
 動的分割ウィンドウの詳細は、資料の「分割ウィンドウ」を参照してください。[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`クラスの概要です。  
  
##  <a name="oninverttracker"></a>CSplitterWnd::OnInvertTracker  
 同じのサイズと形状、フレーム ウィンドウに分割ウィンドウの画像をレンダリングします。  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 参照、`CRect`トラッキング四角形を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、分割ウィンドウのサイズ変更時にフレームワークによって呼び出されます。 オーバーライド`OnInvertTracker`分割ウィンドウの画像の高度にカスタマイズできます。 分割バーの交差部分が混ざり合うことで、既定の画像が Windows または Microsoft Windows 95/98 用 Microsoft works スプリッターに似ています。  
  
 動的分割ウィンドウの詳細は、資料の「分割ウィンドウ」を参照してください。[複数のドキュメント タイプ、ビュー、およびフレーム ウィンドウ](../../mfc/multiple-document-types-views-and-frame-windows.md)、[テクニカル ノート 29:](../../mfc/tn029-splitter-windows.md)、および`CSplitterWnd`クラスの概要です。  
  
##  <a name="recalclayout"></a>CSplitterWnd::RecalcLayout  
 分割ウィンドウを表示し、行または列のサイズを調整した後の呼び出しです。  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>コメント  
 行と列のサイズを調整した後、正しく分割ウィンドウを再表示するのには、このメンバー関数を呼び出す、[小さ](#setrowinfo)と[ために使われます](#setcolumninfo)メンバー関数。 分割ウィンドウを表示する前に、作成プロセスの一部として行と列のサイズを変更する場合、このメンバー関数を呼び出す必要はありません。  
  
 フレームワークは、ユーザーは、分割ウィンドウのサイズを変更したり、移動するたびに、このメンバー関数を呼び出します。  
  
### <a name="example"></a>例  
  例を参照してください[CSplitterWnd::SetColumnInfo](#setcolumninfo)します。  
  
##  <a name="setactivepane"></a>CSplitterWnd::SetActivePane  
 アクティブなフレーム内になるウィンドウを設定します。  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `row`  
 場合`pWnd`は**NULL**、アクティブになるウィンドウ内の行を指定します。  
  
 `col`  
 場合`pWnd`は**NULL**、アクティブになるウィンドウの列を指定します。  
  
 `pWnd`  
 ポインター、`CWnd`オブジェクトです。 場合**NULL**で指定されたウィンドウ`row`と`col`アクティブ設定されています。 ない場合**NULL**、アクティブに設定されているペインを指定します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、ユーザーは、フレーム ウィンドウ内のペインにフォーカスを変更すると、アクティブなとして、ウィンドウを設定するためにフレームワークによって呼び出されます。 明示的に呼び出すことができます`SetActivePane`に指定されたビューにフォーカスを変更します。  
  
 行と列のいずれかでウィンドウを指定**または**により`pWnd`します。  
  
##  <a name="setcolumninfo"></a>CSplitterWnd::SetColumnInfo  
 指定した列の情報を設定する呼び出しです。  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>パラメーター  
 `col`  
 分割ウィンドウの列を指定します。  
  
 *cxIdeal*  
 分割ウィンドウの列の最適の幅をピクセル単位で指定します。  
  
 `cxMin`  
 分割ウィンドウの列の最小幅をピクセル単位で指定します。  
  
### <a name="remarks"></a>コメント  
 新しい最小の幅と列の適切な幅を設定するには、このメンバー関数を呼び出します。 列の最小値は、列を完全に表示するのには小さすぎますが時期を決定します。  
  
 フレームワークでは、分割ウィンドウを表示するときは、分割ウィンドウのクライアント領域の右下隅から左上隅に向かってその最適な大きさに基づいて列と行でウィンドウをレイアウトします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&6;](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="setrowinfo"></a>CSplitterWnd::SetRowInfo  
 指定した行の情報を設定する呼び出しです。  
  
```  
void SetRowInfo(
    int row,  
    int cyIdeal,  
    int cyMin);
```  
  
### <a name="parameters"></a>パラメーター  
 `row`  
 分割ウィンドウの行を指定します。  
  
 *cyIdeal*  
 最適な分割ウィンドウの行の高さをピクセル単位で指定します。  
  
 `cyMin`  
 分割ウィンドウの行の最小の高さをピクセル単位で指定します。  
  
### <a name="remarks"></a>コメント  
 新しい高さの最小値と行の適切な高さを設定するには、このメンバー関数を呼び出します。 行の最小値は、行を完全に表示するのには小さすぎますが時期を決定します。  
  
 フレームワークでは、分割ウィンドウを表示するときは、分割ウィンドウのクライアント領域の右下隅から左上隅に向かってその最適な大きさに基づいて列と行でウィンドウをレイアウトします。  
  
##  <a name="setscrollstyle"></a>CSplitterWnd::SetScrollStyle  
 分割ウィンドウの新しいスクロール スタイル スクロール バーのサポートの共有を指定します。  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 分割ウィンドウの新しいスクロール スタイルでは、スクロール バーのサポートは、次の値のいずれかを共有しました。  
  
- **WS_HSCROLL**作成/表示水平スクロール バーを共有します。  
  
- **WS_VSCROLL**作成/表示垂直スクロール バーを共有します。  
  
### <a name="remarks"></a>コメント  
 スクロール バーを作成した後は破棄されない場合でも`SetScrollStyle`そのスタイルなしで呼び出される代わりに、スクロール バーが非表示になっています。 これにより、非表示になっている場合でも、その状態を保持するスクロール バーです。 呼び出した後`SetScrollStyle`を呼び出す必要がある[RecalcLayout](#recalclayout)のすべての変更を有効にします。  
  
##  <a name="splitcolumn"></a>CSplitterWnd::SplitColumn  
 フレーム ウィンドウを垂直方向に分割する位置を示します。  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>パラメーター  
 *cxBefore*  
 分割が発生する前に、ピクセル位置。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 垂直分割ウィンドウが作成されるときに呼び出されます。 `SplitColumn`分割が発生する既定の場所を示します。  
  
 `SplitColumn`動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (分割ウィンドウがある場合に、 **SPLS_DYNAMIC_SPLIT**スタイル)。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="splitrow"></a>CSplitterWnd::SplitRow  
 フレーム ウィンドウを水平方向に分割する位置を示します。  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>パラメーター  
 *cyBefore*  
 分割が発生する前に、ピクセル位置。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 水平分割ウィンドウが作成されるときに呼び出されます。 `SplitRow`分割が発生する既定の場所を示します。  
  
 `SplitRow`動的分割ウィンドウのロジックを実装するためにフレームワークによって呼び出されます (分割ウィンドウがある場合に、 **SPLS_DYNAMIC_SPLIT**スタイル)。 これはカスタマイズ可能な仮想関数と共に[CreateView](#createview)により高度な動的分割ウィンドウを実装します。  
  
##  <a name="ondraw"></a>CSplitterWnd::OnDraw  
 分割ウィンドウを描画するためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 デバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル VIEWEX](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)

