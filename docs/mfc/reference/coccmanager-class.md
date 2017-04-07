---
title: "クラスの関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COccManager
- AFXOCC/COccManager
- AFXOCC/COccManager::CreateContainer
- AFXOCC/COccManager::CreateDlgControls
- AFXOCC/COccManager::CreateSite
- AFXOCC/COccManager::GetDefBtnCode
- AFXOCC/COccManager::IsDialogMessage
- AFXOCC/COccManager::IsLabelControl
- AFXOCC/COccManager::IsMatchingMnemonic
- AFXOCC/COccManager::OnEvent
- AFXOCC/COccManager::PostCreateDialog
- AFXOCC/COccManager::PreCreateDialog
- AFXOCC/COccManager::SetDefaultButton
- AFXOCC/COccManager::SplitDialogTemplate
dev_langs:
- C++
helpviewer_keywords:
- custom controls [MFC], sites
- COccManager class
- CNoTrackObject class
- ActiveX control containers [C++], control site
ms.assetid: 7d47aeed-d1ab-48e3-b4cf-d429718e370a
caps.latest.revision: 20
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
ms.openlocfilehash: 14a75c491a7061d921d6c0c250c6224f4e7d2f04
ms.lasthandoff: 02/24/2017

---
# <a name="coccmanager-class"></a>関数のクラス
`COleControlContainer` オブジェクトと `COleControlSite` オブジェクトによって実装されるさまざまなカスタム コントロール サイトを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class COccManager : public CNoTrackObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COccManager::CreateContainer](#createcontainer)|作成、 **COleContainer**オブジェクトです。|  
|[COccManager::CreateDlgControls](#createdlgcontrols)|関連付けられたによってホストされている ActiveX コントロールを作成`COleContainer`オブジェクトです。|  
|[COccManager::CreateSite](#createsite)|
          `COleClientSite` オブジェクトを作成します。|  
|[COccManager::GetDefBtnCode](#getdefbtncode)|既定のボタンのコードを取得します。|  
|[COccManager::IsDialogMessage](#isdialogmessage)|ダイアログ メッセージの対象を決定します。|  
|[COccManager::IsLabelControl](#islabelcontrol)|指定したコントロールがラベル コントロールであるかどうかを判断します。|  
|[COccManager::IsMatchingMnemonic](#ismatchingmnemonic)|現在のニーモニックに指定されたコントロールのニーモニックと一致するかどうかを判断します。|  
|[COccManager::OnEvent](#onevent)|指定したイベントを処理しようとします。|  
|[COccManager::PostCreateDialog](#postcreatedialog)|ダイアログの作成時に割り当てられているリソースを解放します。|  
|[COccManager::PreCreateDialog](#precreatedialog)|ActiveX コントロールのダイアログ テンプレートを処理します。|  
|[COccManager::SetDefaultButton](#setdefaultbutton)|指定したコントロールの既定の状態を切り替えます。|  
|[COccManager::SplitDialogTemplate](#splitdialogtemplate)|指定したダイアログ テンプレートでコモン コントロールから、既存の ActiveX コントロールを分離します。|  
  
## <a name="remarks"></a>コメント  
 基本クラス**ラップ**、文書化されていない基本クラス (AFXTLS にあります。H)。 MFC フレームワークによっては、使用するために設計されたから派生したクラス、**ラップ**クラスは、メモリ リークの検出から除外されます。 直接派生させることはお勧めできません**ラップ**します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CNoTrackObject`  
  
 `COccManager`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxocc.h  
  
##  <a name="createcontainer"></a>COccManager::CreateContainer  
 コントロールのコンテナーを作成するために、フレームワークによって呼び出されます。  
  
```  
virtual COleControlContainer* CreateContainer(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カスタムのサイト コンテナーに関連付けられたウィンドウ オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しく作成したコンテナーへのポインターそれ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 カスタムのサイトの作成の詳細については、次を参照してください。 [COleControlContainer::AttachControlSite](../../mfc/reference/colecontrolcontainer-class.md#attachcontrolsite)します。  
  
##  <a name="createdlgcontrols"></a>COccManager::CreateDlgControls  
 指定された ActiveX コントロールを作成するには、この関数を呼び出して、`pOccDialogInfo`パラメーター。  
  
```  
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    LPCTSTR lpszResourceName,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);

 
virtual BOOL CreateDlgControls(
    CWnd* pWndParent,  
    void* lpResource,  
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndParent*  
 ダイアログ オブジェクトの親へのポインター。  
  
 `lpszResourceName`  
 作成されるリソースの名前。  
  
 `pOccDialogInfo`  
 ダイアログ オブジェクトの作成に使用するダイアログ テンプレートへのポインター。  
  
 `lpResource`  
 リソースへのポインター。  
  
### <a name="return-value"></a>戻り値  
 コントロールが正常に作成された場合は&0; 以外それ以外の場合&0; を返します。  
  
##  <a name="createsite"></a>COccManager::CreateSite  
 コントロール サイトを指すコンテナーにホストを作成するためのフレームワークと呼ばれる`pCtrlCont`です。  
  
```  
virtual COleControlSite* CreateSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>パラメーター  
 `pCtrlCont`  
 新しいコントロール サイトをホストするコントロールのコンテナーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたコントロール サイトへのポインター。  
  
### <a name="remarks"></a>コメント  
 カスタム コントロールを作成するには、この関数をオーバーライドして、サイト、[メンバー](../../mfc/reference/colecontrolsite-class.md)-クラスを派生します。  
  
 各コントロールのコンテナーには、複数のサイトをホストできます。 複数の呼び出しで追加のサイトを作成`CreateSite`します。  
  
##  <a name="getdefbtncode"></a>COccManager::GetDefBtnCode  
 この関数では、コントロールが既定のプッシュ ボタンかどうかを決定します。  
  
```  
static DWORD AFX_CDECL GetDefBtnCode(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ボタン コントロールを含むウィンドウのオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 次のいずれかの値です。  
  
- **DLGC_DEFPUSHBUTTON**コントロールがダイアログ ボックスの既定のボタンです。  
  
- **DLGC_UNDEFPUSHBUTTON**コントロールがダイアログ ボックスの既定のボタンではありません。  
  
- **0**コントロールがボタンではありません。  
  
##  <a name="isdialogmessage"></a>COccManager::IsDialogMessage  
 メッセージが、指定のダイアログ ボックスにしてである場合は、メッセージを処理するかどうかを調べるためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL IsDialogMessage(
    CWnd* pWndDlg,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 *pWndDlg*  
 メッセージの対象となるダイアログへのポインター。  
  
 `lpMsg`  
 ポインター、`MSG`確認するメッセージを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理された場合は&0; 以外。それ以外の場合&0; を返します。  
  
### <a name="remarks"></a>コメント  
 既定の動作`IsDialogMessage`キーボード メッセージを確認し、対応するダイアログ ボックスの選択内容に変換します。 たとえば、TAB キーを押すと、次のコントロールまたはコントロールのグループを選択します。  
  
 指定したダイアログ ボックスに送信されるメッセージのカスタム動作を提供するには、この関数をオーバーライドします。  
  
##  <a name="islabelcontrol"></a>COccManager::IsLabelControl  
 この関数では、指定したコントロールがラベル コントロールかどうかを決定します。  
  
```  
static BOOL AFX_CDECL IsLabelControl(CWnd* pWnd);  
static BOOL AFX_CDECL IsLabelControl(COleControlSiteOrWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コントロールを含むウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 コントロールがラベルである場合は&0; 以外。それ以外の場合&0;  
  
### <a name="remarks"></a>コメント  
 ラベル コントロールは、任意のコントロールは、順序の次のラベルのように機能する&1; つです。  
  
##  <a name="ismatchingmnemonic"></a>COccManager::IsMatchingMnemonic  
 現在のニーモニックがコントロールによって表されると一致するかどうかを判断するには、この関数を呼び出します。  
  
```  
static BOOL AFX_CDECL IsMatchingMnemonic(
    CWnd* pWnd,  
    LPMSG lpMsg);

 
static BOOL AFX_CDECL IsMatchingMnemonic(
    COleControlSiteOrWnd* pWnd,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コントロールを含むウィンドウへのポインター。  
  
 `lpMsg`  
 一致するようにニーモニックを含むメッセージへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ニーモニック コントロールに一致する場合は&0; 以外。それ以外の場合&0;  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onevent"></a>COccManager::OnEvent  
 指定したイベントを処理するためにフレームワークによって呼び出されます。  
  
```  
virtual BOOL OnEvent(
    CCmdTarget* pCmdTarget,  
    UINT idCtrl,  
    AFX_EVENT* pEvent,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 *pCmdTarget*  
 ポインター、`CCmdTarget`オブジェクト、イベントを処理しようとしています。  
  
 `idCtrl`  
 コントロールのリソース ID です。  
  
 `pEvent`  
 処理されるイベントです。  
  
 `pHandlerInfo`  
 かどうか**NULL**、`OnEvent`を入力、 **pTarget**と**pmf**のメンバー、 **AFX_CMDHANDLERINFO**ディスパッチ コマンドではなく構造体。 通常、このパラメーターに指定する必要があります**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 イベントが処理された場合、それ以外の場合&0;&0; 以外の値。  
  
### <a name="remarks"></a>コメント  
 イベント処理の既定のプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="precreatedialog"></a>COccManager::PreCreateDialog  
 実際のダイアログ ボックスを作成する前に ActiveX コントロールのダイアログ テンプレートを処理するためにフレームワークによって呼び出されます。  
  
```  
virtual const DLGTEMPLATE* PreCreateDialog(
    _AFX_OCC_DIALOG_INFO* pOccDialogInfo,  
    const DLGTEMPLATE* pOrigTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO**ダイアログ テンプレートと、ダイアログによってホストされているすべての ActiveX コントロールに関する情報を含む構造体。  
  
 *pOrigTemplate*  
 ダイアログ ボックスの作成に使用するダイアログ テンプレートへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスを作成するために使用するダイアログ テンプレート構造体へのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の動作への呼び出しは、 `SplitDialogTemplate`ActiveX がある場合は、存在制御の決定、および表示されるダイアログ テンプレートを返します。  
  
 ActiveX コントロールのホスト ダイアログ ボックスを作成するプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="postcreatedialog"></a>COccManager::PostCreateDialog  
 ダイアログ テンプレートに割り当てられたメモリを解放するためにフレームワークによって呼び出されます。  
  
```  
virtual void PostCreateDialog(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `pOccDialogInfo`  
 **_AFX_OCC_DIALOG_INFO**ダイアログ テンプレートと、ダイアログによってホストされているすべての ActiveX コントロールに関する情報を含む構造体。  
  
### <a name="remarks"></a>コメント  
 このメモリの割り当てへの呼び出しによって`SplitDialogTemplate`、ダイアログ ボックスで、ホストされる ActiveX コントロールに使用されたとします。  
  
 ダイアログ ボックスのオブジェクトで使用されたリソースのクリーンアップのプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
##  <a name="setdefaultbutton"></a>COccManager::SetDefaultButton  
 この関数では、既定のボタンとして設定します。  
  
```  
static void AFX_CDECL SetDefaultButton(
    CWnd* pWnd,  
    BOOL bDefault);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 コントロールを含むウィンドウへのポインター。  
  
 `bDefault`  
 以外の場合は、コントロールが既定のボタンになる必要があります。それ以外の場合&0; を返します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  コントロールが必要、 **OLEMISC_ACTSLIKEBUTTON**ステータス ビットが設定されます。 詳細については**入ります**フラグを参照してください、[入ります](http://msdn.microsoft.com/library/windows/desktop/ms678497)のトピック、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="splitdialogtemplate"></a>COccManager::SplitDialogTemplate  
 コモン ダイアログ コントロールから ActiveX コントロールを分割するためにフレームワークによって呼び出されます。  
  
```  
virtual DLGTEMPLATE* SplitDialogTemplate(
    const DLGTEMPLATE* pTemplate,  
    DLGITEMTEMPLATE** ppOleDlgItems);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTemplate`  
 確認するダイアログ テンプレートへのポインター。  
  
 `ppOleDlgItems`  
 ActiveX コントロールでは、ダイアログ ボックスの項目へのポインターのリスト。  
  
### <a name="return-value"></a>戻り値  
 非 ActiveX コントロールだけを含むダイアログ テンプレートの構造体へのポインター。 ActiveX コントロールも存在しない場合、 **NULL**が返されます。  
  
### <a name="remarks"></a>コメント  
 すべての ActiveX コントロールが見つかった場合は、テンプレートが分析され、非 ActiveX コントロールだけを含む、新しいテンプレートを作成します。 このプロセス中に見つかったすべての ActiveX コントロールに追加`ppOleDlgItems`します。  
  
 テンプレートでは、ActiveX コントロールがない場合**NULL**が返される*です。*  
  
> [!NOTE]
>  新しいテンプレートを解放に割り当てられるメモリ、`PostCreateDialog`関数です。  
  
 このプロセスをカスタマイズするには、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [メンバー クラス](../../mfc/reference/colecontrolsite-class.md)   
 [メンバー クラス](../../mfc/reference/colecontrolcontainer-class.md)

