---
title: "CFrameWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFrameWnd
dev_langs:
- C++
helpviewer_keywords:
- frame window classes, base class
- single document interface (SDI), frame windows
- frame windows, creating
- CFrameWnd class
ms.assetid: e2220aba-5bf4-4002-b960-fbcafcad01f1
caps.latest.revision: 21
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
ms.openlocfilehash: a8df28ed10208973832476b68140594c206bc22b
ms.lasthandoff: 02/24/2017

---
# <a name="cframewnd-class"></a>CFrameWnd クラス
ウィンドウを管理するメンバーと共に、Windows のシングル ドキュメント インターフェイス (SDI: Single Document Interface) のオーバーラップ フレーム ウィンドウまたはポップアップ フレーム ウィンドウの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CFrameWnd : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CFrameWnd::CFrameWnd](#cframewnd)|`CFrameWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFrameWnd::ActivateFrame](#activateframe)|ユーザーに表示され、使用可能なフレームを加えます。|  
|[CFrameWnd::BeginModalState](#beginmodalstate)|フレーム ウィンドウをモーダルに設定します。|  
|[CFrameWnd::Create](#create)|作成し、初期化に関連付けられている Windows のフレーム ウィンドウへの呼び出し、`CFrameWnd`オブジェクトです。|  
|[CFrameWnd::CreateView](#createview)|派生していない、フレーム内でビューを作成`CView`します。|  
|[CFrameWnd::DockControlBar](#dockcontrolbar)|コントロール バーをドッキングします。|  
|[CFrameWnd::EnableDocking](#enabledocking)|により、コントロール バーをドッキングできます。|  
|[CFrameWnd::EndModalState](#endmodalstate)|フレーム ウィンドウのモーダルの状態を終了します。 により、すべてのウィンドウで無効になっている`BeginModalState`します。|  
|[切り離すには](#floatcontrolbar)|コントロール バーを寄せて配置します。|  
|[CFrameWnd::GetActiveDocument](#getactivedocument)|アクティブなを返す**CDocument**オブジェクトです。|  
|[CFrameWnd::GetActiveFrame](#getactiveframe)|アクティブなを返す`CFrameWnd`オブジェクトです。|  
|[CFrameWnd::GetActiveView](#getactiveview)|アクティブなを返す`CView`オブジェクトです。|  
|[CFrameWnd::GetControlBar](#getcontrolbar)|コントロール バーを取得します。|  
|[CFrameWnd::GetDockState](#getdockstate)|フレーム ウィンドウのドッキング状態を取得します。|  
|[CFrameWnd::GetMenuBarState](#getmenubarstate)|現在の MFC アプリケーションのメニューの表示状態を取得します。|  
|[CFrameWnd::GetMenuBarVisibility](#getmenubarvisibility)|現在の MFC アプリケーションのメニューの既定の動作を表示または非表示にするかどうかを示します。|  
|[CFrameWnd::GetMessageBar](#getmessagebar)|ステータス バーのフレーム ウィンドウに属するへのポインターを返します。|  
|[CFrameWnd::GetMessageString](#getmessagestring)|コマンド ID に対応するメッセージを取得します。|  
|[CFrameWnd::GetTitle](#gettitle)|関連するコントロール バーのタイトルを取得します。|  
|[CFrameWnd::InitialUpdateFrame](#initialupdateframe)|により、`OnInitialUpdate`メンバー関数が呼び出されるフレーム ウィンドウのすべてのビューに属しています。|  
|[CFrameWnd::InModalState](#inmodalstate)|フレーム ウィンドウがモーダル状態にするかどうかどうかを示す値を返します。|  
|[CFrameWnd::IsTracking](#istracking)|分割バーが移動中かどうかを判断します。|  
|[CFrameWnd::LoadAccelTable](#loadacceltable)|アクセラレータ テーブルの読み込みの呼び出しです。|  
|[CFrameWnd::LoadBarState](#loadbarstate)|コントロール バーの設定を復元する呼び出しです。|  
|[CFrameWnd::LoadFrame](#loadframe)|リソースの情報からフレーム ウィンドウを動的に作成する呼び出しです。|  
|[CFrameWnd::NegotiateBorderSpace](#negotiateborderspace)|フレーム ウィンドウの境界領域をネゴシエートします。|  
|[CFrameWnd::OnBarCheck](#onbarcheck)|指定したコントロール バーで、アクションが実行されるたびに呼び出されます。|  
|[受信](#oncontexthelp)|埋め込み先アイテムについては、shift キーを押しながら f1 キーを処理します。|  
|[CFrameWnd::OnSetPreviewMode](#onsetpreviewmode)|印刷プレビュー モードとの間は、アプリケーションのメイン フレーム ウィンドウを設定します。|  
|[CFrameWnd::OnUpdateControlBarMenu](#onupdatecontrolbarmenu)|関連するメニューが更新されたときに、フレームワークによって呼び出されます。|  
|[表示](#recalclayout)|コントロール バーの位置を変更、`CFrameWnd`オブジェクトです。|  
|[CFrameWnd::SaveBarState](#savebarstate)|コントロール バーの設定を保存する呼び出しです。|  
|[CFrameWnd::SetActivePreviewView](#setactivepreviewview)|リッチ プレビュー用のアクティブなビューに指定されたビューを指定します。|  
|[CFrameWnd::SetActiveView](#setactiveview)|アクティブな設定`CView`オブジェクトです。|  
|[CFrameWnd::SetDockState](#setdockstate)|メイン ウィンドウ内のフレーム ウィンドウをドッキングするのにを呼び出します。|  
|[CFrameWnd::SetMenuBarState](#setmenubarstate)|非表示または表示は、現在の MFC アプリケーションのメニューの表示状態を設定します。|  
|[CFrameWnd::SetMenuBarVisibility](#setmenubarvisibility)|非表示または非表示には、現在の MFC アプリケーションで、メニューの既定の動作を設定します。|  
|[CFrameWnd::SetMessageText](#setmessagetext)|標準的なステータス バーのテキストを設定します。|  
|[CFrameWnd::SetProgressBarPosition](#setprogressbarposition)|タスク バーに表示される Windows 7 の進行状況バーの現在位置を設定します。|  
|[CFrameWnd::SetProgressBarRange](#setprogressbarrange)|タスク バーに表示される Windows 7 の進行状況バーの範囲を設定します。|  
|[CFrameWnd::SetProgressBarState](#setprogressbarstate)|タスク バー ボタンに表示される進行状況インジケーターの状態の種類を設定します。|  
|[CFrameWnd::SetTaskbarOverlayIcon](#settaskbaroverlayicon)|オーバーロードされます。 アプリケーションの状態や、ユーザーへの通知を示すためにタスク バー ボタンにオーバーレイを適用します。|  
|[CFrameWnd::SetTitle](#settitle)|関連するコントロール バーのタイトルを設定します。|  
|[CFrameWnd::ShowControlBar](#showcontrolbar)|コントロール バーを表示する呼び出しです。|  
|[CFrameWnd::ShowOwnedWindows](#showownedwindows)|子孫であるすべてのウィンドウを表示、`CFrameWnd`オブジェクトです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CFrameWnd::OnCreateClient](#oncreateclient)|フレームのクライアント ウィンドウを作成します。|  
|[CFrameWnd::OnHideMenuBar](#onhidemenubar)|現在の MFC アプリケーションのメニューが非表示に呼び出されます。|  
|[CFrameWnd::OnShowMenuBar](#onshowmenubar)|現在の MFC アプリケーションのメニューが表示される前に呼び出されます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CFrameWnd::m_bAutoMenuEnable](#m_bautomenuenable)|自動コントロールでは、有効にして、メニュー項目の機能を無効にします。|  
|[CFrameWnd::rectDefault](#rectdefault)|静的に渡す`CRect`を作成する際に、パラメーターとして、`CFrameWnd`ウィンドウの初期サイズと位置を選択するウィンドウを許可するオブジェクト。|  
  
## <a name="remarks"></a>コメント  
 アプリケーション用の便利なフレーム ウィンドウを作成するには、派生クラスを`CFrameWnd`します。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 フレーム ウィンドウを作成する&3; つの方法があります。  
  
-   使用してページを直接構築[作成](#create)します。  
  
-   使用してページを直接構築[LoadFrame](#loadframe)します。  
  
-   間接的に構築ドキュメント テンプレートを使用します。  
  
 いずれかを呼び出す前に**作成**または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウのオブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に**作成**を使用してウィンドウ クラスを登録することも、 [AfxRegisterWndClass](../../mfc/reference/application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。  
  
 使用して、**作成**引数を渡すフレームの作成パラメーターに直接のメンバー関数。  
  
 `LoadFrame`も少ない数の引数を必要と**作成**、し、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースから、既定の値のほとんどを取得します。 アクセスできる`LoadFrame`、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、 **IDR_MAINFRAME**)。  
  
 ときに、`CFrameWnd`オブジェクトには、ビューやドキュメントが含まれています、これらは間接的に作成、プログラマが直接は代わりに、フレームワークができます。 `CDocTemplate`オブジェクトは、フレームの作成、コンテナーのビューの作成と適切なドキュメント ビューの接続を調整します。 パラメーター、`CDocTemplate`コンス トラクターを指定、 `CRuntimeClass`&3; つのクラスの関係 (ドキュメント、フレーム、および表示)。 A`CRuntimeClass`オブジェクトは動的に (たとえば、新しいファイルまたは複数ドキュメント インターフェイス (MDI) の新しいウィンドウ を使用して) を指定すると、ユーザーが新しいフレームを作成するために、フレームワークによって使用されます。  
  
 フレーム ウィンドウ クラスから派生`CFrameWnd`で宣言する必要があります`DECLARE_DYNCREATE`上記の順序で`RUNTIME_CLASS`正常に動作するためのメカニズムです。  
  
 A `CFrameWnd` Windows の一般的なアプリケーションでのメイン ウィンドウの次の関数を実行する既定の実装が含まれています。  
  
-   A`CFrameWnd`フレーム ウィンドウの追跡は、Windows のアクティブなウィンドウまたは現在の入力フォーカスの独立した現在アクティブなビューです。 アクティブなビューを呼び出して通知を受け取る、フレームが再アクティブ化された`CView::OnActivateView`します。  
  
-   コマンドのメッセージが処理するものを含む、多くの一般的なフレーム通知メッセージ、 `OnSetFocus`、 `OnHScroll`、および`OnVScroll`関数の`CWnd`、委任されている、`CFrameWnd`フレーム ウィンドウは、現在アクティブなビューをします。  
  
-   現在アクティブなビュー (または MDI フレームの場合の現在アクティブな MDI 子フレーム ウィンドウ) には、フレーム ウィンドウのキャプションを決定できます。 この機能はオフにして無効にすることができます、 **FWS_ADDTOTITLE**フレーム ウィンドウのスタイル ビットです。  
  
-   A`CFrameWnd`フレーム ウィンドウは、コントロール バー、ビュー、およびその他の子ウィンドウ フレーム ウィンドウのクライアント領域内の位置を管理します。 フレーム ウィンドウは、ツールバーおよびその他のコントロール バーのボタンのアイドル時間の更新も行います。 A`CFrameWnd`フレーム ウィンドウは、ツールバーとステータス バーの内外での切り替え用のコマンドの既定の実装もあります。  
  
-   A`CFrameWnd`フレーム ウィンドウはメインのメニュー バーを管理します。 フレーム ウィンドウを使用して、ポップアップ メニューが表示されたら、 **UPDATE_COMMAND_UI**メニュー項目を有効、無効になっている、またはチェックを決定するためのメカニズムです。 ユーザーは、メニュー項目を選択するときに、フレーム ウィンドウは、そのコマンドのメッセージ文字列を使用ステータス バーを更新します。  
  
-   A`CFrameWnd`フレーム ウィンドウがキーボード アクセラレータを自動的に変換し、オプションのアクセラレータ テーブルです。  
  
-   A`CFrameWnd`フレーム ウィンドウで設定されたオプションのヘルプ ID を持つ`LoadFrame`状況依存のヘルプに使用されます。 フレーム ウィンドウは、セミモーダル状態 (shift キーを押しながら f1 キー) の状況依存のヘルプや印刷プレビュー モードなどの主要な orchestrator です。  
  
-   A`CFrameWnd`フレーム ウィンドウがフレーム ウィンドウにファイル マネージャーからのドラッグ アンド ドロップ ファイルを開きます。 ファイル拡張子が登録されている、アプリケーションに関連付けられている場合は、フレーム ウィンドウ要求に応答するダイナミック データ エクス (チェンジ DDE) オープンまたは、ユーザーはファイル マネージャーでデータ ファイルを開くときに発生する、 **ShellExecute** Windows 関数が呼び出されます。  
  
-   フレーム ウィンドウがアプリケーションのメイン ウィンドウの場合 (つまり、 `CWinThread::m_pMainWnd`)、ユーザーは、アプリケーションを終了すると、フレーム ウィンドウには、ユーザー、変更したドキュメントを保存するメッセージが表示されます (の`OnClose`と`OnQueryEndSession`)。  
  
-   フレーム ウィンドウがアプリケーションのメイン ウィンドウの場合は、フレーム ウィンドウ、WinHelp を実行するためのコンテキストです。 WINHELP をシャット ダウンは、フレーム ウィンドウを終了します。このアプリケーションのヘルプを起動した場合は、EXE します。  
  
 C++ を使用しないで**削除**フレーム ウィンドウを破棄する演算子です。 代わりに、 `CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ オブジェクトを削除します。 ユーザーが、既定のフレーム ウィンドウを閉じたときに`OnClose`ハンドラーが呼び出す`DestroyWindow`します。  
  
 詳細については`CFrameWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CFrameWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="a-nameactivateframea--cframewndactivateframe"></a><a name="activateframe"></a>CFrameWnd::ActivateFrame  
 このメンバー関数を呼び出してアクティブ化しが表示され、使用可能なユーザーに、フレーム ウィンドウを復元します。  
  
```  
virtual void ActivateFrame(int nCmdShow = -1);
```  
  
### <a name="parameters"></a>パラメーター  
 `nCmdShow`  
 渡すパラメーターを指定[また](../../mfc/reference/cwnd-class.md#showwindow)します。 既定では、フレームが表示され、不適切に復元します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は通常、DDE、OLE、フレーム ウィンドウまたはその内容を表示することがあります、ユーザーにその他のイベントなどの非ユーザー インターフェイス イベントの後に呼び出されます。  
  
 既定の実装、フレームをアクティブに Z オーダーの先頭に表示および必要に応じて、アプリケーションのメイン フレーム ウィンドウと同じ手順を実行します。  
  
 フレームがアクティブにする方法を変更するには、この関数をオーバーライドします。 たとえば、MDI 子ウィンドウを最大化を強制できます。 適切な機能を追加し、明示的な基底クラスのバージョンを呼び出す`nCmdShow`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#1;](../../mfc/reference/codesnippet/cpp/cframewnd-class_1.cpp)]  
  
##  <a name="a-namebeginmodalstatea--cframewndbeginmodalstate"></a><a name="beginmodalstate"></a>CFrameWnd::BeginModalState  
 フレーム ウィンドウをモーダルにします。  
  
```  
virtual void BeginModalState();
```  
  
##  <a name="a-namecframewnda--cframewndcframewnd"></a><a name="cframewnd"></a>CFrameWnd::CFrameWnd  
 構築、`CFrameWnd`オブジェクトは、表示されるフレーム ウィンドウを作成しません。  
  
```  
CFrameWnd();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す**作成**表示のウィンドウを作成します。  
  
##  <a name="a-namecreatea--cframewndcreate"></a><a name="create"></a>CFrameWnd::Create  
 作成し、初期化に関連付けられている Windows のフレーム ウィンドウへの呼び出し、`CFrameWnd`オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CWnd* pParentWnd = NULL,  
    LPCTSTR lpszMenuName = NULL,  
    DWORD dwExStyle = 0,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 Windows クラスの名前を示す文字の null で終わる文字列へのポインター。 クラス名に登録されている任意の名前を指定できます、`AfxRegisterWndClass`グローバル関数、または**RegisterClass** Windows の機能です。 場合**NULL**、定義済みの既定値を使用して`CFrameWnd`属性です。  
  
 `lpszWindowName`  
 ウィンドウの名前を表す文字の null で終わる文字列へのポインター。 タイトル バーのテキストとして使用します。  
  
 `dwStyle`  
 期間を指定[スタイル](../../mfc/reference/window-styles.md)属性です。 含める、 **FWS_ADDTOTITLE**する場合は、ウィンドウで表されるドキュメントの名前を自動的に表示するタイトル バーのスタイルを設定します。  
  
 `rect`  
 サイズとウィンドウの位置を指定します。 `rectDefault`値により、Windows のサイズと新しいウィンドウの位置を指定します。  
  
 `pParentWnd`  
 このフレーム ウィンドウの親ウィンドウを指定します。 このパラメーターを指定する必要があります**NULL**最上位のフレーム ウィンドウです。  
  
 *lpszMenuName*  
 ウィンドウを使用する] メニューの [リソースの名前を識別します。 使用**されるときは**メニューに文字列の代わりに整数 ID がある場合。 このパラメーターを指定できます**NULL**します。  
  
 `dwExStyle`  
 ウィンドウの拡張[スタイル](../../mfc/reference/extended-window-styles.md)属性です。  
  
 `pContext`  
 ポインターを指定する[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターを指定できます**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 初期化が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 構築、 `CFrameWnd`&2; つのステップ内のオブジェクト。 最初に、構築コンス トラクターを呼び出す、`CFrameWnd`オブジェクト、し、呼び出す**作成**、ウィンドウ フレームを作成およびそれにアタッチする、`CFrameWnd`オブジェクトです。 **作成**ウィンドウのクラス名やウィンドウ名を初期化し、スタイル、親、および関連付けられている menu の既定値を登録します。  
  
 使用`LoadFrame`なく**作成**フレーム ウィンドウを引数を指定する代わりに、そのリソースから読み込めません。  
  
##  <a name="a-namecreateviewa--cframewndcreateview"></a><a name="createview"></a>CFrameWnd::CreateView  
 呼び出す`CreateView`フレーム内でビューを作成します。  
  
```  
CWnd* CreateView(
    CCreateContext* pContext,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 ビュー、およびドキュメントの種類を指定します。  
  
 `nID`  
 ビューの ID 番号。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CWnd`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 「ビュー」を作成するこのれないメンバー関数を使用して`CView`-フレーム内で派生します。 呼び出した後`CreateView`、手動でアクティブにビューを設定し、表示されるように設定する必要があります。 によってこれらのタスクが自動的に実行されない`CreateView`します。  
  
##  <a name="a-namedockcontrolbara--cframewnddockcontrolbar"></a><a name="dockcontrolbar"></a>CFrameWnd::DockControlBar  
 フレーム ウィンドウにドッキングするコントロール バーが発生します。  
  
```  
void DockControlBar(
    CControlBar* pBar,  
    UINT nDockBarID = 0,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBar`  
 ドッキング コントロール バーへのポインター。  
  
 `nDockBarID`  
 フレーム ウィンドウにドッキングのどの辺を決定します。 0 または 1 つ以上の次を指定できます。  
  
- `AFX_IDW_DOCKBAR_TOP`フレーム ウィンドウの上の辺にドッキングします。  
  
- **AFX_IDW_DOCKBAR_BOTTOM**フレーム ウィンドウの下部にドッキングします。  
  
- `AFX_IDW_DOCKBAR_LEFT`フレーム ウィンドウの左側にドッキングします。  
  
- `AFX_IDW_DOCKBAR_RIGHT`フレーム ウィンドウの右側にドッキングします。  
  
 0 の場合、コントロール バーがドッキング先フレーム ウィンドウの任意の辺にドッキングできます。  
  
 `lpRect`  
 コントロール バーをドッキングする、移行先のフレーム ウィンドウの非クライアント領域で、画面の座標を判断します。  
  
### <a name="remarks"></a>コメント  
 コントロール バーは両方への呼び出しで指定されたフレーム ウィンドウの横のいずれかにドッキングする[CControlBar::EnableDocking](../../mfc/reference/ccontrolbar-class.md#enabledocking)と[CFrameWnd::EnableDocking](#enabledocking)します。 選択された側はによって決まります`nDockBarID`します。  
  
##  <a name="a-nameenabledockinga--cframewndenabledocking"></a><a name="enabledocking"></a>CFrameWnd::EnableDocking  
 フレーム ウィンドウのドッキング コントロール バーを有効にするには、この関数を呼び出します。  
  
```  
void EnableDocking(DWORD dwDockStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwDockStyle`  
 フレーム ウィンドウのどちら側になるドッキング コントロール バー用のサイトを指定します。 次の&1; つ以上を指定できます。  
  
- `CBRS_ALIGN_TOP`により、クライアント領域の上部にドッキングできます。  
  
- `CBRS_ALIGN_BOTTOM`により、クライアント領域の下部にドッキングできます。  
  
- `CBRS_ALIGN_LEFT`により、クライアント領域の左側にドッキングできます。  
  
- `CBRS_ALIGN_RIGHT`により、クライアント領域の右側にドッキングできます。  
  
- `CBRS_ALIGN_ANY`により、クライアント領域の任意の辺にドッキングできます。  
  
### <a name="remarks"></a>コメント  
 次の順序でフレーム ウィンドウの側に既定では、コントロール バーがドッキングされる: top、bottom、left、right です。  
  
### <a name="example"></a>例  
  例を参照してください[用意されて](../../mfc/reference/ctoolbar-class.md#create)します。  
  
##  <a name="a-nameendmodalstatea--cframewndendmodalstate"></a><a name="endmodalstate"></a>CFrameWnd::EndModalState  
 フレーム ウィンドウをモーダルからモードレスに変更します。  
  
```  
virtual void EndModalState();
```  
  
### <a name="remarks"></a>コメント  
 `EndModalState`により、すべてのウィンドウで無効になっている[BeginModalState](#beginmodalstate)します。  
  
##  <a name="a-namefloatcontrolbara--cframewndfloatcontrolbar"></a><a name="floatcontrolbar"></a>切り離すには  
 この関数では、フレーム ウィンドウにドッキングされずに、コントロール バーが発生します。  
  
```  
void FloatControlBar(
    CControlBar* pBar,  
    CPoint point,  
    DWORD dwStyle = CBRS_ALIGN_TOP);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBar`  
 フローティングするコントロール バーへのポインター。  
  
 `point`  
 内の位置を画面座標コントロール バーの左上隅を配置する場所。  
  
 `dwStyle`  
 新しいフレーム ウィンドウ内で、コントロール バーを水平方向または垂直方向に配置するかどうかを指定します。 次のいずれかを指定できます。  
  
- `CBRS_ALIGN_TOP`コントロール バーの方向を垂直方向にするには。  
  
- `CBRS_ALIGN_BOTTOM`コントロール バーの方向を垂直方向にするには。  
  
- `CBRS_ALIGN_LEFT`コントロール バーが横向きにします。  
  
- `CBRS_ALIGN_RIGHT`コントロール バーが横向きにします。  
  
 水平および垂直の両方の方向を指定するスタイルが渡された場合、ツールバーになります指向水平方向にします。  
  
### <a name="remarks"></a>コメント  
 通常、これは、アプリケーションの起動時にプログラムが前回の実行からの設定を復元する場合。  
  
 この関数は、フレームワークによって、ユーザーがドッキングの利用可能な場所に、コントロール バーをドラッグするときにマウスの左ボタンを離すドロップ操作が発生します。  
  
##  <a name="a-namegetactivedocumenta--cframewndgetactivedocument"></a><a name="getactivedocument"></a>CFrameWnd::GetActiveDocument  
 現在へのポインターを取得するには、このメンバー関数を呼び出す**CDocument**現在アクティブなビューにアタッチします。  
  
```  
virtual CDocument* GetActiveDocument();
```  
  
### <a name="return-value"></a>戻り値  
 現在へのポインター [CDocument](../../mfc/reference/cdocument-class.md)します。 現在のドキュメントがない場合は、返す**NULL**します。  
  
##  <a name="a-namegetactiveframea--cframewndgetactiveframe"></a><a name="getactiveframe"></a>CFrameWnd::GetActiveFrame  
 マルチ ドキュメント インターフェイス (MDI) 子ウィンドウの MDI フレーム ウィンドウのアクティブなへのポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CFrameWnd* GetActiveFrame();
```  
  
### <a name="return-value"></a>戻り値  
 アクティブな MDI 子ウィンドウへのポインター。 かどうか、アプリケーションは、SDI アプリケーション、または MDI フレーム ウィンドウは、暗黙的にアクティブだったドキュメントを持たない**この**ポインターが返されます。  
  
### <a name="remarks"></a>コメント  
 アクティブな MDI 子がないかどうか、またはアプリケーションは、暗黙的なシングル ドキュメント インターフェイス (SDI)**この**ポインターが返されます。  
  
##  <a name="a-namegetactiveviewa--cframewndgetactiveview"></a><a name="getactiveview"></a>CFrameWnd::GetActiveView  
 フレーム ウィンドウにアタッチされているアクティブなビュー (もしあれば) へのポインターを取得するには、このメンバー関数を呼び出します ( `CFrameWnd`)。  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在へのポインター [CView](../../mfc/reference/cview-class.md)します。 現在のビューがない場合は、返す**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この関数が返す**NULL** MDI メイン フレーム ウィンドウに対して呼び出したときに ( `CMDIFrameWnd`)。 MDI アプリケーションでは、MDI メイン フレーム ウィンドウに関連付けられているビューはありません。 代わりに、それぞれ個別の子ウィンドウ ( `CMDIChildWnd`) が&1; つまたは複数の関連する表示します。 MDI アプリケーションでアクティブなビューは、まずアクティブな MDI 子ウィンドウを検索し、その子ウィンドウのアクティブなビューを検索して取得できます。 関数を呼び出してアクティブな MDI 子ウィンドウが見つかりません`MDIGetActive`または**GetActiveFrame**次に示すようにします。  
  
 [!code-cpp[NVC_MFCWindowing&#2;](../../mfc/reference/codesnippet/cpp/cframewnd-class_2.cpp)]  
  
##  <a name="a-namegetcontrolbara--cframewndgetcontrolbar"></a><a name="getcontrolbar"></a>CFrameWnd::GetControlBar  
 呼び出す`GetControlBar`ID に関連付けられているコントロール バーにアクセスするには  
  
```  
CControlBar* GetControlBar(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 コントロール バーの ID 番号。  
  
### <a name="return-value"></a>戻り値  
 ID に関連付けられているコントロール バーへのポインター  
  
### <a name="remarks"></a>コメント  
 `nID`パラメーターに渡される一意の識別子を参照、**作成**コントロール バーのメソッドです。 コントロール バーの詳細については、トピックを参照してください[コントロール バー](../../mfc/control-bars.md)します。  
  
 `GetControlBar`固定されていない、したがってが現在存在しない子ウィンドウ フレームの場合でも、コントロール バーを戻ります。  
  
##  <a name="a-namegetdockstatea--cframewndgetdockstate"></a><a name="getdockstate"></a>CFrameWnd::GetDockState  
 フレーム ウィンドウのコントロール バーの状態情報を格納するには、このメンバー関数を呼び出す、`CDockState`オブジェクトです。  
  
```  
void GetDockState(CDockState& state) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `state`  
 フレーム ウィンドウのコントロール バーの現在の状態が含まれています。  
  
### <a name="remarks"></a>コメント  
 内容を記述することができますし、`CDockState`を使用してストレージに`CDockState::SaveState`または`Serialize`です。 後で、コントロール バーを以前の状態に復元する場合での状態を読み込む`CDockState::LoadState`または`Serialize`、まず`SetDockState`フレーム ウィンドウのコントロール バーに以前の状態を適用します。  
  
##  <a name="a-namegetmenubarstatea--cframewndgetmenubarstate"></a><a name="getmenubarstate"></a>CFrameWnd::GetMenuBarState  
 現在の MFC アプリケーションのメニューの表示状態を取得します。  
  
```  
virtual DWORD GetMenuBarState();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値は、次の値をとります。  
  
-   AFX_MBS_VISIBLE (0x01) –、メニューが表示されます。  
  
-   AFX_MBS_HIDDEN (0x02) –、メニューは表示されません。  
  
### <a name="remarks"></a>コメント  
 実行時エラーが発生した場合、このメソッドはデバッグ モードでアサートしから派生する例外を発生させる、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
##  <a name="a-namegetmenubarvisibilitya--cframewndgetmenubarvisibility"></a><a name="getmenubarvisibility"></a>CFrameWnd::GetMenuBarVisibility  
 現在の MFC アプリケーションのメニューの既定の状態を表示または非表示にするかどうかを示します。  
  
```  
virtual DWORD CFrameWnd::GetMenuBarVisibility();
```  
  
### <a name="return-value"></a>戻り値  
 このメソッドは、次の値のいずれかを返します。  
  
-   AFX_MBV_KEEPVISIBLE (0x01) で、メニューが表示されるすべてのタイミングと、既定で、フォーカスがないです。  
  
-   AFX_MBV_DISPLAYONFOCUS (0x02) - 既定では、メニューは表示されません。 メニューが表示されていない場合は、メニューを表示し、フォーカスに ALT キーを押します。 メニューが表示される場合は、非表示にする alt キーまたは ESC キーを押します。  
  
-   AFX_MBV_ DISPLAYONFOCUS (0X02) |AFX_MBV_DISPLAYONF10 (0x04) (ビットごとの組み合わせ (OR)) - 既定では、メニューは表示されません。 メニューが表示されていない場合は、メニューを表示し、フォーカスを設定する F10 キーを押します。 メニューが表示される場合は、オンまたはオフ、メニューのフォーカスを切り替える F10 キーを押します。 非表示にする、alt キーまたは ESC キーを押すまで、メニューが表示されます。  
  
### <a name="remarks"></a>コメント  
 実行時エラーが発生した場合、このメソッドはデバッグ モードでアサートしから派生する例外を発生させる、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
##  <a name="a-namegetmessagebara--cframewndgetmessagebar"></a><a name="getmessagebar"></a>CFrameWnd::GetMessageBar  
 ステータス バーにポインターを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CWnd* GetMessageBar();
```  
  
### <a name="return-value"></a>戻り値  
 ステータス バー ウィンドウへのポインター。  
  
##  <a name="a-namegetmessagestringa--cframewndgetmessagestring"></a><a name="getmessagestring"></a>CFrameWnd::GetMessageString  
 コマンド Id のカスタム文字列を提供するには、この関数をオーバーライドします。  
  
```  
virtual void GetMessageString(
    UINT nID,  
    CString& rMessage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 目的のメッセージのリソース ID です。  
  
 `rMessage`  
 `CString`メッセージを格納するオブジェクトです。  
  
### <a name="remarks"></a>コメント  
 既定の実装で指定された文字列を読み込みのみ`nID`リソース ファイルからです。 ステータス バーにメッセージ文字列の更新が必要なときに、この関数がフレームワークによって呼び出されます。  
  
##  <a name="a-namegettitlea--cframewndgettitle"></a><a name="gettitle"></a>CFrameWnd::GetTitle  
 ウィンドウ オブジェクトのタイトルを取得します。  
  
```  
CString GetTitle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)ウィンドウ オブジェクトの現在のタイトルを格納するオブジェクト。  
  
##  <a name="a-nameinitialupdateframea--cframewndinitialupdateframe"></a><a name="initialupdateframe"></a>CFrameWnd::InitialUpdateFrame  
 呼び出す**IntitialUpdateFrame**と新しいフレームを作成した後**作成**します。  
  
```  
void InitialUpdateFrame(
    CDocument* pDoc,  
    BOOL bMakeVisible);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDoc`  
 フレーム ウィンドウが関連付けられているドキュメントへのポインター。 できる**NULL**します。  
  
 `bMakeVisible`  
 場合**TRUE**を示すフレームは表示され、アクティブになる必要があります。 場合**FALSE**子孫は一切表示します。  
  
### <a name="remarks"></a>コメント  
 これにより、受信するには、そのフレーム ウィンドウ内のすべてのビュー、`OnInitialUpdate`呼び出しです。  
  
 また、存在していなかった以前アクティブなビュー、フレーム ウィンドウの主要なビューがアクティブなが作成されます。 プライマリ ビューの子の ID では、ビューは、 **AFX_IDW_PANE_FIRST**します。 最後に、フレーム ウィンドウが表示される場合は`bMakeVisible`は&0; 以外。 場合`bMakeVisible`が 0 の場合、現在フォーカスをフレーム ウィンドウの表示状態は変更されません。 新しいファイルとファイルを開くのフレームワークの実装を使用する場合は、この関数を呼び出す必要はありません。  
  
##  <a name="a-nameinmodalstatea--cframewndinmodalstate"></a><a name="inmodalstate"></a>CFrameWnd::InModalState  
 フレーム ウィンドウをモーダルまたはモードレス チェックするには、このメンバー関数を呼び出します。  
  
```  
BOOL InModalState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は yes です。それ以外の場合 0 を返します。  
  
##  <a name="a-nameistrackinga--cframewndistracking"></a><a name="istracking"></a>CFrameWnd::IsTracking  
 ウィンドウでスプリッター バーが動いている現在かどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsTracking() const;  
```  
  
### <a name="return-value"></a>戻り値  
 分割操作の実行中の場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="a-nameloadacceltablea--cframewndloadacceltable"></a><a name="loadacceltable"></a>CFrameWnd::LoadAccelTable  
 指定されたアクセラレータ テーブルの読み込みの呼び出しです。  
  
```  
BOOL LoadAccelTable(LPCTSTR lpszResourceName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszResourceName`  
 アクセラレータ リソースの名前を識別します。 使用**されるときは**リソースが整数の ID で識別された場合  
  
### <a name="return-value"></a>戻り値  
 アクセラレータ テーブル読み込みが成功した場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 1 つのテーブルは、同時に読み込むことができます。  
  
 リソースから読み込まれたアクセラレータ テーブルは、アプリケーションの終了時に自動的に解放されます。  
  
 呼び出した場合`LoadFrame`フレーム ウィンドウを作成するには、フレームワークはメニューやアイコンのリソースと一緒にアクセラレータ テーブルを読み込みます。 および後続の呼び出し、このメンバー関数に必要はありません。  
  
##  <a name="a-nameloadbarstatea--cframewndloadbarstate"></a><a name="loadbarstate"></a>CFrameWnd::LoadBarState  
 フレーム ウィンドウによって所有されている各コントロール バーの設定を復元するには、この関数を呼び出します。  
  
```  
void LoadBarState(LPCTSTR lpszProfileName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProfileName`  
 初期化 (INI) ファイルのセクションまたは状態情報が格納されている Windows レジストリ内のキーの名前。  
  
### <a name="remarks"></a>コメント  
 復元情報には、可視性には、水平、垂直方向には、ドッキング状態には、コントロール バーの位置が含まれます。  
  
 呼び出す前に、レジストリに書き込まれる、設定を復元する`LoadBarState`です。 呼び出して情報をレジストリに書き込む[書き込むに](../../mfc/reference/cwinapp-class.md#setregistrykey)します。 INI ファイルを呼び出すことにより、情報を書き込む[に](#savebarstate)します。  
  
##  <a name="a-nameloadframea--cframewndloadframe"></a><a name="loadframe"></a>CFrameWnd::LoadFrame  
 リソースの情報からフレーム ウィンドウを動的に作成する呼び出しです。  
  
```  
virtual BOOL LoadFrame(
    UINT nIDResource,  
    DWORD dwDefaultStyle = WS_OVERLAPPEDWINDOW | FWS_ADDTOTITLE,  
    CWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 フレーム ウィンドウに関連付けられている共有リソースの ID です。  
  
 *dwDefaultStyle*  
 フレームの[スタイル](../../mfc/reference/window-styles.md)します。 含める、 **FWS_ADDTOTITLE**する場合は、ウィンドウで表されるドキュメントの名前を自動的に表示するタイトル バーのスタイルを設定します。  
  
 `pParentWnd`  
 フレームの親ウィンドウへのポインター。  
  
 `pContext`  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターを指定できます**NULL**します。  
  
### <a name="remarks"></a>コメント  
 構築、 `CFrameWnd`&2; つのステップ内のオブジェクト。 最初に、構築コンス トラクターを呼び出す、 `CFrameWnd` 、object し、呼び出す`LoadFrame`、Windows フレーム ウィンドウおよび関連付けられているリソースを読み込むし、フレーム ウィンドウの接続、`CFrameWnd`オブジェクトです。 `nIDResource`パラメーターは、メニューのアクセラレータ テーブル、アイコン、およびフレーム ウィンドウのタイトルの文字列リソースを指定します。  
  
 使用して、**作成**メンバー関数ではなく`LoadFrame`すべてのフレーム ウィンドウの作成パラメーターを指定する場合。  
  
 Framework 呼び出し`LoadFrame`ドキュメント テンプレート オブジェクトを使用して、フレーム ウィンドウを作成するとします。  
  
 フレームワークを使用して、`pContext`をいずれかを含む、フレーム ウィンドウに接続されているオブジェクトを指定する引数には、オブジェクト表示にはが含まれています。 設定することができます、`pContext`引数**NULL**を呼び出すと`LoadFrame`です。  
  
##  <a name="a-namembautomenuenablea--cframewndmbautomenuenable"></a><a name="m_bautomenuenable"></a>CFrameWnd::m_bAutoMenuEnable  
 このデータ メンバーには、(既定である) が有効な場合は、メニュー項目がない`ON_UPDATE_COMMAND_UI`または`ON_COMMAND`ハンドラーは、ユーザーがメニューをプルダウンときに自動的に無効です。  
  
```  
BOOL m_bAutoMenuEnable;  
```  
  
### <a name="remarks"></a>コメント  
 持つメニュー項目、`ON_COMMAND`ハンドラーがない`ON_UPDATE_COMMAND_UI`ハンドラーが自動的に有効にします。  
  
 このデータ メンバーを設定すると、メニュー項目がツール バー ボタンが有効になっているのと同じ方法で自動的に有効にします。  
  
> [!NOTE]
> `m_bAutoMenuEnable`トップレベルのメニュー項目に対する影響がありません。  
  
 このデータ メンバーが、現在の選択に基づいた省略可能なコマンドの実装を簡略化し、記述する必要性を軽減`ON_UPDATE_COMMAND_UI`のハンドラーを有効にして、メニュー項目を無効にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#3;](../../mfc/reference/codesnippet/cpp/cframewnd-class_3.cpp)]  
  
##  <a name="a-namenegotiateborderspacea--cframewndnegotiateborderspace"></a><a name="negotiateborderspace"></a>CFrameWnd::NegotiateBorderSpace  
 OLE インプレース アクティブ化時にフレーム ウィンドウの境界領域をネゴシエートする場合は、このメンバー関数を呼び出します。  
  
```  
virtual BOOL NegotiateBorderSpace(
    UINT nBorderCmd,  
    LPRECT lpRectBorder);
```  
  
### <a name="parameters"></a>パラメーター  
 *nBorderCmd*  
 次の値の&1; つ含まれる、 **enum BorderCmd**:  
  
- **borderGet** = 1  
  
- **borderRequest** = 2  
  
- **borderSet** = 3  
  
 `lpRectBorder`  
 ポインター、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または[CRect](../../atl-mfc-shared/reference/crect-class.md)罫線の座標を指定するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、 **CFrameWnd** OLE 境界領域の調整を実装します。  
  
##  <a name="a-nameonbarchecka--cframewndonbarcheck"></a><a name="onbarcheck"></a>CFrameWnd::OnBarCheck  
 指定したコントロール バーで、アクションが実行されるたびに呼び出されます。  
  
```  
afx_msg BOOL OnBarCheck(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 表示されているバー コントロールの ID。  
  
### <a name="return-value"></a>戻り値  
 コントロール バーが存在する場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="a-nameoncontexthelpa--cframewndoncontexthelp"></a><a name="oncontexthelp"></a>受信  
 埋め込み先アイテムについては、shift キーを押しながら f1 キーを処理します。  
  
```  
afx_msg void OnContextHelp();
```  
  
### <a name="remarks"></a>コメント  
 状況依存のヘルプを有効にするに追加する必要があります、  
  
 [!code-cpp[NVC_MFCDocViewSDI&#16;](../../mfc/codesnippet/cpp/cframewnd-class_4.cpp)]  
  
 ステートメントを`CFrameWnd`メッセージ マップのクラスし、も通常 shift キーを押しながら F1 このメンバー関数を有効にする、アクセラレータ テーブル エントリを追加します。  
  
 アプリケーションが OLE コンテナー、`OnContextHelp`ヘルプ モードには、フレーム ウィンドウ オブジェクト内に含まれるすべての埋め込み先アイテムを配置します。 矢印と疑問符 () と、ユーザーがカーソルの変更はマウス ポインターを移動し、 ダイアログ ボックス、ウィンドウ、メニューのまたはコマンド ボタンを選択するマウスの左ボタンを押します。 このメンバー関数は、Windows の関数を呼び出す`WinHelp`カーソルでは、オブジェクトのヘルプ コンテキストを使用します。  
  
##  <a name="a-nameoncreateclienta--cframewndoncreateclient"></a><a name="oncreateclient"></a>CFrameWnd::OnCreateClient  
 実行中に、フレームワークによって呼び出されます`OnCreate`します。  
  
```  
virtual BOOL OnCreateClient(
    LPCREATESTRUCT lpcs,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcs`  
 Windows へのポインター [CREATESTRUCT](../../mfc/reference/createstruct-structure.md)構造*します。*  
  
 `pContext`  
 ポインター、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造*します。*  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数を呼び出すことはありません。  
  
 この関数の既定の実装を作成、`CView`で提供された情報からオブジェクト`pContext`可能であれば、します。  
  
 渡される値を上書きするには、この関数をオーバーライドして、`CCreateContext`オブジェクトまたは変更するフレーム ウィンドウのメインのクライアント領域内を制御する方法を作成します。 `CCreateContext`オーバーライドできるメンバーのとおり、 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)クラスです。  
  
> [!NOTE]
>  渡される値を置き換えないで、`CREATESTRUCT`構造体。 これらは情報目的のみです。 最初のウィンドウの四角形をオーバーライドする場合は、たとえば、オーバーライド、`CWnd`メンバー関数[PreCreateWindow](../../mfc/reference/cwnd-class.md#precreatewindow)します。  
  
##  <a name="a-nameonhidemenubara--cframewndonhidemenubar"></a><a name="onhidemenubar"></a>CFrameWnd::OnHideMenuBar  
 システムが現在の MFC アプリケーションでメニュー バーを非表示にすると、この関数が呼び出されます。  
  
```  
virtual void OnHideMenuBar();
```  
  
### <a name="remarks"></a>コメント  
 このイベント ハンドラーでは、アプリケーションで、システムが、メニューを非表示にすると、カスタム アクションを実行できます。 非表示、メニューを防ぐことはできませんが、たとえば、メニューのスタイルまたは状態を取得するには、その他のメソッドを呼び出すことはできます。  
  
##  <a name="a-nameonsetpreviewmodea--cframewndonsetpreviewmode"></a><a name="onsetpreviewmode"></a>CFrameWnd::OnSetPreviewMode  
 印刷プレビュー モードの内外にアプリケーションのメイン フレーム ウィンドウを設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void OnSetPreviewMode(
    BOOL bPreview,  
    CPrintPreviewState* pState);
```  
  
### <a name="parameters"></a>パラメーター  
 *bPreview*  
 印刷プレビュー モードでアプリケーションを配置するかどうかを指定します。 設定**TRUE**印刷プレビューで配置する**FALSE**プレビュー モードをキャンセルします。  
  
 `pState`  
 ポインター、 **CPrintPreviewState**構造体。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、すべての標準ツールバーを無効にして、メイン メニューと、クライアントのメイン ウィンドウを非表示になります。 これには、一時的なを囲む SDI フレーム ウィンドウに MDI フレーム ウィンドウが有効にします。  
  
 コントロール バーやその他のフレーム ウィンドウの一部の印刷プレビュー期間中の表示や非表示をカスタマイズするには、このメンバー関数をオーバーライドします。 オーバーライドした関数内から基本クラス実装を呼び出します。  
  
##  <a name="a-nameonshowmenubara--cframewndonshowmenubar"></a><a name="onshowmenubar"></a>CFrameWnd::OnShowMenuBar  
 現在の MFC アプリケーションでメニュー バーを表示しようとして、システムは、この関数が呼び出されます。  
  
```  
virtual void OnShowMenuBar();
```  
  
### <a name="remarks"></a>コメント  
 このイベント ハンドラーでは、アプリケーションでメニューが表示される直前にある場合は、カスタム アクションを実行できます。 表示されてから、メニューを防ぐことはできませんが、たとえば、メニューのスタイルまたは状態を取得するには、その他のメソッドを呼び出すことはできます。  
  
##  <a name="a-nameonupdatecontrolbarmenua--cframewndonupdatecontrolbarmenu"></a><a name="onupdatecontrolbarmenu"></a>CFrameWnd::OnUpdateControlBarMenu  
 関連するメニューが更新されたときに、フレームワークによって呼び出されます。  
  
```  
afx_msg void OnUpdateControlBarMenu(CCmdUI* pCmdUI);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCmdUI`  
 ポインター、 [CCmdUI](../../mfc/reference/ccmdui-class.md)更新コマンドを作成するメニューを表すオブジェクト。 更新ハンドラーは、[を有効にする](../../mfc/reference/ccmdui-class.md#enable)のメンバー関数、`CCmdUI`オブジェクト`pCmdUI`ユーザー インターフェイスを更新します。  
  
##  <a name="a-namerecalclayouta--cframewndrecalclayout"></a><a name="recalclayout"></a>表示  
 オンまたはオフに標準のコントロール バーが切り替えられたときに、またはフレーム ウィンドウのサイズが変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bNotify`  
 フレーム ウィンドウのアクティブなインプレース アイテムがレイアウトの変更の通知を受け取るかどうかを決定します。 場合**TRUE**、したアイテムが通知された**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数の既定の実装、`CWnd`メンバー関数`RepositionBars`フレームも、クライアントのメイン ウィンドウと同様に、すべてのコントロール バーの位置を変更する (通常、`CView`または**MDICLIENT**)。  
  
 フレーム ウィンドウのレイアウトが変更された後に、コントロール バーの動作と外観を制御するには、この関数をオーバーライドします。 たとえば、コントロール バーを有効または無効にするか、別のコントロール バーを追加するときに、それを呼び出します。  
  
##  <a name="a-namerectdefaulta--cframewndrectdefault"></a><a name="rectdefault"></a>CFrameWnd::rectDefault  
 静的に渡す`CRect`ウィンドウの初期サイズと位置を選択するウィンドウを許可するようにウィンドウを作成する際に、パラメーターとして。  
  
```  
static AFX_DATA const CRect rectDefault;  
```  
  
##  <a name="a-namesavebarstatea--cframewndsavebarstate"></a><a name="savebarstate"></a>CFrameWnd::SaveBarState  
 フレーム ウィンドウによって所有されている各コントロール バーの情報を格納するには、この関数を呼び出します。  
  
```  
void SaveBarState(LPCTSTR lpszProfileName) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszProfileName`  
 初期化ファイルのセクションまたは状態情報が格納されている Windows レジストリ内のキーの名前。  
  
### <a name="remarks"></a>コメント  
 この情報を使用して、初期化ファイルから読み取ることができます[戻す](#loadbarstate)します。 格納されている情報には、可視性、水平、垂直方向、ドッキング状態、およびコントロール バーの位置が含まれています。  
  
##  <a name="a-namesetactivepreviewviewa--cframewndsetactivepreviewview"></a><a name="setactivepreviewview"></a>CFrameWnd::SetActivePreviewView  
 リッチ プレビュー用のアクティブなビューに指定されたビューを指定します。  
  
```  
void SetActivePreviewView(CView* pViewNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `pViewNew`  
 アクティブ化するためのビューへのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetactiveviewa--cframewndsetactiveview"></a><a name="setactiveview"></a>CFrameWnd::SetActiveView  
 アクティブなビューを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetActiveView(
    CView* pViewNew,  
    BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *pViewNew*  
 指すポインター、 [CView](../../mfc/reference/cview-class.md)オブジェクト、または**NULL**のアクティブなビューがありません。  
  
 `bNotify`  
 ビューがアクティブ化の通知を受け取るかどうかを指定します。 場合**TRUE**、`OnActivateView`ときに呼び出される新しいビューの**FALSE**はありません。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、この関数のフレーム ウィンドウ内のビューにフォーカスを変更すると自動的に呼び出します。 明示的に呼び出すことができます`SetActiveView`に指定されたビューにフォーカスを変更します。  
  
##  <a name="a-namesetdockstatea--cframewndsetdockstate"></a><a name="setdockstate"></a>CFrameWnd::SetDockState  
 格納されている状態情報を適用するには、このメンバー関数を呼び出して、`CDockState`フレーム ウィンドウのコントロール バーへのオブジェクト。  
  
```  
void SetDockState(const CDockState& state);
```  
  
### <a name="parameters"></a>パラメーター  
 `state`  
 フレーム ウィンドウのコントロール バーに格納されている状態を適用します。  
  
### <a name="remarks"></a>コメント  
 コントロール バーの以前の状態を復元するに格納されている状態を読み込むことができます`CDockState::LoadState`または`Serialize`を使用して`SetDockState`フレーム ウィンドウのコントロール バーに適用します。 以前の状態が格納されている、`CDockState`でオブジェクトです。`GetDockState`  
  
##  <a name="a-namesetmenubarstatea--cframewndsetmenubarstate"></a><a name="setmenubarstate"></a>CFrameWnd::SetMenuBarState  
 非表示または表示は、現在の MFC アプリケーションのメニューの表示状態を設定します。  
  
```  
virtual BOOL SetMenuBarState(DWORD nState);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nState`|メニューを表示または非表示にするかどうかを指定します。 `nState`パラメーターは、次の値を持つことができます。<br /><br /> AFX_MBS_VISIBLE (0x01) – では、それが非表示が表示されている場合は、効果はない場合に、メニューが表示されます。<br />AFX_MBS_HIDDEN (0x02) – には、メニューが非表示に、表示されても、非表示にされている場合は無効です。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドは、メニューの状態を正常に変更された場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 実行時エラーが発生した場合、このメソッドはデバッグ モードでアサートしから派生する例外を発生させる、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
##  <a name="a-namesetmenubarvisibilitya--cframewndsetmenubarvisibility"></a><a name="setmenubarvisibility"></a>CFrameWnd::SetMenuBarVisibility  
 非表示または非表示には、現在の MFC アプリケーションで、メニューの既定の動作を設定します。  
  
```  
virtual void SetMenuBarVisibility(DWORD nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `nStyle`|かどうか、メニューは表示されず、既定では表示やフォーカスがあるを指定します。 `nStyle`パラメーターは、次の値を持つことができます。<br /><br /> AFX_MBV_KEEPVISIBLE (0X01)-<br />     メニューは、常に表示され、既定にフォーカスがないです。<br />AFX_MBV_DISPLAYONFOCUS (0X02)-<br />     既定では、メニューが表示されません。 メニューが表示されていない場合は、メニューを表示し、フォーカスに ALT キーを押します。 メニューが表示される場合は、メニューを非表示に alt キーまたは ESC キーを押します。<br />-AFX_MBV_ DISPLAYONFOCUS (0X02) |AFX_MBV_DISPLAYONF10 (0X04)<br />     (ビットごとの組み合わせ (OR)) - 既定では、メニューは表示されません。 メニューが表示されていない場合は、メニューを表示し、フォーカスを設定する F10 キーを押します。 メニューが表示される場合は、オンまたはオフ、メニューのフォーカスを切り替える F10 キーを押します。 非表示にする、alt キーまたは ESC キーを押すまで、メニューが表示されます。|  
  
### <a name="remarks"></a>コメント  
 場合の値、`nStyle`パラメーターが有効でないこのメソッドをデバッグ モードとでアサート[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)リリース モードでします。 その他のランタイム エラーが発生した場合、このメソッドはデバッグ モードでアサートから派生する例外を発生させる、 [CException](../../mfc/reference/cexception-class.md)クラスです。  
  
 このメソッドに記述されたアプリケーションでメニューの状態に影響[!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)]以降。  
  
##  <a name="a-namesetmessagetexta--cframewndsetmessagetext"></a><a name="setmessagetext"></a>CFrameWnd::SetMessageText  
 ステータス バー ペインを持つ ID は 0 で文字列を配置するには、この関数を呼び出します。  
  
```  
void SetMessageText(LPCTSTR lpszText);  
void SetMessageText(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 ステータス バーに配置される文字列へのポインター。  
  
 `nID`  
 ステータス バーに配置される文字列のリソース ID の文字列を指定します。  
  
### <a name="remarks"></a>コメント  
 これは、通常、ステータス バーの最も長い、左端、ウィンドウです。  
  
##  <a name="a-namesetprogressbarpositiona--cframewndsetprogressbarposition"></a><a name="setprogressbarposition"></a>CFrameWnd::SetProgressBarPosition  
 タスク バーに表示される Windows 7 の進行状況バーの現在の位置を設定します。  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `nProgressPos`  
 設定する位置を指定します。 設定されている範囲内になければなりません`SetProgressBarRange`します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetprogressbarrangea--cframewndsetprogressbarrange"></a><a name="setprogressbarrange"></a>CFrameWnd::SetProgressBarRange  
 タスク バーに表示される Windows 7 の進行状況バーの範囲を設定します。  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRangeMin`  
 最小値。  
  
 `nRangeMax`  
 最大値。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesetprogressbarstatea--cframewndsetprogressbarstate"></a><a name="setprogressbarstate"></a>CFrameWnd::SetProgressBarState  
 タスク バー ボタンに表示される進行状況インジケーターの状態の種類を設定します。  
  
```  
void SetProgressBarState(TBPFLAG tbpFlags);
```  
  
### <a name="parameters"></a>パラメーター  
 `tbpFlags`  
 進捗状況ボタンの現在の状態を制御するフラグ。 すべての状態が相互に排他的であるため、次のいずれかにのみフラグを指定します。 TBPF_NOPROGRESS、TBPF_INDETERMINATE、TBPF_NORMAL、TBPF_ERROR、TBPF_PAUSED です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesettaskbaroverlayicona--cframewndsettaskbaroverlayicon"></a><a name="settaskbaroverlayicon"></a>CFrameWnd::SetTaskbarOverlayIcon  
 オーバーロードされます。 アプリケーションの状態を示すために、またはユーザーに通知するのには、タスク バー ボタンにオーバーレイを適用します。  
  
```  
BOOL SetTaskbarOverlayIcon(
    UINT nIDResource,  
    LPCTSTR lpcszDescr);

 
BOOL SetTaskbarOverlayIcon(
    HICON hIcon,  
    LPCTSTR lpcszDescr);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDResource`  
 オーバーレイを使用するアイコンのリソース ID を指定します。 説明を参照してください`hIcon`詳細です。  
  
 `lpcszDescr`  
 ユーザー補助用のオーバーレイで表現される情報の代替テキスト バージョンを提供する文字列へのポインター。  
  
 `hIcon`  
 オーバーレイとして使用するアイコンのハンドル。 これは、96 ドット/インチ (dpi) にある 16 x 16 ピクセルの測定、小さいアイコンでなければなりません。 オーバーレイ アイコンは、タスク バー ボタンに既に適用されて、既存のオーバーレイが置き換えられます。 この値は、`NULL` の場合もあります。 どのように、`NULL`値はタスク バー ボタンが&1; つのウィンドウまたは windows のグループを表しているかどうかによって異なります。 解放する呼び出し元のアプリケーションの機能により`hIcon`不要になったとき。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`成功した場合`FALSE`オペレーティング システムのバージョンが Windows 7 より小さい場合、またはアイコンを設定、エラーが発生します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namesettitlea--cframewndsettitle"></a><a name="settitle"></a>CFrameWnd::SetTitle  
 ウィンドウ オブジェクトのタイトルを設定します。  
  
```  
void SetTitle(LPCTSTR lpszTitle);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTitle`  
 ウィンドウ オブジェクトのタイトルを含む文字列へのポインター。  
  
##  <a name="a-nameshowcontrolbara--cframewndshowcontrolbar"></a><a name="showcontrolbar"></a>CFrameWnd::ShowControlBar  
 コントロール バーを非表示には、このメンバー関数を呼び出します。  
  
```  
void ShowControlBar(
    CControlBar* pBar,  
    BOOL bShow,  
    BOOL bDelay);
```  
  
### <a name="parameters"></a>パラメーター  
 `pBar`  
 コントロール バーを表示するか非表示へのポインター。  
  
 `bShow`  
 場合**TRUE**、コントロール バーが表示されることを指定します。 場合**FALSE**、コントロール バーを非表示にすることを指定します。  
  
 *bDelay*  
 場合**TRUE**、遅延、コントロール バーを表示します。 場合**FALSE**、バーのすぐにコントロールを表示します。  
  
##  <a name="a-nameshowownedwindowsa--cframewndshowownedwindows"></a><a name="showownedwindows"></a>CFrameWnd::ShowOwnedWindows  
 子孫であるすべてのウィンドウを表示するには、このメンバー関数を呼び出す、`CFrameWnd`オブジェクトです。  
  
```  
void ShowOwnedWindows(BOOL bShow);
```  
  
### <a name="parameters"></a>パラメーター  
 `bShow`  
 所有しているウィンドウを表示するか非表示になっているかどうかを指定します。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)   
 [CDocTemplate クラス](../../mfc/reference/cdoctemplate-class.md)   
 [編集](../../mfc/reference/cruntimeclass-structure.md)

