---
title: "CView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CView
dev_langs:
- C++
helpviewer_keywords:
- views [C++], view classes
- multiple views
- CView class
- document/view architecture
- input, and view class
- MDI [C++], view windows
- print preview, view windows
- windows [C++], views
- child windows, views
- frame windows [C++], views
- user input [C++], interpreting through view class
ms.assetid: 9cff3c56-7564-416b-b9a4-71a9254ed755
caps.latest.revision: 25
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
ms.openlocfilehash: ce5100a9ee4a1c20df04f79f0c8cd645ae3afce7
ms.lasthandoff: 02/24/2017

---
# <a name="cview-class"></a>CView クラス
ユーザーが定義するビュークラスの基本機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CView : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CView::CView](#cview)|`CView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[しません](#doprepareprinting)|印刷 ダイアログ ボックスを表示し、プリンター デバイス コンテキストの作成オーバーライドするときに呼び出す、`OnPreparePrinting`メンバー関数。|  
|[CView::GetDocument](#getdocument)|ビューに関連付けられているドキュメントを返します。|  
|[CView::IsSelected](#isselected)|ドキュメントまたはアイテムが選択されているかどうかをテストします。 OLE のサポートが必要です。|  
|[CView::OnDragEnter](#ondragenter)|項目が最初に、ビューのドラッグ アンド ドロップ領域にドラッグされたときに呼び出されます。|  
|[CView::OnDragLeave](#ondragleave)|ドラッグした項目がビューのドラッグ アンド ドロップ領域を離れるときに呼び出されます。|  
|[直前](#ondragover)|項目がビューのドラッグ アンド ドロップ領域にドラッグされたときに呼び出されます。|  
|[CView::OnDragScroll](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされるかどうかを判断するには、呼び出されます。|  
|[この関数](#ondrop)|項目が、ビューでは、既定のハンドラーのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|  
|[CView::OnDropEx](#ondropex)|項目が、ビューでは、プライマリ ハンドラーのドラッグ アンド ドロップ領域にドロップされたときに呼び出されます。|  
|[:Oninitialupdate](#oninitialupdate)|ドキュメントにビューを最初にアタッチした後に呼び出されます。|  
|[付け](#onpreparedc)|前に呼び出される、`OnDraw`画面表示のメンバー関数が呼び出される、または`OnPrint`印刷または印刷プレビューのメンバー関数が呼び出されます。|  
|[CView::OnScroll](#onscroll)|OLE アイテムが、ビューの境界を越えてドラッグされるときに呼び出されます。|  
|[CView::OnScrollBy](#onscrollby)|アクティブなインプレース OLE アイテムを含むビューがスクロールされたときに呼び出されます。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CView::OnActivateFrame](#onactivateframe)|ビューを含むフレーム ウィンドウがアクティブまたは非アクティブになると呼び出されます。|  
|[CView::OnActivateView](#onactivateview)|ビューがアクティブになったときに呼び出されます。|  
|[値](#onbeginprinting)|印刷ジョブが開始するときに呼び出されますグラフィックス デバイス インターフェイス (GDI) のリソースを割り当てることをオーバーライドします。|  
|[詳細](#ondraw)|画面の表示、印刷、または印刷プレビューのドキュメントのイメージをレンダリングすると呼ばれます。 必要な実装です。|  
|[CView::OnEndPrinting](#onendprinting)|印刷ジョブの終了時に呼び出されますGDI リソースの解放をオーバーライドします。|  
|[CView::OnEndPrintPreview](#onendprintpreview)|プレビュー モードが終了したときに呼び出されます。|  
|[関数](#onprepareprinting)|ドキュメントが印刷またはプレビューされる前に呼び出されます印刷 ダイアログ ボックスを初期化するためにオーバーライドします。|  
|[のみ](#onprint)|印刷またはドキュメントのページをプレビューするには、呼び出されます。|  
|[CView::OnUpdate](#onupdate)|呼び出してそのドキュメントがされているビューに通知を変更します。|  
  
## <a name="remarks"></a>コメント  
 ビューは、ドキュメントにアタッチされ、ドキュメントとユーザー間の仲介役として機能します。 ビューは、画面またはプリンター上のドキュメントのイメージをレンダリングし、ユーザー入力をドキュメントの操作として解釈します。  
  
 ビューは、フレーム ウィンドウの子です。 複数のビューには、分割ウィンドウの場合のように、フレーム ウィンドウを共有できます。 ビュー クラス、フレーム ウィンドウ クラス、およびドキュメントのクラス間の関係を確立、`CDocTemplate`オブジェクトです。 ユーザーが新しいウィンドウを開きます。 または、既存の分割、1 つ、framework 新しいビューを構築して、ドキュメントにアタッチします。  
  
 ビューは、1 つのドキュメントにアタッチできますが、ドキュメントには、接続して、一度に複数のビューがあります: たとえば、分割ウィンドウで、またはマルチ ドキュメント インターフェイス (MDI) アプリケーションで複数の子ウィンドウで、ドキュメントが表示されます。 アプリケーションは特定のドキュメント型であるのさまざまな種類のビューをサポートすることができます。たとえば、ワード プロセッシング プログラムでは、ドキュメントの完全なテキスト ビューとセクションの見出しのみを表示するアウトライン ビューの両方を提供可能性があります。 これらのさまざまな種類のビューの配置できます個別のフレーム ウィンドウまたは&1; つのフレーム ウィンドウの分割されたペイン分割ウィンドウを使用する場合。  
  
 ビューは、さまざまなキーボード入力やマウス入力のメニュー、ツールバー、またはスクロール バーのコマンドと同様に、ドラッグ アンド ドロップを使用して入力などの入力を処理する可能性があります。 ビューは、そのフレーム ウィンドウによって転送されたコマンドを受信します。 ビューが指定されたコマンドを処理しない場合は、関連付けられたドキュメントにコマンドを転送します。 すべてのコマンドのターゲットのようには、ビューは、メッセージ マップを使用してメッセージを処理します。  
  
 ビューは、表示すると、ドキュメントのデータを変更するのではなく保存することです。 ドキュメントでは、必要な詳細データの詳細ビューを提供します。 ドキュメントのデータ メンバーを直接またはするを呼び出してビュー クラスのドキュメント クラスのメンバー関数を提供できますのアクセス許可の表示することができます。  
  
 変更内容を担当するビューを呼び出す通常ドキュメントのデータが変更されたときに、 [CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)関数を呼び出すことによって他のすべてのビューに通知すると、ドキュメント、`OnUpdate`ごとにメンバー関数。 既定の実装`OnUpdate`ビューのクライアント領域全体を無効にします。 ドキュメントの変更された部分に割り当てられたクライアント領域の領域のみを無効化するメソッドをオーバーライドすることができます。  
  
 使用する`CView`、クラスの派生、および実装、`OnDraw`画面表示を実行するメンバー関数。 使用することも`OnDraw`印刷と印刷プレビューを実行します。 フレームワークでは、印刷とドキュメントのプレビューの印刷ループを処理します。  
  
 ビューのスクロール バーのメッセージを処理する、 [CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)メンバー関数。 スクロール バーのメッセージがこれらの関数で処理を実装するか、使用することができます、`CView`クラスを派生[CScrollView](../../mfc/reference/cscrollview-class.md)スクロールを処理します。  
  
 それに`CScrollView`、Microsoft Foundation Class ライブラリから派生したその他の&9; つのクラスを提供する`CView`:  
  
- [CCtrlView](../../mfc/reference/cctrlview-class.md)ドキュメント/ビュー アーキテクチャでは、ツリー、一覧、およびリッチ エディット コントロールを使用できるビューです。  
  
- [CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)、ダイアログ ボックス コントロールでデータベースのレコードを表示するビュー。  
  
- [CEditView](../../mfc/reference/ceditview-class.md)、単純な複数行のテキスト エディターを提供するビュー。 使用することができます、 `CEditView`  ダイアログ ボックスだけでなく、ドキュメントのビュー コントロールとしてオブジェクトです。  
  
- [CFormView](../../mfc/reference/cformview-class.md)、ダイアログ ボックス コントロールを含み、ダイアログ テンプレート リソースに基づくスクロール可能なビューです。  
  
- [CListView](../../mfc/reference/clistview-class.md)、ドキュメント/ビュー アーキテクチャ リスト コントロールを利用できるビューです。  
  
- [CRecordView](../../mfc/reference/crecordview-class.md)、ダイアログ ボックス コントロールでデータベースのレコードを表示するビュー。  
  
- [CRichEditView](../../mfc/reference/cricheditview-class.md)ドキュメント/ビュー アーキテクチャ リッチ エディット コントロールを使用できるビューです。  
  
- [CScrollView](../../mfc/reference/cscrollview-class.md)、自動的にスクロールのサポートを提供するビュー。  
  
- [CTreeView](../../mfc/reference/ctreeview-class.md)、ドキュメント/ビュー アーキテクチャ ツリー コントロールを利用できるビューです。  
  
 `CView`クラスという名前の派生実装クラスにもあります**CPreviewView**、印刷プレビューを実行するために、フレームワークを使用するができます。 このクラスは、ツールバーでは、単一または二重ページのプレビューなどの印刷プレビュー ウィンドウに固有の機能のサポートを提供し、ズーム、プレビュー イメージを拡大する、します。 呼び出すかのいずれかの上書きがなくても**CPreviewView**のメンバー関数 (たとえば、印刷プレビュー モードで編集をサポートする) 場合は、印刷プレビューの独自のインターフェイスを実装するのでない限りです。 使用する方法について`CView`を参照してください[ドキュメント/ビュー アーキテクチャ](../../mfc/document-view-architecture.md)と[印刷](../../mfc/printing.md)します。 さらに、[テクニカル ノート 30:](../../mfc/tn030-customizing-printing-and-print-preview.md)印刷プレビューのカスタマイズの詳細についてです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-namecviewa--cviewcview"></a><a name="cview"></a>CView::CView  
 `CView` オブジェクトを構築します。  
  
```  
CView();
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、新しいフレーム ウィンドウが作成されるか、ウィンドウを分割時に、コンス トラクターを呼び出します。 オーバーライド、 [OnInitialUpdate](#oninitialupdate)ドキュメントをアタッチした後に、ビューを初期化するためにメンバー関数。  
  
##  <a name="a-namedoprepareprintinga--cviewdoprepareprinting"></a><a name="doprepareprinting"></a>しません  
 この関数のオーバーライドから呼び出す[OnPreparePrinting](#onprepareprinting)を印刷 ダイアログ ボックスを起動し、プリンター デバイス コンテキストを作成します。  
  
```  
BOOL DoPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="return-value"></a>戻り値  
 印刷または印刷プレビューが開始できる場合は 0 以外操作が取り消された場合は 0。  
  
### <a name="remarks"></a>コメント  
 この関数の動作は、印刷または印刷プレビューの呼び出されたかどうかによって異なります (によって指定された、**されます**のメンバー、`pInfo`パラメーター)。 この関数がで値を使用して印刷 ダイアログ ボックスを起動して、ファイルを印刷する場合、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体`pInfo`; を指す、関数は、ユーザーがダイアログ ボックスで指定したし、を使ってデバイス コンテキストを取得の設定に基づくプリンター デバイス コンテキストを作成、ユーザーがダイアログ ボックスを閉じた後、`pInfo`パラメーター。 このデバイス コンテキストは、ドキュメントの印刷に使用されます。  
  
 この関数は、現在のプリンターの設定を使用してプリンター デバイス コンテキストを作成、ファイルがプレビューされている場合このデバイス コンテキストは、プレビュー期間中にプリンターをシミュレートするために使用されます。  
  
##  <a name="a-namegetdocumenta--cviewgetdocument"></a><a name="getdocument"></a>CView::GetDocument  
 ビューのドキュメントへのポインターを取得するには、この関数を呼び出します。  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CDocument](../../mfc/reference/cdocument-class.md)ビューに関連付けられているオブジェクト。 **NULL**ビューがドキュメントにアタッチされていない場合。  
  
### <a name="remarks"></a>コメント  
 これにより、ドキュメントのメンバー関数を呼び出すことができます。  
  
##  <a name="a-nameisselecteda--cviewisselected"></a><a name="isselected"></a>CView::IsSelected  
 指定したドキュメントの項目が選択されているかどうか確認するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL IsSelected(const CObject* pDocItem) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDocItem`  
 テスト対象のドキュメントのアイテムへのポインター。  
  
### <a name="return-value"></a>戻り値  
 指定したドキュメントの項目が選択されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装**FALSE**します。 選択範囲を使用して実装している場合は、この関数をオーバーライド[CDocItem](../../mfc/reference/cdocitem-class.md)のオブジェクト。 ビューには、OLE アイテムが含まれている場合は、この関数をオーバーライドする必要があります。  
  
##  <a name="a-nameonactivateframea--cviewonactivateframe"></a><a name="onactivateframe"></a>CView::OnActivateFrame  
 ビューを含むフレーム ウィンドウがアクティブまたは非アクティブ化されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateFrame(
    UINT nState,  
    CFrameWnd* pFrameWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `nState`  
 フレーム ウィンドウがされているかどうかを示すアクティブまたは非アクティブ化します。 次の値のいずれかを指定できます。  
  
- **WA_INACTIVE**フレーム ウィンドウを非アクティブ化します。  
  
- **WA_ACTIVE**フレーム ウィンドウがアクティブ化されたいくつかのメソッドを通じて以外 (たとえば、ウィンドウの選択にキーボード インターフェイスの使用など) をクリックします。  
  
- **WA_CLICKACTIVE**フレーム ウィンドウをマウスのクリックによってアクティブ化  
  
 `pFrameWnd`  
 アクティブ化するのには、フレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 ビューに関連付けられているフレーム ウィンドウがアクティブまたは非アクティブになる場合は、特別な処理を実行する場合は、このメンバー関数をオーバーライドします。 たとえば、 [CFormView](../../mfc/reference/cformview-class.md)の保存およびフォーカスのあるコントロールを復元すると、この上書きを実行します。  
  
##  <a name="a-nameonactivateviewa--cviewonactivateview"></a><a name="onactivateview"></a>CView::OnActivateView  
 ビューがアクティブ化または非アクティブ化されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateView(
    BOOL bActivate,  
    CView* pActivateView,  
    CView* pDeactiveView);
```  
  
### <a name="parameters"></a>パラメーター  
 `bActivate`  
 表示されているかどうかを示しますがアクティブまたは非アクティブ化します。  
  
 `pActivateView`  
 アクティブ化されたビュー オブジェクトへのポインター。  
  
 `pDeactiveView`  
 非アクティブになるビュー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装では、アクティブ化されているビューにフォーカスを設定します。 ビューがアクティブ化または非アクティブになる場合は、特別な処理を実行する場合は、この関数をオーバーライドします。 たとえば、非アクティブなビューからアクティブなビューを識別する特別な視覚的手掛かりを提供する場合を確認する、`bActivate`パラメーターし、それに応じてビューの表示を更新します。  
  
 `pActivateView`と`pDeactiveView`パラメーターは、アクティブなビューが変化せずに、アプリケーションのメイン フレーム ウィンドウがアクティブ化される場合、同じビューを指して — たとえば、フォーカスが転送される間、アプリケーション内で&1; つのビューではなく、他のアプリケーションからの MDI 子ウィンドウの間で切り替えるとします。 これにより、必要な場合、そのパレットを再現するためのビューです。  
  
 これらのパラメーターが異なるとき[CFrameWnd::SetActiveView](../../mfc/reference/cframewnd-class.md#setactiveview)はどのような異なるビューを使用して呼び出された[CFrameWnd::GetActiveView](../../mfc/reference/cframewnd-class.md#getactiveview)を返します。 これは、分割ウィンドウでよく発生します。  
  
##  <a name="a-nameonbeginprintinga--cviewonbeginprinting"></a><a name="onbeginprinting"></a>値  
 `OnPreparePrinting` が呼び出された後で、印刷または印刷プレビュー ジョブの開始時にフレームワークによって呼び出されます。  
  
```  
virtual void OnBeginPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 この関数をオーバーライドして、特に印刷のために必要な GDI リソース (ペン、フォントなど) を割り当てます。 GDI オブジェクトを選択して内からデバイス コンテキスト内に、 [OnPrint](#onprint)それらを使用する各ページのメンバー関数。 同じビュー オブジェクトを使用して画面の表示と印刷の両方を実行している場合は、各表示に必要な GDI リソースに別個の変数を使用します。これにより、印刷時に画面を更新することができます。  
  
 さらに、この関数を使用して、プリンター デバイス コンテキストのプロパティに依存する初期化を実行することもできます。 たとえば、ドキュメントを印刷するために必要なページ数は、印刷ダイアログ ボックスでユーザーが指定した設定 (たとえば、ページの長さ) によって異なる可能性があります。 このような場合で文書全体の長さを指定することはできません、 [OnPreparePrinting](#onprepareprinting)メンバー関数の場合、これを通常行うよう; プリンター デバイス コンテキストがダイアログ ボックスの設定に基づいて作成されるまでに待機する必要があります。 [OnBeginPrinting](#onbeginprinting)することができる&1; つ目のオーバーライド可能な関数がアクセス、 [CDC](../../mfc/reference/cdc-class.md)のため、文書全体の長さを設定するにはこの関数から、プリンター デバイス コンテキストを表すオブジェクト。 この時点でドキュメントの長さを指定しない場合、印刷プレビュー時にスクロール バーは表示されません。  
  
##  <a name="a-nameondragentera--cviewondragenter"></a><a name="ondragenter"></a>CView::OnDragEnter  
 マウスがドロップ ターゲット ウィンドウの非スクロール領域を最初に入るときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragEnter(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ビューのドロップ領域にドラッグしています。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
 `point`  
 ビューのクライアント領域を基準と現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 値、`DROPEFFECT`列挙型で、ユーザーがこの位置では、オブジェクトを削除する場合に発生するドロップの種類を示します。 型は、通常で示される現在のキーの状態に依存`dwKeyState`します。 標準のマッピングを keystates の`DROPEFFECT`値は。  
  
- `DROPEFFECT_NONE`このウィンドウで、データ オブジェクトを削除できません。  
  
- `DROPEFFECT_LINK`**MK_CONTROL |MK_SHIFT**オブジェクトとそのサーバーの間のリンケージを作成します。  
  
- `DROPEFFECT_COPY`**MK_CONTROL**削除したオブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE`**MK_ALT**破棄されたオブジェクトのコピーを作成し、元のオブジェクトを削除します。 これは、通常、既定のドロップ効果、ビューは、このデータ オブジェクトを受け取ることができます。  
  
 詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では何を返す`DROPEFFECT_NONE`します。  
  
 以降の呼び出しを準備するには、この関数をオーバーライド、 [OnDragOver](#ondragover)メンバー関数。 この時点で後で使用できるデータ オブジェクトから必要なすべてのデータを取得する必要が、`OnDragOver`メンバー関数。 ビューは、ユーザーの視覚的フィードバックを送るには、この時点でも更新する必要があります。 詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)します。  
  
##  <a name="a-nameondragleavea--cviewondragleave"></a><a name="ondragleave"></a>CView::OnDragLeave  
 そのウィンドウの有効なドロップ エリアの外側、マウスを移動すると、ドラッグ操作中に、フレームワークが呼び出します。  
  
```  
virtual void OnDragLeave();
```  
  
### <a name="remarks"></a>コメント  
 現在のビューは、中に行った操作をクリーンアップする必要がある場合は、この関数をオーバーライド[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)オブジェクトがドラッグ アンド ドロップ中にユーザーを視覚的フィードバックを削除するなどの呼び出しです。  
  
##  <a name="a-nameondragovera--cviewondragover"></a><a name="ondragover"></a>直前  
 マウスをドロップ ターゲットのウィンドウに移動するドラッグ操作中に、フレームワークが呼び出します。  
  
```  
virtual DROPEFFECT OnDragOver(
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ドロップ ターゲット上にドラッグします。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
 `point`  
 ビューのクライアント領域を基準と現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 値、`DROPEFFECT`列挙型で、ユーザーがこの位置では、オブジェクトを削除する場合に発生するドロップの種類を示します。 示すとおり、このドロップの種類は、多くの場合に現在のキーの状態によって異なります`dwKeyState`します。 標準のマッピングを keystates の`DROPEFFECT`値は。  
  
- `DROPEFFECT_NONE`このウィンドウで、データ オブジェクトを削除できません。  
  
- `DROPEFFECT_LINK`**MK_CONTROL |MK_SHIFT**オブジェクトとそのサーバーの間のリンケージを作成します。  
  
- `DROPEFFECT_COPY`**MK_CONTROL**削除したオブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE`**MK_ALT**破棄されたオブジェクトのコピーを作成し、元のオブジェクトを削除します。 これは、通常、既定のドロップ効果、ビューは、データ オブジェクトを受け取ることができます。  
  
 詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)します。  
  
### <a name="remarks"></a>コメント  
 既定の実装は、何も返す`DROPEFFECT_NONE`します。  
  
 ドラッグ操作中にユーザーに視覚的フィードバックを提供するには、この関数をオーバーライドします。 この関数は継続的に呼び出されると、のでそれに含まれるすべてのコードを可能な限り最適化してください。 詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)します。  
  
##  <a name="a-nameondragscrolla--cviewondragscroll"></a><a name="ondragscroll"></a>CView::OnDragScroll  
 呼び出しの前に、フレームワークによって呼び出さ[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)ポイントがスクロール可能な領域があるかどうかを決定します。  
  
```  
virtual DROPEFFECT OnDragScroll(
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**します。  
  
 `point`  
 (ピクセル単位)、画面を基準と、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 値、`DROPEFFECT`列挙型で、ユーザーがこの位置では、オブジェクトを削除する場合に発生するドロップの種類を示します。 型は、通常で示される現在のキーの状態に依存`dwKeyState`します。 標準のマッピングを keystates の`DROPEFFECT`値は。  
  
- `DROPEFFECT_NONE`このウィンドウで、データ オブジェクトを削除できません。  
  
- `DROPEFFECT_LINK`**MK_CONTROL |MK_SHIFT**オブジェクトとそのサーバーの間のリンケージを作成します。  
  
- `DROPEFFECT_COPY`**MK_CONTROL**削除したオブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE`**MK_ALT**破棄されたオブジェクトのコピーを作成し、元のオブジェクトを削除します。  
  
- `DROPEFFECT_SCROLL`ドラッグ スクロール操作が発生するか、対象のビューで発生していることを示します。  
  
 詳細については、MFC Advanced Concepts サンプルを参照してください。 [OCLIENT](../../visual-cpp-samples.md)します。  
  
### <a name="remarks"></a>コメント  
 このイベントの特別な動作を提供する場合に、この関数をオーバーライドします。 既定の実装では、カーソルが各ウィンドウの枠線内の既定のスクロール領域にドラッグされると、windows が自動的にスクロールします。詳細については、記事を参照してください。[ドラッグ アンド ドロップ: ドロップ ターゲットの実装](../../mfc/drag-and-drop-implementing-a-drop-target.md)します。  
  
##  <a name="a-nameondrawa--cviewondraw"></a><a name="ondraw"></a>詳細  
 ドキュメントのイメージをレンダリングするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnDraw(CDC* pDC) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ドキュメントのイメージの描画に使用するデバイス コンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 フレームワークは画面の表示、印刷、および印刷プレビューを実行するには、この関数を呼び出しますされ、いずれの場合、別のデバイス コンテキストが渡されます。 既定の実装はありません。  
  
 ドキュメントのビューを表示するには、この関数をオーバーライドする必要があります。 使用してグラフィック デバイス インターフェイス (GDI) の呼び出しを行うことができます、 [CDC](../../mfc/reference/cdc-class.md)によって指されるオブジェクト、`pDC`パラメーター。 描画前に、デバイス コンテキストにペンやフォントなどの GDI リソースを選択し、後に選択解除できます。 デバイスに依存しない; を指定できる多くの場合、描画コードデバイスの種類が、イメージを表示する方法についての情報を必要としないことです。  
  
 描画を最適化するために呼び出す、[ため](../../mfc/reference/cdc-class.md#rectvisible)指定した四角形を描画するかどうかを確認するデバイス コンテキストのメンバー関数。 通常の画面表示と印刷を区別する必要がある場合は、呼び出し、 [IsPrinting](../../mfc/reference/cdc-class.md#isprinting)デバイス コンテキストのメンバー関数。  
  
##  <a name="a-nameondropa--cviewondrop"></a><a name="ondrop"></a>この関数  
 有効なドロップ ターゲット上でデータ オブジェクトを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrop(
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ですが、ドロップ先にドロップします。  
  
 `dropEffect`  
 ユーザーが要求したドロップ効果です。  
  
- `DROPEFFECT_COPY`削除するデータ オブジェクトのコピーを作成します。  
  
- `DROPEFFECT_MOVE`データ オブジェクトを現在のマウスの位置に移動します。  
  
- `DROPEFFECT_LINK`データ オブジェクトとサーバー間のリンクを作成します。  
  
 `point`  
 ビューのクライアント領域を基準と現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 ドロップが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では nothing を返します**FALSE**します。  
  
 ビューのクライアント領域に OLE ドロップの効果を実装するには、この関数をオーバーライドします。 使用して、データ オブジェクトを検査できる`pDataObject`クリップボード データ形式とデータ削除指定したポイントにします。  
  
> [!NOTE]
>  に対するオーバーライドがある場合、フレームワークはこの関数を呼び出しません[OnDropEx](#ondropex)このビュー クラスにします。  
  
##  <a name="a-nameondropexa--cviewondropex"></a><a name="ondropex"></a>CView::OnDropEx  
 有効なドロップ ターゲット上でデータ オブジェクトを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDropEx(
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDataObject`  
 指す、 [COleDataObject](../../mfc/reference/coledataobject-class.md)ですが、ドロップ先にドロップします。  
  
 `dropDefault`  
 現在のキーの状態に基づく既定のドロップ操作のユーザーが選択した結果。 ある可能性があります`DROPEFFECT_NONE`します。 ドロップ効果は、「解説」セクションで説明します。  
  
 `dropList`  
 ドロップ ソースがサポートする、ドロップ効果の一覧。 ビットごとの OR を使用して、ドロップ効果の値を組み合わせることができます ( **|**) 操作です。 ドロップ効果は、「解説」セクションで説明します。  
  
 `point`  
 ビューのクライアント領域を基準と現在のマウスの位置。  
  
### <a name="return-value"></a>戻り値  
 指定された位置にある削除の試行から生成されるドロップ効果`point`します。 によって示される値のいずれか必ず*dropEffectList*します。 ドロップ効果は、「解説」セクションで説明します。  
  
### <a name="remarks"></a>コメント  
 既定の実装が何もしないし、フレームワークを呼び出すことを示すためにダミーの値 (-1) を返すには、 [OnDrop](#ondrop)ハンドラー。  
  
 マウスの右ボタンのドラッグ アンド ドロップの効果を実装するには、この関数をオーバーライドします。 マウスの右ボタンのドラッグ アンド ドロップ、マウスの右ボタンが離されると通常の選択肢のメニューを表示されます。  
  
 オーバーライド`OnDropEx`マウスの右ボタンを照会する必要があります。 呼び出すことができます[GetKeyState](http://msdn.microsoft.com/library/windows/desktop/ms646301)からマウスの右ボタンの状態を保存、 [OnDragEnter](#ondragenter)ハンドラー。  
  
-   マウスの右ボタンがダウンしている場合は、オーバーライドには、ドロップ効果をドロップ ソースがサポートを提供するポップアップ メニューが表示されます。  
  
    -   調べる`dropList`をドロップ ソースがサポートされているドロップ効果を確認します。 ポップアップ メニューのこれらのアクションのみを有効にします。  
  
    -   使用[SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)に基づいて既定のアクションを設定する`dropDefault`です。  
  
    -   最後に、ポップアップ メニューからユーザーの選択によって指定されたアクションを実行します。  
  
-   マウスの右ボタンが押されていない場合、オーバーライドとして処理標準のドロップ要求します。 指定されているドロップ効果を使用して`dropDefault`します。 代わりに、オーバーライドがあることを示すダミー値 (-1) を返すことができます`OnDrop`このドロップ操作を処理します。  
  
 使用`pDataObject`を調べる、`COleDataObject`クリップボード データ形式とデータ削除指定したポイントにします。  
  
 ドロップ効果では、ドロップ操作に関連付けられたアクションについて説明します。 次のようなドロップ効果の一覧を参照してください。  
  
- `DROPEFFECT_NONE`ドロップは許可されていません。  
  
- `DROPEFFECT_COPY`コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE`移動操作が実行されます。  
  
- `DROPEFFECT_LINK`ドロップされたデータから、元のデータへのリンクが確立されます。  
  
- `DROPEFFECT_SCROLL`ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
 既定のメニュー コマンドの設定の詳細については、次を参照してください。 [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]と[CMenu::GetSafeHmenu](../../mfc/reference/cmenu-class.md#getsafehmenu)このボリュームのです。  
  
##  <a name="a-nameonendprintinga--cviewonendprinting"></a><a name="onendprinting"></a>CView::OnEndPrinting  
 ドキュメントの印刷またはプレビューした後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnEndPrinting(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、何も行いません。 割り当てられているすべての GDI リソースを解放するには、この関数をオーバーライドして、 [OnBeginPrinting](#onbeginprinting)メンバー関数。  
  
##  <a name="a-nameonendprintpreviewa--cviewonendprintpreview"></a><a name="onendprintpreview"></a>CView::OnEndPrintPreview  
 印刷プレビュー モードを終了するときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnEndPrintPreview(
    CDC* pDC,  
    CPrintInfo* pInfo,  
    POINT point,  
    CPreviewView* pView);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
 `point`  
 プレビュー モードで最後に表示されたページで、ポイントを指定します。  
  
 `pView`  
 プレビューに使用するビュー オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装、 [OnEndPrinting](#onendprinting)印刷プレビューの前に、の状態をメイン フレーム ウィンドウの開始メンバー関数を復元します。 プレビュー モードが終了した場合に、特別な処理を実行するには、この関数をオーバーライドします。 たとえば、プレビュー モードから通常の表示モードに切り替えるときに、ドキュメント内のユーザーの位置を維持する場合は、必要に応じて、スクロールによって記述された位置に、`point`パラメーターおよび`m_nCurPage`のメンバー、`CPrintInfo`構造体、`pInfo`パラメーターが指し示します。  
  
 常に、基本クラスのバージョンを呼び出す`OnEndPrintPreview`関数の末尾には通常、オーバーライドします。  
  
##  <a name="a-nameoninitialupdatea--cviewoninitialupdate"></a><a name="oninitialupdate"></a>:Oninitialupdate  
 ドキュメントにビューを最初にアタッチ後、ビューが最初に表示される前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnInitialUpdate();
```  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装、 [OnUpdate](#onupdate)ヒント情報のないメンバー関数 (つまり、0 に設定する既定値を使用して、`lHint`パラメーターと**NULL**の`pHint`パラメーター)。 ドキュメントに関する情報を必要とする&1; 回限りの初期化を実行するには、この関数をオーバーライドします。 たとえば、アプリケーションに固定サイズのドキュメントがある場合は、ドキュメントのサイズに基づくビューのスクロールの上限を初期化するためにこの関数を使用できます。 アプリケーションでは、可変サイズのドキュメントをサポートする場合に使用して[OnUpdate](#onupdate)スクロールを更新するたびに、ドキュメントにより変更制限します。  
  
##  <a name="a-nameonpreparedca--cviewonpreparedc"></a><a name="onpreparedc"></a>付け  
 前に、フレームワークによって呼び出さ、 [OnDraw](#ondraw)画面表示とする前に、メンバー関数が呼び出される、 [OnPrint](#onprint)印刷または印刷プレビュー期間中の各ページのメンバー関数が呼び出されます。  
  
```  
virtual void OnPrepareDC(
    CDC* pDC,  
    CPrintInfo* pInfo = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 ドキュメントのイメージの描画に使用するデバイス コンテキストへのポインター。  
  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)場合は、現在の印刷ジョブを記述する構造体`OnPrepareDC`印刷または印刷プレビューで呼び出しが、`m_nCurPage`メンバーは、印刷するページを指定します。 このパラメーターは**NULL**場合`OnPrepareDC`が画面表示のために呼び出されます。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は画面表示のため、関数が呼び出された場合に、何も行いません。 ただし、この関数は、派生クラスでオーバーライドなど[CScrollView](../../mfc/reference/cscrollview-class.md)のデバイス コンテキストの属性を調整するには、オーバーライドした関数の先頭に、基本クラス実装を呼び出すは常にその結果、します。  
  
 印刷関数が呼び出された場合、既定の実装に格納されているページの情報を調べて、`pInfo`パラメーター。 ドキュメントの長さが指定されていない場合`OnPrepareDC`1 ページをするためにドキュメントを前提としていて、1 つのページを印刷した後に印刷ループを停止します。 関数では、印刷のループを停止するには、`m_bContinuePrinting`構造体のメンバー **FALSE**します。  
  
 オーバーライド`OnPrepareDC`理由は次のいずれか。  
  
-   指定したページに必要なデバイス コンテキストの属性を調整します。 たとえば、マップ モードや、デバイス コンテキストの他の特性を設定する必要があればこの関数でします。  
  
-   印刷時の改ページ調整を実行します。 使用して、印刷の開始時に、ドキュメントの長さを指定する通常の[OnPreparePrinting](#onprepareprinting)メンバー関数。 ただし、かわからない場合、事前にどのくらいの期間のドキュメントは (たとえば、印刷時に、何らかの数のレコードをデータベースから)、オーバーライド`OnPrepareDC`が出力されている状態で、文書の終わりをテストします。 いいえ、印刷するドキュメントの詳細が、設定、`m_bContinuePrinting`のメンバー、`CPrintInfo`構造の**FALSE**します。  
  
-   エスケープ コードをページごとにプリンターに送信します。 エスケープ コードを送信する`OnPrepareDC`を呼び出す、**エスケープ**のメンバー関数、`pDC`パラメーター。  
  
 基本クラスを呼び出して`OnPrepareDC`オーバーライドした関数の先頭にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&183;](../../mfc/codesnippet/cpp/cview-class_1.cpp)]  
  
##  <a name="a-nameonprepareprintinga--cviewonprepareprinting"></a><a name="onprepareprinting"></a>関数  
 ドキュメントを印刷または印刷プレビューする前に、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnPreparePrinting(CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInfo`  
 指す、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)現在の印刷ジョブを記述する構造体。  
  
### <a name="return-value"></a>戻り値  
 印刷が開始する 0 以外の値印刷ジョブが取り消された場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。  
  
 印刷と印刷プレビューを有効にするには、この関数をオーバーライドする必要があります。 呼び出す、 [DoPreparePrinting](#doprepareprinting)メンバー関数を渡すこと、`pInfo`パラメーター、その戻り値を返す`DoPreparePrinting`印刷 ダイアログ ボックスを表示し、プリンター デバイス コンテキストを作成します。 メンバーに値を割り当てる場合は、既定以外の値を持つ [印刷] ダイアログ ボックスを初期化するには、`pInfo`です。 たとえば、ドキュメントの長さがわかっている場合に値を渡す、 [SetMaxPage](../../mfc/reference/cprintinfo-structure.md#setmaxpage)のメンバー関数`pInfo`呼び出す前に`DoPreparePrinting`します。 この値が表示されます。 印刷 ダイアログ ボックスの範囲 ボックス。  
  
 `DoPreparePrinting`プレビューのジョブの印刷 ダイアログ ボックスは表示されません。 印刷ジョブの印刷 ダイアログ ボックスをバイパスするには、以下を確認、**されます**のメンバー`pInfo`は**FALSE**に設定し、 **TRUE**に渡す前に`DoPreparePrinting`; リセットして**FALSE**後です。  
  
 アクセスが必要な初期化を実行する必要があるかどうか、 `CDC` (たとえば、ドキュメントの長さを指定する前にページ サイズを確認する必要がある場合)、プリンター デバイス コンテキストを表すオブジェクトの上書き、`OnBeginPrinting`メンバー関数。  
  
 値を設定する場合、 **m_nNumPreviewPages**または**関数**のメンバー、`pInfo`パラメーターを呼び出した後は`DoPreparePrinting`です。 `DoPreparePrinting`メンバー関数のセット**m_nNumPreviewPages**については、アプリケーションの値にします。INI ファイル設定と**関数**を既定値にします。  
  
### <a name="example"></a>例  
  オーバーライド`OnPreparePrinting`を呼び出すと`DoPreparePrinting`オーバーライドから、フレームワークは印刷 ダイアログ ボックスが表示され、DC のプリンターを自動的に作成できるようにします。  
  
 [!code-cpp[NVC_MFCDocView #&184;](../../mfc/codesnippet/cpp/cview-class_2.cpp)]  
  
 ドキュメントが含まれるページ数がわかっている場合は、最大のページを設定`OnPreparePrinting`呼び出す前に`DoPreparePrinting`します。 フレームワークは、[印刷] ダイアログ ボックスの"to"ボックス ページの最大数が表示されます。  
  
 [!code-cpp[NVC_MFCDocView #&185;](../../mfc/codesnippet/cpp/cview-class_3.cpp)]  
  
##  <a name="a-nameonprinta--cviewonprint"></a><a name="onprint"></a>のみ  
 印刷またはドキュメントのページをプレビューするためにフレームワークによって呼び出されます。  
  
```  
virtual void OnPrint(
    CDC* pDC,  
    CPrintInfo* pInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDC`  
 プリンター デバイス コンテキストを指し示します。  
  
 `pInfo`  
 指す、`CPrintInfo`現在の印刷ジョブを記述する構造体。  
  
### <a name="remarks"></a>コメント  
 印刷されるページごとに、フレームワークからこの関数呼び出し直後後、 [OnPrepareDC](#onpreparedc)メンバー関数。 印刷されるページが指定された、`m_nCurPage`のメンバー、 [CPrintInfo](../../mfc/reference/cprintinfo-structure.md)構造体`pInfo`をポイントします。 既定の実装、 [OnDraw](#ondraw)メンバー関数をプリンター デバイス コンテキストを渡します。  
  
 次の理由により、この関数をオーバーライドします。  
  
-   マルチページ ドキュメントの印刷ができるようにします。 現在印刷中のページに対応するドキュメントの一部のみを表示します。 使用している場合`OnDraw`レンダリングを実行する文書の適切な部分だけが出力されるよう、ビューポートの原点を調整できます。  
  
-   (つまり、アプリケーションは、WYSIWYG ではない) 場合、画面イメージとは異なる印刷されたイメージにします。 プリンター デバイス コンテキストを渡す代わりに`OnDraw`、デバイス コンテキストを使用して、画面に表示されない属性を使用してイメージをレンダリングします。  
  
     画面表示のために使用しない印刷に GDI リソースが必要な場合は、描画前に、デバイス コンテキストに選択しは後で選択を解除します。 これらの GDI リソースを割り当てる必要がある[OnBeginPrinting](#onbeginprinting)で公開される[OnEndPrinting](#onendprinting)します。  
  
-   ヘッダーまたはフッターを実装します。 引き続き使用できます`OnDraw`描画するために印刷できる領域を制限しています。  
  
 なお、 **m_rectDraw**のメンバー、`pInfo`パラメーターは、論理ユニットのページの印刷可能な領域を表します。  
  
 呼び出す必要はありません`OnPrepareDC`のオーバーライドで`OnPrint`; は、フレームワークによって`OnPrepareDC`呼び出す前に自動的に`OnPrint`します。  
  
### <a name="example"></a>例  
 次に、オーバーライドのスケルトン`OnPrint`関数。  
  
 [!code-cpp[NVC_MFCDocView #&186;](../../mfc/codesnippet/cpp/cview-class_4.cpp)]  
  
 別の例では、次を参照してください。 [CRichEditView::PrintInsideRect](../../mfc/reference/cricheditview-class.md#printinsiderect)します。  
  
##  <a name="a-nameonscrolla--cviewonscroll"></a><a name="onscroll"></a>CView::OnScroll  
 スクロールするかどうかを調べるためにフレームワークによって呼び出されることができます。  
  
```  
virtual BOOL OnScroll(
    UINT nScrollCode,  
    UINT nPos,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nScrollCode`  
 スクロール バーのコードをユーザーを示すには、要求のスクロールします。 このパラメーターは&2; つの部分で構成されます。 水平方向にスクロール発生の種類を決定する下位バイトと垂直方向にスクロール発生の型を決定する上位バイト。  
  
- **SB_BOTTOM**一番下までスクロールします。  
  
- **SB_LINEDOWN**が&1; 行下へスクロールします。  
  
- **SB_LINEUP**を&1; つの行にスクロールします。  
  
- **SB_PAGEDOWN**&1; つのページを下へスクロールします。  
  
- **SB_PAGEUP**を&1; つのページをスクロールします。  
  
- **SB_THUMBTRACK**の指定位置にドラッグがスクロール ボックス。 現在の位置を指定`nPos`します。  
  
- **SB_TOP**上部までスクロールします。  
  
 `nPos`  
 現在のスクロール ボックスの位置が含まれる場合、スクロール バーのコードは**SB_THUMBTRACK**。 それ以外の場合は使用されません。 初期スクロールの範囲に応じて`nPos`が負の数およびにキャストする必要があります、`int`必要な場合です。  
  
 `bDoScroll`  
 指定されたスクロール動作を実際に行うかどうかを決定します。 場合**true の場合、**スクロールする必要があります。 場合行う、 **FALSE**、スクロールが実行し、します。  
  
### <a name="return-value"></a>戻り値  
 場合`bDoScroll`は**TRUE**とビューをスクロール実際には、返されるは 0 以外。 それ以外の場合 0 です。 場合`bDoScroll`は**FALSE**が返された場合、値を返す`bDoScroll`された**TRUE**スクロールを実際にはない場合でも、します。  
  
### <a name="remarks"></a>コメント  
 1 つのケースで、この関数がフレームワークによって呼び出されます`bDoScroll`設定**TRUE**ビューがスクロール バーのメッセージを受信するとします。 この場合、ビューを実際にスクロールする必要があります。 その他の場合は、この関数が呼び出されます`bDoScroll`設定**FALSE** OLE アイテムが最初にドロップときのドロップ ターゲットの自動スクロール領域にスクロール実際に行われる前にします。 この場合、する必要があります実際にはスクロールされませんビュー。  
  
##  <a name="a-nameonscrollbya--cviewonscrollby"></a><a name="onscrollby"></a>CView::OnScrollBy  
 ビューの現在の境界に対して OLE アイテムをドラッグして、または垂直または水平スクロール バーを操作することによって、ドキュメントの存在のビューを超える領域を表示するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnScrollBy(
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `sizeScroll`  
 ピクセル数は、水平方向および垂直方向にスクロールします。  
  
 `bDoScroll`  
 ビューのスクロール行うかどうかを決定します。 場合**true の場合、**場合; スクロールに配置し、 **FALSE**、スクロールは発生しません。  
  
### <a name="return-value"></a>戻り値  
 ビューがこの方向にスクロールするできた場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 派生クラスでは、このメソッドは、ビューは、ユーザーが要求され、必要に応じて新しい領域を更新し、方向にスクロール可能かどうかを確認します。 この関数は自動的に呼び出されます[CWnd::OnHScroll](../../mfc/reference/cwnd-class.md#onhscroll)と[ために](../../mfc/reference/cwnd-class.md#onvscroll)を実際のスクロールの要求を実行します。  
  
 このメソッドの既定の実装では、ビューは変更しませんが呼び出されない場合、ビューをスクロールするのには`CScrollView`-クラスを派生します。  
  
 ドキュメントの幅または高さがピクセルを超えると、過去の 32767 スクロールために失敗します`OnScrollBy`に、無効なという`sizeScroll`引数。  
  
##  <a name="a-nameonupdatea--cviewonupdate"></a><a name="onupdate"></a>CView::OnUpdate  
 ビューのドキュメントが変更された後に、フレームワークによって呼び出されますこの関数は[CDocument::UpdateAllViews](../../mfc/reference/cdocument-class.md#updateallviews)と、それらの変更を反映するように表示を更新します。  
  
```  
virtual void OnUpdate(
    CView* pSender,  
    LPARAM lHint,  
    CObject* pHint);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSender`  
 ドキュメントを変更するビューへのポインターまたは**NULL**場合、すべてのビューを更新します。  
  
 `lHint`  
 変更についての情報が含まれています。  
  
 `pHint`  
 変更についての情報を格納するオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装によってもと呼ばれる[OnInitialUpdate](#oninitialupdate)します。 既定の実装には、全体のクライアント領域で、ときに描画するためにマークが無効になります。 次`WM_PAINT`メッセージを受信します。 ドキュメントの変更部分に割り当てられた領域のみを更新する場合は、この関数をオーバーライドします。 これを行うには、ヒントのパラメーターを使用して変更についての情報を渡す必要があります。  
  
 使用する`lHint`ビットマスクまたは列挙型では、通常、特別なヒントの値を定義、およびドキュメントをこれらの値のいずれかを渡します。 使用する`pHint`からヒント クラスを派生[CObject](../../mfc/reference/cobject-class.md)ドキュメントをオーバーライドする場合のヒントにポインターを渡す`OnUpdate`を使用して、[使うため](../../mfc/reference/cobject-class.md#iskindof)ヒント オブジェクトの実行時の型を調べます。  
  
 通常実行しないでいずれかから直接描画`OnUpdate`します。 代わりに、デバイス座標で、更新を要求する領域を示す四角形を決定します。この四角形を渡す[エディット](../../mfc/reference/cwnd-class.md#invalidaterect)します。 これを次に行うことが原因で、 [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213)メッセージを受信します。  
  
 場合`lHint`は 0 と`pHint`は**NULL**ドキュメントが汎用的な更新の通知を送信します。 ビューは、汎用的な更新の通知を受信した場合、または、ヒントをデコードできない場合は、クライアント領域全体を無効にします。  
  
## <a name="see-also"></a>関連項目  
 [MFC のサンプルは](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)   
 [CDC クラス](../../mfc/reference/cdc-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [CDocument クラス](../../mfc/reference/cdocument-class.md)

