---
title: "CDialogImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialogImpl
- ATLWIN/ATL::CDialogImpl
- ATLWIN/ATL::Create
- ATLWIN/ATL::DestroyWindow
- ATLWIN/ATL::DoModal
- ATLWIN/ATL::EndDialog
- ATLWIN/ATL::GetDialogProc
- ATLWIN/ATL::MapDialogRect
- ATLWIN/ATL::OnFinalMessage
- ATLWIN/ATL::DialogProc
- ATLWIN/ATL::StartDialogProc
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, ATL
- CDialogImpl class
ms.assetid: d430bc7b-8a28-4ad3-9507-277bdd2c2c2e
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
ms.openlocfilehash: 732227ef8566ce5e2985a3e65a1153a130df6b20
ms.lasthandoff: 02/24/2017

---
# <a name="cdialogimpl-class"></a>CDialogImpl クラス
このクラスは、モーダルまたはモードレスのダイアログ ボックスを作成するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```  
 
template <class T,  
    class TBase = CWindow>  
    class ATL_NO_VTABLE CDialogImpl : public CDialogImplBaseT<TBase>  
 
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`CDialogImpl`です。  
  
 *TBase*  
 新しいクラスの基本クラス。 既定の基本クラスは[CWindow](../../atl/reference/cwindow-class.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[作成します。](#create)|モードレス ダイアログ ボックスを作成します。|  
|[DestroyWindow](#destroywindow)|モードレス ダイアログ ボックスを破棄します。|  
|[DoModal](#domodal)|モーダル ダイアログ ボックスを作成します。|  
|[EndDialog](#enddialog)|モーダル ダイアログ ボックスを破棄します。|  
  
### <a name="cdialogimplbaset-methods"></a>CDialogImplBaseT メソッド  
  
|||  
|-|-|  
|[GetDialogProc](#getdialogproc)|現在のダイアログ ボックス プロシージャが返されます。|  
|[MapDialogRect](#mapdialogrect)|指定された四角形のダイアログ ボックスの単位を画面の単位 (ピクセル単位) にマップします。|  
|[OnFinalMessage](#onfinalmessage)|通常、最後のメッセージの受信後に呼び出される`WM_NCDESTROY`です。|  
  
### <a name="static-functions"></a>静的関数  
  
|||  
|-|-|  
|[DialogProc](#dialogproc)|ダイアログ ボックスに送信されたメッセージを処理します。|  
|[StartDialogProc](#startdialogproc)|ダイアログ ボックスに送信されたメッセージを処理する最初のメッセージが受信したときに呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 `CDialogImpl`モーダルまたはモードレス ダイアログ ボックスを作成することができます。 `CDialogImpl`適切なハンドラーにメッセージを既定のメッセージ マップを使用して、ダイアログ ボックス プロシージャを提供します。  
  
 基本クラスのデストラクター **~ CWindowImplRoot**ウィンドウがオブジェクトを破棄する前になったことを確認します。  
  
 `CDialogImpl`派生した**CDialogImplBaseT**、さらにから派生した**CWindowImplRoot**します。  
  
> [!NOTE]
>  クラスを定義する必要があります、 **IDD**ダイアログ テンプレート リソース ID を指定するメンバー たとえば、ATL プロジェクト ウィザードは、クラスに次の行を自動的に追加します。  
  
 [!code-cpp[NVC_ATL_Windowing #&41;](../../atl/codesnippet/cpp/cdialogimpl-class_1.h)]  
  
 ここで`MyDlg`は、**短い名前**、ウィザードに入力した**名**ページです。  
  
|詳細情報:|参照トピック|  
|--------------------------------|---------|  
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|  
|ATL のダイアログ ボックスを使用します。|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|  
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|  
|ダイアログ ボックス|[ダイアログ ボックス](http://msdn.microsoft.com/library/windows/desktop/ms632588)およびそれ以降のトピックでは、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="create"></a>CDialogImpl::Create  
 モードレス ダイアログ ボックスを作成します。  
  
```  
HWND Create(
    HWND hWndParent,  
    LPARAM dwInitParam = NULL );  

HWND Create(
    HWND hWndParent,  
    RECT&, 
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]オーナー ウィンドウへのハンドル。  
  
 **RECT >/DOCUMENTS/REPORT1.RDL」の**`rect`  
 [in]A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)  ダイアログ ボックスのサイズと位置を指定する構造体。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定する、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージです。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたダイアログ ボックスへのハンドル。  
  
