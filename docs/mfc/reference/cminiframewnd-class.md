---
title: "CMiniFrameWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMiniFrameWnd
- AFXWIN/CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::CMiniFrameWnd
- AFXWIN/CMiniFrameWnd::Create
- AFXWIN/CMiniFrameWnd::CreateEx
dev_langs:
- C++
helpviewer_keywords:
- CMiniFrameWnd class
- mini-frame windows
- toolbars [C++]
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1229f5405c9eeb90abcdc54108ed26e28d94f0e0
ms.lasthandoff: 02/24/2017

---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd クラス
フローティング ツール バーの周りなどで使用される、半分の高さのフレーム ウィンドウを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|`CMiniFrameWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[には](#create)|作成、`CMiniFrameWnd`作成した後のオブジェクト。|  
|[CMiniFrameWnd::CreateEx](#createex)|作成、`CMiniFrameWnd`作成した後 (に追加のオプション) オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 これらのミニフレーム ウィンドウの通常のフレーム ウィンドウと同様に動作する点を除いて、最小/最大化ボタンがないか、メニューとするのみを [システム] メニューを閉じるには、1 回のクリックを持つです。  
  
 使用する、`CMiniFrameWnd`オブジェクト、最初に、オブジェクトを定義します。 まず、[作成](#create)ミニフレーム ウィンドウを表示するメンバー関数。  
  
 使用する方法の詳細についての`CMiniFrameWnd`オブジェクト、記事を参照して[ドッキング ツールバーとフローティング ツールバー](../../mfc/docking-and-floating-toolbars.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd  
 構築、`CMiniFrameWnd`オブジェクトは、ウィンドウを作成しません。  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウを作成するには[には](#create)です。  
  
##  <a name="create"></a>には  
 Windows ミニフレーム ウィンドウを作成し、それをアタッチ、`CMiniFrameWnd`オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpClassName`  
 Windows クラスの名前を示す文字の null で終わる文字列へのポインター。 クラス名は、グローバルに登録されている任意の名前を指定できます[AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)関数です。 場合**NULL**、ウィンドウ クラスには、フレームワークによってに登録されます。 MFC では、既定のクラスを次のスタイルと属性。  
  
-   セットのスタイル ビット**CS_DBLCLKS**、送信し、ユーザーがマウスをダブルクリックすると、ウィンドウ プロシージャへのメッセージ をダブルクリックします。  
  
-   セット スタイル ビット**CS_HREDRAW**と**CS_VREDRAW**、ウィンドウ サイズが変更されたときに再描画されるクライアント領域の内容を送信します。  
  
-   クラスのカーソル標準の Windows に設定**IDC_ARROW**します。  
  
-   クラスの背景ブラシが設定**NULL**ので、ウィンドウは、背景を消去できません。  
  
-   [クラス] アイコンを手を振るフラグの標準の Windows ロゴ アイコンに設定します。  
  
-   Windows が示すとおり、既定のサイズと位置をウィンドウを設定します。  
  
 `lpWindowName`  
 ウィンドウの名前を表す null で終わる文字列へのポインター。  
  
 `dwStyle`  
 ウィンドウのスタイル属性を指定します。 これには、標準のウィンドウ スタイルと&1; つ以上の次の特殊なスタイルも含まれます。  
  
- **MFS_MOVEFRAME**ミニフレーム ウィンドウ キャプションだけでなく、ウィンドウのいずれかの端をクリックして移動するようにします。  
  
- **MFS_4THICKFRAME**ミニフレーム ウィンドウのサイズ変更が無効です。  
  
- **返さ**親ウィンドウのアクティブ化するミニフレーム ウィンドウのアクティブ化を同期します。  
  
- **MFS_THICKFRAME**ミニフレーム ウィンドウのクライアント領域の内容を用意する小さなサイズを使用します。  
  
