---
title: "CAxDialogImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
dev_langs:
- C++
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 71e77ac6b8d2a89e384817020772bb855ce2d573
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl クラス
このクラスは、ActiveX コントロールをホストする ダイアログ ボックス (モーダルまたはモードレス) を実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class TBase = CWindow>  
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`CAxDialogImpl`です。  
  
 *TBase*  
 基本ウィンドウ クラス**CDialogImplBaseT**します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|オブジェクトのシンク イベント マップのすべてのエントリをアドバイズするか、このメソッドを呼び出します。|  
|[CAxDialogImpl::Create](#create)|モードレス ダイアログ ボックスを作成するには、このメソッドを呼び出します。|  
|[CAxDialogImpl::DestroyWindow](#destroywindow)|モードレス ダイアログ ボックスを破棄するには、このメソッドを呼び出します。|  
|[CAxDialogImpl::DoModal](#domodal)|モーダル ダイアログ ボックスを作成するには、このメソッドを呼び出します。|  
|[CAxDialogImpl::EndDialog](#enddialog)|モーダル ダイアログ ボックスを破棄するには、このメソッドを呼び出します。|  
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|ポインターを取得するには、このメソッドを呼び出して、`DialogProc`コールバック関数。|  
|[CAxDialogImpl::GetIDD](#getidd)|ダイアログ テンプレート リソース ID を取得するには、このメソッドを呼び出す|  
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|このダイアログ ボックスのメッセージが対象とするかどうかを特定するには、このメソッドを呼び出すし、メッセージを処理している場合。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAxDialogImpl::m_bModal](#m_bmodal)|デバッグにのみ存在する変数は、ビルドし、ダイアログ ボックスがモーダルの場合は true に設定されています。|  
  
## <a name="remarks"></a>コメント  
 `CAxDialogImpl`使用すると、モーダルまたはモードレスのダイアログ ボックスを作成できます。 `CAxDialogImpl`適切なハンドラーにメッセージを既定のメッセージ マップを使用して、ダイアログ ボックス プロシージャを提供します。  
  
 `CAxDialogImpl`派生した`CDialogImplBaseT`、さらにから派生した*TBase* (既定では、 `CWindow`) と`CMessageMap`です。  
  
 クラスは、ダイアログ テンプレート リソース ID を指定する IDD メンバーを定義する必要があります。 ATL ダイアログ オブジェクトを使用して、たとえば、追加、**クラスの追加** ダイアログ ボックスが自動的に次の行をクラスに追加します。  
  
 [!code-cpp[NVC_ATL_Windowing #&41;](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]  
  
 ここで`MyDialog`は、**短い名前**ATL ダイアログ ウィザードに入力します。  
  
 参照してください[ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)の詳細。  
  
 モーダル ダイアログ ボックス上の ActiveX コントロールを使用して作成注`CAxDialogImpl`アクセラレータ キーはサポートされません。 [作成] ダイアログ ボックスのアクセラレータ キーをサポートするために`CAxDialogImpl`モードレス ダイアログ ボックスを作成し、独自のメッセージ ループを使用して、 [CAxDialogImpl::IsDialogMessage](#isdialogmessage)アクセラレータ キーを処理するキューからメッセージを取得した後です。  
  
 詳細については`CAxDialogImpl`を参照してください[ATL コントロール コンテインメント FAQ](../../atl/atl-control-containment-faq.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CDialogImplBaseT`  
  
 `CAxDialogImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="advisesinkmap"></a>CAxDialogImpl::AdviseSinkMap  
 オブジェクトのシンク イベント マップのすべてのエントリをアドバイズするか、このメソッドを呼び出します。  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAdvise`  
 シンクのすべてのエントリがすることに注意している場合は true に設定します。false の場合、すべてのシンク エントリは、アドバイズを中止すること。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
##  <a name="create"></a>CAxDialogImpl::Create  
 モードレス ダイアログ ボックスを作成するには、このメソッドを呼び出します。  
  
```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]オーナー ウィンドウへのハンドル。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定する、`lParam`のパラメーター、 **WM_INITDIALOG**メッセージです。  
  
 **RECT &GT;/DOCUMENTS/REPORT1.RDL」の**  
 このパラメーターは使用されません。 このパラメーターが渡された`CComControl`です。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたダイアログ ボックスへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このダイアログ ボックスが自動的に接続されている、`CAxDialogImpl`オブジェクトです。 モーダル ダイアログ ボックスを作成するには[DoModal](#domodal)します。  
  
 ダイアログ ボックスを併用するためにのみ&2; 番目のオーバーライドが提供される[CComControl](../../atl/reference/ccomcontrol-class.md)します。  
  
##  <a name="destroywindow"></a>CAxDialogImpl::DestroyWindow  
 モードレス ダイアログ ボックスを破棄するには、このメソッドを呼び出します。  
  
```
BOOL DestroyWindow();
```  
  
### <a name="return-value"></a>戻り値  
 ウィンドウが破棄された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要はありません`DestroyWindow`モーダル ダイアログ ボックスを破棄します。 呼び出す[EndDialog](#enddialog)代わりにします。  
  
##  <a name="domodal"></a>CAxDialogImpl::DoModal  
 モーダル ダイアログ ボックスを作成するには、このメソッドを呼び出します。  
  
```
INT_PTR DoModal(
  HWND hWndParent = ::GetActiveWindow(), 
  LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]オーナー ウィンドウへのハンドル。 既定値はの戻り値、 [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 関数です。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定する、`lParam`のパラメーター、 **WM_INITDIALOG**メッセージです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合の値、`nRetCode`への呼び出しで指定されたパラメーター [EndDialog](#enddialog)以外の場合、-1 です。  
  
### <a name="remarks"></a>コメント  
 このダイアログ ボックスが自動的に接続されている、`CAxDialogImpl`オブジェクトです。  
  
 モードレス ダイアログ ボックスを作成するには[作成](#create)します。  
  
##  <a name="enddialog"></a>CAxDialogImpl::EndDialog  
 モーダル ダイアログ ボックスを破棄するには、このメソッドを呼び出します。  
  
```
BOOL EndDialog(int nRetCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetCode`  
 [in]によって返される値[DoModal](#domodal)します。  
  
### <a name="return-value"></a>戻り値  
 ダイアログ ボックスが破棄された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 `EndDialog`ダイアログ ボックス プロシージャを呼び出す必要があります。 Windows ダイアログ ボックスの破棄の値を使用して`nRetCode`の戻り値として`DoModal`、ダイアログ ボックスの作成対象とします。  
  
> [!NOTE]
>  呼び出す必要はありません`EndDialog`モードレス ダイアログ ボックスを破棄します。 呼び出す[DestroyWindow](#destroywindow)代わりにします。  
  
##  <a name="getdialogproc"></a>CAxDialogImpl::GetDialogProc  
 ポインターを取得するには、このメソッドを呼び出して、`DialogProc`コールバック関数。  
  
```
virtual DLGPROC GetDialogProc();
```  
  
### <a name="return-value"></a>戻り値  
 ポインターを返す、`DialogProc`コールバック関数。  
  
### <a name="remarks"></a>コメント  
 `DialogProc`関数は、アプリケーション定義のコールバック関数。  
  
##  <a name="getidd"></a>CAxDialogImpl::GetIDD  
 ダイアログ テンプレート リソース ID を取得するには、このメソッドを呼び出す  
  
```
int GetIDD();
```  
  
### <a name="return-value"></a>戻り値  
 ダイアログ テンプレート リソース ID を返します。  
  
##  <a name="isdialogmessage"></a>CAxDialogImpl::IsDialogMessage  
 このダイアログ ボックスのメッセージが対象とするかどうかを特定するには、このメソッドを呼び出すし、メッセージを処理している場合。  
  
```
BOOL IsDialogMessage(LPMSG pMsg);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMsg`  
 ポインター、 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958)確認するメッセージを格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 メッセージが処理されたかどうかに TRUE を返します。  
  
### <a name="remarks"></a>コメント  
 メッセージ ループ内から呼び出されるメソッドです。  
  
##  <a name="m_bmodal"></a>CAxDialogImpl::m_bModal  
 デバッグにのみ存在する変数は、ビルドし、ダイアログ ボックスがモーダルの場合は true に設定されています。  
  
```
bool m_bModal;
```  
  
## <a name="see-also"></a>関連項目  
 [CDialogImpl クラス](../../atl/reference/cdialogimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

