---
title: "CPaneDialog クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneDialog
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog::OnLButtonDblClk method
- CPaneDialog::OnLButtonDown method
- CPaneDialog::CreateObject method
- CPaneDialog::OnUpdateCmdUI method
- CPaneDialog constructor
- CPaneDialog::OnEraseBkgnd method
- CPaneDialog class
- CPaneDialog::OnWindowPosChanging method
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
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
ms.openlocfilehash: 85c7e338382758dd809fb770c5ab14860e362da8
ms.lasthandoff: 02/24/2017

---
# <a name="cpanedialog-class"></a>CPaneDialog クラス
`CPaneDialog`クラスはモードレスでドッキング可能なダイアログ ボックスをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|既定のコンストラクター|  
|`CPaneDialog::~CPaneDialog`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|ドッキング可能なダイアログ ボックスを作成し、それにアタッチ、`CPaneDialog`オブジェクトです。|  
|`CPaneDialog::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|`CPaneDialog::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|処理、 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428)メッセージです。 (再定義`CBasePane::HandleInitDialog`)。|  
|`CPaneDialog::OnEraseBkgnd`|処理、 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)メッセージです。 (再定義[CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd))。|  
|`CPaneDialog::OnLButtonDblClk`|処理、[や](http://msdn.microsoft.com/library/windows/desktop/ms645606)メッセージです。 (再定義[CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk))。|  
|`CPaneDialog::OnLButtonDown`|処理、 [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607)メッセージです。 (再定義[CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown))。|  
|`CPaneDialog::OnUpdateCmdUI`|ダイアログ ボックスのウィンドウを更新するためにフレームワークによって呼び出されます。 (上書き[CDockablePane::OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0))。|  
|`CPaneDialog::OnWindowPosChanging`|処理、 [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653)メッセージです。 (再定義[CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging))。|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|OLE コントロール コンテナーである ダイアログ ボックスのテンプレートを指定します。|  
  
## <a name="remarks"></a>コメント  
 構築、 `CPaneDialog`&2; つのステップ内のオブジェクト。 最初に、コード内のオブジェクトを構築します。 次に、呼び出す[CPaneDialog::Create](#create)します。 有効なリソースのテンプレートの名前またはテンプレートの ID を指定して、親ウィンドウへのポインターを渡す必要があります。 それ以外の場合、作成プロセスは失敗します。 ダイアログ ボックスでは、WS_CHILD と WS_VISIBLE のスタイルを指定する必要があります。 WS_CLIPCHILDREN と WS_CLIPSIBLINGS のスタイルを指定することをお勧めします。 詳細については、次を参照してください。[ウィンドウ スタイル](window-styles.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxpanedialog.h  
  
##  <a name="a-namecreatea--cpanedialogcreate"></a><a name="create"></a>CPaneDialog::Create  
 ドッキングのダイアログ ボックスを作成し、それにアタッチ、`CPaneDialog`オブジェクトです。  
  
```  
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID,  
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,  
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

 
BOOL Create(
    LPCTSTR lpszWindowName,  
    CWnd* pParentWnd,  
    BOOL bHasGripper,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    LPCTSTR lpszTemplateName,  
    UINT nStyle,  
    UINT nID);

 
BOOL Create(
    CWnd* pParentWnd,  
    UINT nIDTemplate,  
    UINT nStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszWindowName`  
 ドッキングのダイアログ ボックスの名前。  
  
 [入力] `pParentWnd`  
 親ウィンドウへのポインター。  
  
 [入力] `bHasGripper`  
 `TRUE`キャプション (グリップ); とドッキングのダイアログ ボックスを作成するにはそれ以外の場合、`FALSE`です。  
  
 [入力] `lpszTemplateName`  
 リソースのダイアログ テンプレートの名前。  
  
 [入力] `nStyle`  
 ウィンドウ スタイル。  
  
 [入力] `nID`  
 コントロールの id。  
  
 [入力] `nIDTemplate`  
 ダイアログ テンプレートのリソース ID です。  
  
 [入力] `dwTabbedStyle`  
 このコントロール ウィンドウのキャプションにユーザーがコントロールの別のウィンドウをドラッグするときに結果をタブ付きウィンドウのスタイル。 既定値は `AFX_CBRS_REGULAR_TABS` です。 詳細については、の「解説」セクションを参照してください、 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)メソッドです。  
  
 [入力] `dwControlBarStyle`  
 追加のスタイル属性。 既定値は `AFX_DEFAULT_DOCKING_PANE_STYLE` です。 詳細については、の「解説」セクションを参照してください、 [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex)メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>コメント  
  
### <a name="example"></a>例  
 次の例では、使用して、`Create`メソッドで、`CPaneDialog`クラスです。 この例は、[ウィンドウのサイズを設定サンプル](../../visual-cpp-samples.md)します。  
  
 [!code-cpp[NVC_MFC_SetPaneSize&#2;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize&#3;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="a-namehandleinitdialoga--cpanedialoghandleinitdialog"></a><a name="handleinitdialog"></a>CPaneDialog::HandleInitDialog  
 処理、 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428)メッセージです。  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `wParam`  
 既定のキーボード フォーカスを受け取るコントロールへのハンドルします。  
  
 [入力] `lParam`  
 追加の初期化データを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`このメソッドが成功した場合それ以外の場合、`FALSE`です。 さらに、`TRUE`で指定されたコントロールにキーボード フォーカスを設定、`wParam`パラメーターです。`FALSE`既定のキーボード フォーカスを設定できないようにします。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、このメソッドを使用して、コントロールとダイアログ ボックスの外観を初期化します。 フレームワークは、ダイアログ ボックスが表示される前に、このメソッドを呼び出します。  
  
##  <a name="a-namesetoccdialoginfoa--cpanedialogsetoccdialoginfo"></a><a name="setoccdialoginfo"></a>CPaneDialog::SetOccDialogInfo  
 OLE コントロール コンテナーである ダイアログ ボックスのテンプレートを指定します。  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pOccDialogInfo`  
 ダイアログ ボックスのオブジェクトを作成するために使用されるダイアログ ボックス テンプレートへのポインター。 このパラメーターの値が、その後に渡される、 [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols)メソッドです。  
  
### <a name="return-value"></a>戻り値  
 常に `TRUE`。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、サポート、[関数](../../mfc/reference/coccmanager-class.md)クラスは、OLE コントロールのサイトと ActiveX コントロールを管理します。 _AFX_OCC_DIALOG_INFO 構造は、afxocc.h ヘッダー ファイルで定義されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)   
 [ウィンドウ スタイル](../../mfc/reference/window-styles.md)