- **MFS_BLOCKSYSMENU**システム メニューのコントロールのメニューへのアクセスを無効にし、キャプション (タイトル バー) の一部に変換します。  
  
 参照してください[cwnd::create](../../mfc/reference/cwnd-class.md#create)利用可能なウィンドウのスタイル値の詳細についてです。 ミニフレーム ウィンドウで使用される一般的な組み合わせは**WS_POPUP |WS_CAPTION |WS_SYSMENU**します。  
  
 `rect`  
 A`RECT`構造体のウィンドウの大きさを指定します。  
  
 `pParentWnd`  
 親ウィンドウへのポインター。 使用**NULL**トップレベル ウィンドウです。  
  
 `nID`  
 子ウィンドウで、ミニフレーム ウィンドウが作成された場合は、これは、子コントロールの識別子それ以外の場合 0 を返します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **作成**ウィンドウのクラス名やウィンドウ名を初期化し、スタイルと親の既定値を登録します。  
  
##  <a name="createex"></a>CMiniFrameWnd::CreateEx  
 
          `CMiniFrameWnd` オブジェクトを作成します。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 拡張スタイルを指定、`CMiniFrameWnd`作成中です。 任意の適用、[拡張ウィンドウ スタイル](../../mfc/reference/extended-window-styles.md)ウィンドウにします。  
  
 `lpClassName`  
 Windows クラスの名前を示す文字の null で終わる文字列へのポインター (、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造) です。 クラス名は、グローバルに登録されている任意の名前を指定できます[AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0)関数または定義済みのコントロール クラス名のいずれかです。 ことはできません**NULL**します。  
  
 `lpWindowName`  
 ウィンドウの名前を表す null で終わる文字列へのポインター。  
  
 `dwStyle`  
 ウィンドウのスタイル属性を指定します。 参照してください[ウィンドウ スタイル](../../mfc/reference/window-styles.md)と[cwnd::create](../../mfc/reference/cwnd-class.md#create)使用可能な値の詳細についてです。  
  
 `rect`  
 サイズと、ウィンドウの位置のクライアント座標で`pParentWnd`します。  
  
 `pParentWnd`  
 親ウィンドウ オブジェクトへのポインター。  
  
 `nID`  
 子ウィンドウの識別子です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますを返します。  
  
### <a name="remarks"></a>コメント  
 `CreateEx`パラメーターの指定、 **WNDCLASS**ウィンドウのスタイルと (必要に応じて) 初期位置、およびウィンドウのサイズ。 `CreateEx`また、ウィンドウの親 (存在する場合) と ID を指定します。  
  
 `CreateEx`実行されると、Windows の送信、 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)、 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate)、 [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize)、および[WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate)メッセージ ウィンドウにします。  
  
 既定のメッセージ処理を拡張するには、派生クラスを`CMiniFrameWnd`メッセージ マップを新しいクラスに追加し、上記のメッセージのメンバー関数を提供します。 オーバーライド`OnCreate`など、新しいクラスに必要な初期化を実行します。  
  
 さらにオーバーライド**に***メッセージ*メッセージ ハンドラーは、派生クラスに機能を追加します。  
  
 場合、 **WS_VISIBLE**スタイルが与えられると、Windows アクティブ化して、ウィンドウを表示するために必要なすべてのメッセージ ウィンドウに送信します。 ウィンドウ スタイルでは、タイトル バーを指定する場合、ウィンドウのタイトルが指す、`lpszWindowName`パラメーターは、タイトル バーに表示されます。  
  
 `dwStyle`パラメーターの任意の組み合わせを指定できます[ウィンドウ スタイル](../../mfc/reference/window-styles.md)します。  
  
 古いスタイルのパレット ツールボックス ウィンドウはサポートされていません。 "X"閉じるボタン設定されていない、旧スタイルは、windows の以前のバージョンの MFC アプリケーションを実行している場合にサポートされていましたが、Visual C .NET でサポートされて不要になった。 のみ新しい`WS_EX_TOOLWINDOW`スタイルのサポートが追加されました。 このスタイルについては、次を参照してください。[拡張ウィンドウ スタイル](../../mfc/reference/extended-window-styles.md)します。  
  
## <a name="see-also"></a>関連項目  
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)