### <a name="remarks"></a>コメント  
 このダイアログ ボックスが自動的に接続されている、`CDialogImpl`オブジェクトです。 モーダル ダイアログ ボックスを作成するには[DoModal](#domodal)します。 上記の&2; 番目のオーバーライドはでのみ使用[CComControl](../../atl/reference/ccomcontrol-class.md)します。  
  
##  <a name="destroywindow"></a>CDialogImpl::DestroyWindow  
 モードレス ダイアログ ボックスを破棄します。  
  
```  
 
BOOL DestroyWindow();

 
```  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ダイアログ ボックスが正常に破棄された、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 返します。 **TRUE**ダイアログ ボックスが正常に破棄された、それ以外の場合**FALSE**します。  
  
##  <a name="dialogproc"></a>CDialogImpl::DialogProc  
 この静的関数では、ダイアログ ボックス プロシージャを実装します。  
  
```  
 
static LRESULT CALLBACK DialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam);

 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]ダイアログ ボックスへのハンドル。  
  
 `uMsg`  
 [in]ダイアログ ボックスに送信されるメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、メッセージが処理された以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 `DialogProc`適切なハンドラーへのメッセージを送信するのにには、既定のメッセージ マップを使用します。  
  
 オーバーライドできます`DialogProc`メッセージを処理するためのさまざまなメカニズムを提供します。  
  
##  <a name="domodal"></a>CDialogImpl::DoModal  
 モーダル ダイアログ ボックスを作成します。  
  
```   
INT_PTR DoModal(  
    HWND hWndParent = ::GetActiveWindow(),   
    LPARAM dwInitParam = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]オーナー ウィンドウへのハンドル。 既定値はの戻り値、 [GetActiveWindow](http://msdn.microsoft.com/library/windows/desktop/ms646292) Win32 関数です。  
  
 `dwInitParam`  
 [in]ダイアログ ボックスに渡す値を指定する、 **lParam**のパラメーター、 **WM_INITDIALOG**メッセージです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合の値、`nRetCode`への呼び出しで指定されたパラメーター [EndDialog](#enddialog)します。 それ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 このダイアログ ボックスが自動的に接続されている、`CDialogImpl`オブジェクトです。  
  
 モードレス ダイアログ ボックスを作成するには[作成](#create)します。  
  
##  <a name="enddialog"></a>CDialogImpl::EndDialog  
 モーダル ダイアログ ボックスを破棄します。  
  
```   
BOOL EndDialog(int nRetCode); 
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetCode`  
 [in]によって返される値[CDialogImpl::DoModal](#domodal)します。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合は、ダイアログ ボックスが破棄された以外の場合、 **FALSE**します。  
  
### <a name="remarks"></a>コメント  
 `EndDialog`ダイアログのプロシージャを呼び出す必要があります。 Windows ダイアログ ボックスの破棄の値を使用して`nRetCode`の戻り値として`DoModal`、ダイアログ ボックスの作成対象とします。  
  
> [!NOTE]
>  呼び出す必要はありません`EndDialog`モードレス ダイアログ ボックスを破棄します。 呼び出す[CWindow::DestroyWindow](../../atl/reference/cwindow-class.md#destroywindow)代わりにします。  
  
##  <a name="getdialogproc"></a>CDialogImpl::GetDialogProc  
 返します。 `DialogProc`、現在のダイアログ ボックス プロシージャです。  
  
```   
virtual WNDPROC GetDialogProc(); 
```  
  
### <a name="return-value"></a>戻り値  
 現在のダイアログ ボックス プロシージャです。  
  
### <a name="remarks"></a>コメント  
 独自のダイアログのプロシージャを置換するには、このメソッドをオーバーライドします。  
  
##  <a name="mapdialogrect"></a>CDialogImpl::MapDialogRect  
 (Maps) 画面に指定された四角形のダイアログ ボックスの単位の単位 (ピクセル単位) に変換します。  
  
```   
BOOL MapDialogRect(LPRECT lpRect); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、`CRect`オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)更新領域を囲む、更新プログラムのクライアント座標を受け取る構造体。  
  
### <a name="return-value"></a>戻り値  
 更新プログラムが成功した場合は 0 以外。更新が失敗した場合は 0。 拡張されたエラー情報を取得するには、`GetLastError` を呼び出します。  
  
### <a name="remarks"></a>コメント  
 関数は、指定した座標の置き換えます`RECT`変換された座標を持つ構造体、構造の作成 ダイアログ ボックスまたはダイアログ ボックス内でコントロールを配置するために使用できるようにします。  
  
##  <a name="onfinalmessage"></a>CDialogImpl::OnFinalMessage  
 最後のメッセージの受信後に呼び出されます (通常`WM_NCDESTROY`)。  
  
```   
virtual void OnFinalMessage(HWND hWnd); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]破棄されているウィンドウのハンドル。  
  
### <a name="remarks"></a>コメント  
 ウィンドウの破棄後にオブジェクトを自動的に削除する場合は呼び出すことに注意してください`delete this;`ここです。  
  
##  <a name="startdialogproc"></a>CDialogImpl::StartDialogProc  
 ダイアログ ボックスに送信されたメッセージを処理する最初のメッセージを受信すると、1 回だけ呼び出されます。  
  
```   
static LRESULT CALLBACK StartDialogProc(
    HWND hWnd,  
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam); 
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]ダイアログ ボックスへのハンドル。  
  
 `uMsg`  
 [in]ダイアログ ボックスに送信されるメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 ウィンドウ プロシージャです。  
  
### <a name="remarks"></a>コメント  
 最初の呼び出し後`StartDialogProc`、`DialogProc`が設定されていくダイアログの手順およびさらに呼び出しがあります。  
  
## <a name="see-also"></a>関連項目  
 [送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [クラスの概要](../../atl/atl-class-overview.md)
