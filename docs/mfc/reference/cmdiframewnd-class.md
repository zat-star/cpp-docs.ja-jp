---
title: "CMDIFrameWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
dev_langs:
- C++
helpviewer_keywords:
- MDI frame windows
- CMDIFrameWnd class
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
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
ms.openlocfilehash: 0eae6c14038dd27a5779757d1807068fbe865b81
ms.lasthandoff: 02/24/2017

---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd クラス
Windows のマルチ ドキュメント インターフェイス (MDI: Multiple Document Interface) のフレーム ウィンドウの機能が用意されています。さらに、ウィンドウを管理するメンバーも用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|`CMDIFrameWnd` を構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIFrameWnd::CreateClient](#createclient)|Windows の作成**MDICLIENT**このウィンドウ`CMDIFrameWnd`です。 によって呼び出される、`OnCreate`のメンバー関数`CWnd`します。|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|新しい子ウィンドウを作成します。|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|ウィンドウのポップアップ メニューを返します。|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|別の MDI 子ウィンドウをアクティブにします。|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|すべての子ウィンドウを重ねて表示を配置します。|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|子プロセスが最大化されているかどうかを示すフラグと共に、現在アクティブな MDI 子ウィンドウを取得します。|  
|[ある最小化されました。](#mdiiconarrange)|最小化されたドキュメントのすべての子ウィンドウを整列します。|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|MDI 子ウィンドウを最大化します。|  
|[CMDIFrameWnd::MDINext](#mdinext)|現在アクティブな子ウィンドウの背後にすぐに子ウィンドウをアクティブにし、その他のすべての子ウィンドウの後ろに、現在アクティブな子ウィンドウを配置します。|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|前の子ウィンドウをアクティブにし、すぐ後ろに、現在アクティブな子ウィンドウを置きます。|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|MDI 子ウィンドウを最大化または最小化されているサイズから復元します。|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|MDI フレーム ウィンドウのメニューのウィンドウのポップアップ メニューで、またはその両方を置き換えます。|  
|[CMDIFrameWnd::MDITile](#mditile)|タイル化された形式でのすべての子ウィンドウを整列します。|  
  
## <a name="remarks"></a>コメント  
 アプリケーションの便利な MDI フレーム ウィンドウを作成するには、派生クラスを`CMDIFrameWnd`します。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 MDI フレーム ウィンドウを構築するには呼び出すことによって、[作成](../../mfc/reference/cframewnd-class.md#create)または[LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe)のメンバー関数`CFrameWnd`します。  
  
 呼び出す前に**作成**または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に**作成**でウィンドウ クラスを登録することも、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。  
  
 使用して、**作成**引数を渡すフレームの作成パラメーターに直接のメンバー関数。  
  
 `LoadFrame`も少ない数の引数を必要と**作成**、し、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースから、既定の値のほとんどを取得します。 アクセスする`LoadFrame`、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、 **IDR_MAINFRAME**)。  
  
 **MDIFrameWnd**から派生した`CFrameWnd`、フレーム ウィンドウ クラスから派生した`CMDIFrameWnd`と共に宣言する必要がない`DECLARE_DYNCREATE`します。  
  
 `CMDIFrameWnd`クラスは継承から既定の実装の大部分`CFrameWnd`します。 これらの機能の詳細な一覧を参照してください、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの記述。 `CMDIFrameWnd`クラスには次の追加機能。  
  
-   MDI フレーム ウィンドウの管理、 **MDICLIENT**ウィンドウで、コントロール バーと共に位置を変更します。 MDI クライアント ウィンドウは、MDI 子フレーム ウィンドウの直接の親です。 **WS_HSCROLL**と**WS_VSCROLL**で指定されたウィンドウのスタイル、 `CMDIFrameWnd` MDI クライアントのウィンドウに適用、ユーザーは MDI クライアントの領域 (と同様に、Windows プログラム マネージャーなど) をスクロールできるように、メイン フレーム ウィンドウではなく。  
  
-   MDI フレーム ウィンドウには、アクティブな MDI 子ウィンドウがない場合は、メニュー バーとして使用される既定のメニューが所有しています。 アクティブな MDI 子がある場合は、MDI 子ウィンドウのメニューで、MDI フレーム ウィンドウのメニュー バーは自動的に置換します。  
  
-   MDI フレーム ウィンドウは、1 つを使用する必要がある場合、現在の MDI 子ウィンドウと組み合わせて動作します。 たとえば、コマンド メッセージは、MDI フレーム ウィンドウの前に、現在アクティブな MDI 子に委任されます。  
  
-   MDI フレーム ウィンドウには、以下の標準のウィンドウのメニュー コマンドの既定のハンドラーがあります。  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   MDI フレーム ウィンドウにも、実装の**ID_WINDOW_NEW**、新しいフレームと現在のドキュメントのビューを作成します。 アプリケーションでは、これら既定のコマンドを MDI ウィンドウの処理をカスタマイズする実装をオーバーライドできます。  
  
 C++ を使用しないで**削除**フレーム ウィンドウを破棄する演算子です。 代わりに、 `CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ オブジェクトを削除します。 ユーザーが、既定のフレーム ウィンドウを閉じたときに`OnClose`ハンドラーが呼び出す`DestroyWindow`します。  
  
 詳細については`CMDIFrameWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cmdiframewnd"></a>CMDIFrameWnd::CMDIFrameWnd  
 `CMDIFrameWnd` オブジェクトを構築します。  
  
```  
CMDIFrameWnd();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す、**作成**または`LoadFrame`表示 MDI フレーム ウィンドウを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#13;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]  
  
##  <a name="createclient"></a>CMDIFrameWnd::CreateClient  
 管理する MDI クライアント ウィンドウを作成、`CMDIChildWnd`オブジェクトです。  
  
```  
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpCreateStruct`  
 Long ポインター、 [CREATESTRUCT](../../mfc/reference/createstruct-structure.md)構造体。  
  
 `pWindowMenu`  
 ウィンドウのポップアップ メニューへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 オーバーライドする場合、このメンバー関数を呼び出す必要があります、`OnCreate`直接のメンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#14;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]  
  
##  <a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild  
 新しい子ウィンドウを作成します。  
  
```  
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,  
    UINT nResource,  
    HMENU hMenu = NULL,  
    HACCEL hAccel = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pClass`  
 子ウィンドウを作成できるのランタイム クラスです。  
  
 *nResource*  
 子ウィンドウに関連付けられている共有リソースの ID です。  
  
 `hMenu`  
 子ウィンドウのメニュー。  
  
 `hAccel`  
 子ウィンドウのアクセラレータです。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、子 MDI フレーム ウィンドウのウィンドウを作成できます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#15;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 この例は、サポート技術情報記事 Q201045 からの抜粋"HOWTO: 非ドキュメント/ビュー MDI アプリケーションに複数のウィンドウの種類を追加します"。 サポート技術情報の記事は、MSDN ライブラリの Visual Studio のドキュメントで使用可能な[http://support.microsoft.com](http://support.microsoft.com/)します。  
  
##  <a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup  
 「ウィンドウ」(MDI ウィンドウの管理のためのメニュー項目を含むポップアップ メニュー) という名前の現在のポップアップ メニューへのハンドルを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>パラメーター  
 *hMenuBar*  
 現在のメニュー バー。  
  
### <a name="return-value"></a>戻り値  
 1 つのウィンドウのポップアップ メニューが存在します。それ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 既定の実装はなどの標準のウィンドウ メニューのコマンドを含むポップアップ メニューの検索**ID_WINDOW_NEW**と**ID_WINDOW_TILE_HORZ**します。  
  
 標準のメニュー コマンド Id を使用しないウィンドウ メニューがある場合は、このメンバー関数をオーバーライドします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#16;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate  
 別の MDI 子ウィンドウをアクティブにします。  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndActivate*  
 アクティブ化する MDI 子ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、 [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate)子ウィンドウがアクティブ化および非アクティブ化して子ウィンドウにメッセージをします。  
  
 これは、ユーザーは、マウスまたはキーボードを使用して MDI 子ウィンドウにフォーカスを移したときに送られるのと同じメッセージです。  
  
> [!NOTE]
>  MDI フレーム ウィンドウとは無関係に、MDI 子ウィンドウがアクティブ化されます。 最後にアクティブになった子ウィンドウが送信されたフレームがアクティブになったとき、[ため](../../mfc/reference/cwnd-class.md#onncactivate)がアクティブなウィンドウ フレームとタイトル バーを描画するメッセージを受け取りません別`WM_MDIACTIVATE`メッセージです。  
  
### <a name="example"></a>例  
 例を参照してください[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)します。  
  
##  <a name="mdicascade"></a>CMDIFrameWnd::MDICascade  
 Cascade 形式でのすべての MDI 子ウィンドウを整列します。  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nType`  
 Cascade フラグを指定します。 次のフラグのみを指定できます: `MDITILE_SKIPDISABLED`、ため、無効になっている MDI 子ウィンドウを重ねて表示されています。  
  
### <a name="remarks"></a>コメント  
 最初のバージョン`MDICascade`、パラメーターなしで、無効になっているものを含むすべての MDI 子ウィンドウを重ねて表示します。 2 番目のバージョンは cascade が無効になっている MDI 子ウィンドウいないを指定した場合に必要に応じて`MDITILE_SKIPDISABLED`の`nType`パラメーター。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&17;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive  
 現在アクティブな MDI 子ウィンドウ、と共に子ウィンドウを最大化するかどうかを示すフラグを取得します。  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pbMaximized*  
 ポインター、 **BOOL**値を返します。 設定**TRUE**ウィンドウが最大化、それ以外の場合に返された**FALSE**します。  
  
### <a name="return-value"></a>戻り値  
 アクティブな MDI 子ウィンドウへのポインター。  
  
### <a name="example"></a>例  
 例を参照してください[CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)します。  
  
##  <a name="mdiiconarrange"></a>ある最小化されました。  
 最小化されたドキュメントのすべての子ウィンドウを整列します。  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>コメント  
 最小化されていない子ウィンドウには影響しません。  
  
### <a name="example"></a>例  
 例を参照してください[CMDIFrameWnd::MDICascade](#mdicascade)します。  
  
##  <a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize  
 指定の MDI 子ウィンドウを最大化します。  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 最大化するウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 子ウィンドウが最大化されたときに、クライアント領域の [クライアント] ウィンドウを入力するために Windows がサイズ変更します。 Windows は、フレームのメニュー バーで、子ウィンドウのコントロールのメニューを配置するユーザーは、復元したり、子ウィンドウを閉じるようにします。 また、フレーム ウィンドウのタイトルを子ウィンドウのタイトルを追加します。  
  
 現在アクティブな MDI 子ウィンドウが最大化されているときに別の MDI 子ウィンドウがアクティブな場合、Windows は現在アクティブな子を復元し、新しくアクティブになる子ウィンドウを最大化します。  
  
### <a name="example"></a>例  
 例を参照してください[CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)します。  
  
##  <a name="mdinext"></a>CMDIFrameWnd::MDINext  
 現在アクティブな子ウィンドウの背後にすぐに子ウィンドウをアクティブにし、その他のすべての子ウィンドウの後ろに、現在アクティブな子ウィンドウを配置します。  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>コメント  
 現在アクティブな MDI 子ウィンドウが最大化されている場合、メンバー関数は現在アクティブな子を復元し、新しくアクティブ化の子を最大化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#18;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="mdiprev"></a>CMDIFrameWnd::MDIPrev  
 前の子ウィンドウをアクティブにし、すぐ後ろに、現在アクティブな子ウィンドウを置きます。  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>コメント  
 現在アクティブな MDI 子ウィンドウが最大化されている場合、メンバー関数は現在アクティブな子を復元し、新しくアクティブ化の子を最大化します。  
  
##  <a name="mdirestore"></a>CMDIFrameWnd::MDIRestore  
 MDI 子ウィンドウを最大化または最小化されているサイズから復元します。  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 元に戻すウィンドウへのポインター。  
  
### <a name="example"></a>例  
 例を参照してください[CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore)します。  
  
##  <a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu  
 MDI フレーム ウィンドウのメニューのウィンドウのポップアップ メニューで、またはその両方を置き換えます。  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 *pFrameMenu*  
 新しいフレーム ウィンドウ メニューのメニューを指定します。 場合**NULL**メニューは変更されません。  
  
 `pWindowMenu`  
 新しいウィンドウのポップアップ メニューのメニューを指定します。 場合**NULL**メニューは変更されません。  
  
### <a name="return-value"></a>戻り値  
 このメッセージに置き換え、フレーム ウィンドウのメニューへのポインター。 ポインターは一時的である可能性があり、後で使用するために格納しないでください。  
  
### <a name="remarks"></a>コメント  
 呼び出した後`MDISetMenu`、アプリケーションを呼び出す必要があります、 [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar)のメンバー関数`CWnd`メニュー バーを更新します。  
  
 この呼び出しに代わる、ウィンドウのポップアップ メニューで、MDI 子ウィンドウのメニュー項目は前のウィンドウ メニューから削除し、新しいウィンドウのポップアップ メニューに追加します。  
  
 MDI 子ウィンドウが最大化されている、この呼び出しは、MDI フレーム ウィンドウのメニューを置き換える場合は、コントロールのメニューと復元のコントロールが前のフレーム ウィンドウ メニューから削除し、新しいメニューに追加します。  
  
 MDI 子ウィンドウを管理するために、フレームワークを使用する場合は、このメンバー関数を呼び出さないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#19;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#20;](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="mditile"></a>CMDIFrameWnd::MDITile  
 タイル化された形式でのすべての子ウィンドウを整列します。  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>パラメーター  
 `nType`  
 並べて表示フラグを指定します。 このパラメーターは、次のフラグのいずれかを指定できます。  
  
- `MDITILE_HORIZONTAL`MDI 子ウィンドウがタイル上別にその&1; つのウィンドウが表示されます。  
  
- `MDITILE_SKIPDISABLED`無効になっている MDI 子ウィンドウが並べて表示する対象するを防ぎます。  
  
- `MDITILE_VERTICAL`MDI 子ウィンドウが並べてその&1; つのウィンドウが別の横に表示されます。  
  
### <a name="remarks"></a>コメント  
 最初のバージョン`MDITile`パラメーターを指定せずには、Windows 3.1 以降のバージョン 垂直方向にウィンドウを並べて表示します。 第&2; のバージョンでは、ウィンドウを並べて表示垂直または水平の値に応じて、`nType`パラメーター。  
  
### <a name="example"></a>例  
 例を参照してください[CMDIFrameWnd::MDICascade](#mdicascade)します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [MFC のサンプルは](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd クラス](../../mfc/reference/cmdichildwnd-class.md)

