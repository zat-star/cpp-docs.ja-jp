---
title: "CWindowImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CWindowImpl
- ATL.CWindowImpl
- CWindowImpl
dev_langs:
- C++
helpviewer_keywords:
- CWindowImpl class
- subclassing windows, ATL
ms.assetid: 02eefd45-a0a6-4d1b-99f6-dbf627e2cc2f
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 76827682e96d2aea80880fa7d70c267abe02ee1c
ms.lasthandoff: 02/24/2017

---
# <a name="cwindowimpl-class"></a>CWindowImpl クラス
ウィンドウを作成またはサブクラス化するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class ATL_NO_VTABLE CWindowImpl : public CWindowImplBaseT<TBase, TWinTraits>
```    
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 `CWindowImpl` から派生した新しいクラス。  
  
 *TBase*  
 クラスの基底クラス。 基本クラスは、既定では、 [CWindow](../../atl/reference/cwindow-class.md)します。  
  
 `TWinTraits`  
 A[特徴 (traits) クラス](../../atl/understanding-window-traits.md)ウィンドウのスタイルを定義します。 既定値は、`CControlWinTraits` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWindowImpl::Create](#create)|ウィンドウを作成します。|  
  
### <a name="cwindowimplbaset-methods"></a>CWindowImplBaseT メソッド  
  
|||  
|-|-|  
|[DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|  
|[GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|  
|[GetWindowProc](#getwindowproc)|現在のウィンドウ プロシージャを返します。|  
|[OnFinalMessage](#onfinalmessage)|最後のメッセージが受信された後に (通常は `WM_NCDESTROY`) 呼び出されます。|  
|[SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|  
|[UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|  
  
### <a name="static-methods"></a>静的メソッド  
  
|||  
|-|-|  
|[GetWndClassInfo](#getwndclassinfo)|静的インスタンスを返す[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)、ウィンドウ クラスの情報を管理します。|  
|[3 番目のプロシージャ](#windowproc)|ウィンドウに送信されるメッセージを処理します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[コンテナー内](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|  
  
## <a name="remarks"></a>コメント  
 使用する`CWindowImpl`既存のウィンドウのウィンドウまたはサブクラスを作成します。 `CWindowImpl`ウィンドウ プロシージャは、適切なハンドラーにメッセージをメッセージ マップを使用します。  
  
 `CWindowImpl::Create`管理されているウィンドウ クラスの情報に基づいてウィンドウを作成[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)します。 `CWindowImpl`含む、 [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971)つまりマクロ`CWndClassInfo`新しいウィンドウ クラスを登録します。 既存のウィンドウ クラスをスーパークラスにする場合からクラスを派生`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd)マクロです。 この場合、`CWndClassInfo` は、既存のクラスに基づくウィンドウ クラスを登録しますが、`CWindowImpl::WindowProc` を使用します。 例:  
  
 [!code-cpp[NVC_ATL_Windowing #&43;](../../atl/codesnippet/cpp/cwindowimpl-class_1.h)]  
  
> [!NOTE]
>  `CWndClassInfo` は、1 つのウィンドウ クラスの情報のみを管理するため、`CWindowImpl` のインスタンスによって作成された各ウィンドウは、同じウィンドウ クラスに基づきます。  
  
 `CWindowImpl` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CWindowImpl` オブジェクトにアタッチし、ウィンドウ プロシージャを `CWindowImpl::WindowProc` に変更します。 `CWindowImpl` の各インスタンスは、別のウィンドウをサブクラス化できます。  
  
> [!NOTE]
>  指定されたいずれかの`CWindowImpl`オブジェクト、いずれかを呼び出す**作成**または`SubclassWindow`です。 同じオブジェクトで両方のメソッドを呼び出さないでください。  
  
 他に、 `CWindowImpl`、ATL には、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)を別のオブジェクトに含まれるウィンドウを作成します。  
  
 基本クラスのデストラクター (~ **CWindowImplRoot**) により、オブジェクトが破棄される前に、ウィンドウが消えます。  
  
 `CWindowImpl`派生した**CWindowImplBaseT**から派生した**CWindowImplRoot**から派生した**TBase**と[CMessageMap](../../atl/reference/cmessagemap-class.md)します。  
  
|詳細情報:|参照トピック|  
|--------------------------------|---------|  
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|  
|ATL でのウィンドウの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|  
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMessageMap](../../atl/reference/cmessagemap-class.md)  
  
 `TBase`  
  
 `CWindowImplRoot`  
  
 `CWindowImplBaseT`  
  
 `CWindowImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="a-namecreatea--cwindowimplcreate"></a><a name="create"></a>CWindowImpl::Create  
 新しいウィンドウ クラスに基づくウィンドウを作成します。  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]親またはオーナー ウィンドウへのハンドル。  
  
 `rect`  
 [in]A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ウィンドウの位置を指定する構造体。 `RECT`ポインターまたは参照渡しで渡すことができます。  
  
 `szWindowName`  
 [in]ウィンドウの名前を指定します。 既定値は**NULL**します。  
  
 `dwStyle`  
 [in]ウィンドウのスタイル。 この値は、ウィンドウの特徴 (traits) クラスが提供するスタイルと組み合わされます。 既定値は、特徴 (traits) クラスのスタイルを完全に制御を示します。 使用可能な値の一覧は、次を参照してください。 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwExStyle`  
 [in]拡張ウィンドウ スタイル。 この値は、ウィンドウの特徴 (traits) クラスが提供するスタイルと組み合わされます。 既定値は、特徴 (traits) クラスのスタイルを完全に制御を示します。 使用可能な値の一覧は、次を参照してください。 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `MenuOrID`  
 [in]子ウィンドウの場合、ウィンドウの識別子。 最上位レベルのウィンドウのメニューはウィンドウのハンドルします。 既定値は**0 u**します。  
  
 `lpCreateParam`  
 [in]ウィンドウの作成のデータへのポインター。 詳細については、最終パラメーターの説明を参照して[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、新しく作成されたウィンドウを識別するハンドル。 それ以外の場合、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 **作成**が、まだ登録していない場合は、まず、ウィンドウ クラスを登録します。 新しく作成されたウィンドウが自動的にアタッチ、`CWindowImpl`オブジェクトです。  
  
> [!NOTE]
>  呼び出す必要はありません**作成**既にを呼び出した場合[SubclassWindow](#subclasswindow)します。  
  
 既存のウィンドウ クラスに基づくウィンドウ クラスを使用するからクラスを派生`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd)マクロです。 既存のウィンドウ クラスのウィンドウ プロシージャ[コンテナー内](#m_pfnsuperwindowproc)します。 詳細については、次を参照してください。、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要です。  
  
> [!NOTE]
>  値として 0 が使用する場合、`MenuOrID`パラメーター 0 u として指定する必要があります (既定値) コンパイラのエラーを回避します。  
  
##  <a name="a-namedefwindowproca--cwindowimpldefwindowproc"></a><a name="defwindowproc"></a>CWindowImpl::DefWindowProc  
 によって呼び出される[WindowProc](#windowproc)メッセージ マップで処理されないメッセージを処理します。  
  
```
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);

LRESULT DefWindowProc();
```  
  
### <a name="parameters"></a>パラメーター  
 `uMsg`  
 [in]ウィンドウに送信するメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 メッセージの処理の結果。  
  
### <a name="remarks"></a>コメント  
 既定では、`DefWindowProc`呼び出し、 [CallWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633571)で指定されたウィンドウ プロシージャにメッセージの情報を送信する Win32 関数[コンテナー内](#m_pfnsuperwindowproc)します。  
  
 パラメーターなしの関数は、現在のメッセージから自動的に必要なパラメーターを取得します。  
  
##  <a name="a-namegetcurrentmessagea--cwindowimplgetcurrentmessage"></a><a name="getcurrentmessage"></a>CWindowImpl::GetCurrentMessage  
 パッケージ化されて、現在のメッセージ、`MSG`構造体。  
  
```
const MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>戻り値  
 現在のメッセージ。  
  
##  <a name="a-namegetwindowproca--cwindowimplgetwindowproc"></a><a name="getwindowproc"></a>CWindowImpl::GetWindowProc  
 返します。 `WindowProc`、現在のウィンドウ プロシージャです。  
  
```
virtual WNDPROC GetWindowProc();
```  
  
### <a name="return-value"></a>戻り値  
 現在のウィンドウ プロシージャです。  
  
### <a name="remarks"></a>コメント  
 独自のウィンドウ プロシージャを置換するには、このメソッドをオーバーライドします。  
  
##  <a name="a-namegetwndclassinfoa--cwindowimplgetwndclassinfo"></a><a name="getwndclassinfo"></a>CWindowImpl::GetWndClassInfo  
 によって呼び出される[作成](#create)ウィンドウ クラスの情報にアクセスします。  
  
```
static CWndClassInfo& GetWndClassInfo();
```  
  
### <a name="return-value"></a>戻り値  
 静的インスタンス[CWndClassInfo](../../atl/reference/cwndclassinfo-class.md)します。  
  
### <a name="remarks"></a>コメント  
 既定では、`CWindowImpl`を通じてこのメソッドを取得、 [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971)マクロで、新しいウィンドウ クラスを指定します。  
  
 クラスを派生を既存のウィンドウ クラスをスーパークラス化、`CWindowImpl`を含めると、 [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd)をオーバーライドするマクロ`GetWndClassInfo`します。 詳細については、次を参照してください。、 [CWindowImpl](../../atl/reference/cwindowimpl-class.md)の概要です。  
  
 使用するだけでなく、`DECLARE_WND_CLASS`と`DECLARE_WND_SUPERCLASS`マクロをオーバーライドできます`GetWndClassInfo`独自の実装にします。  
  
##  <a name="a-namempfnsuperwindowproca--cwindowimplmpfnsuperwindowproc"></a><a name="m_pfnsuperwindowproc"></a>CWindowImpl::m_pfnSuperWindowProc  
 によって、ウィンドウには、次のウィンドウ プロシージャのいずれかを指します。  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>コメント  
  
|ウィンドウの種類|ウィンドウ プロシージャ|  
|--------------------|----------------------|  
|新しいウィンドウ クラスを使用して指定に基づいて、 [DECLARE_WND_CLASS](http://msdn.microsoft.com/library/55247a72-fb9e-4bde-87f3-747c08076971)マクロです。|[DefWindowProc](http://msdn.microsoft.com/library/windows/desktop/ms633572) Win32 関数です。|  
|既存のクラスを使用して指定を変更するウィンドウ クラスに基づいて、 [DECLARE_WND_SUPERCLASS](http://msdn.microsoft.com/library/650337b6-4973-41e5-8c36-55f90327bdcd)マクロです。|既存のウィンドウ クラスのウィンドウ プロシージャです。|  
|サブクラス化されたウィンドウです。|サブクラス化されたウィンドウの元のウィンドウ プロシージャです。|  
  
 [CWindowImpl::DefWindowProc](#defwindowproc)に保存されているウィンドウ プロシージャに情報メッセージを送信`m_pfnSuperWindowProc`します。  
  
##  <a name="a-nameonfinalmessagea--cwindowimplonfinalmessage"></a><a name="onfinalmessage"></a>CWindowImpl::OnFinalMessage  
 最後のメッセージの受信後に呼び出されます (通常`WM_NCDESTROY`)。  
  
```
virtual void OnFinalMessage(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]破棄されているウィンドウのハンドル。  
  
### <a name="remarks"></a>コメント  
 既定の実装`OnFinalMessage`、何もしませんが、ウィンドウを破棄する前にクリーンアップを処理するには、この関数をオーバーライドできます。 ウィンドウの破棄後にオブジェクトを自動的に削除する場合は、呼び出す`delete this;`この関数にします。  
  
##  <a name="a-namesubclasswindowa--cwindowimplsubclasswindow"></a><a name="subclasswindow"></a>CWindowImpl::SubclassWindow  
 識別される、ウィンドウのサブクラス`hWnd`に接続し、`CWindowImpl`オブジェクトです。  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]サブクラス化されているウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ウィンドウが正常にサブクラス化された、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 では、サブクラス化されたウィンドウ[CWindowImpl::WindowProc](#windowproc)します。 元のウィンドウ プロシージャ[コンテナー内](#m_pfnsuperwindowproc)します。  
  
> [!NOTE]
>  呼び出す必要はありません`SubclassWindow`既にを呼び出した場合[作成](#create)します。  
  
##  <a name="a-nameunsubclasswindowa--cwindowimplunsubclasswindow"></a><a name="unsubclasswindow"></a>CWindowImpl::UnsubclassWindow  
 サブクラス化されたウィンドウのデタッチ、`CWindowImpl`オブジェクトし、復元に保存されている元のウィンドウ プロシージャ[コンテナー内](#m_pfnsuperwindowproc)します。  
  
```
HWND UnsubclassWindow();
```  
  
### <a name="return-value"></a>戻り値  
 以前にサブクラス化されたウィンドウのハンドル。  
  
##  <a name="a-namewindowproca--cwindowimplwindowproc"></a><a name="windowproc"></a>CWindowImpl::WindowProc  
 この静的関数では、ウィンドウ プロシージャを実装します。  
  
```
static LRESULT CALLBACK WindowProc(
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]ウィンドウのハンドル。  
  
 `uMsg`  
 [in]ウィンドウに送信するメッセージ。  
  
 `wParam`  
 [in]その他のメッセージに固有の情報です。  
  
 `lParam`  
 [in]その他のメッセージに固有の情報です。  
  
### <a name="return-value"></a>戻り値  
 メッセージの処理の結果。  
  
### <a name="remarks"></a>コメント  
 `WindowProc`既定のメッセージ マップを使用して (で宣言された[送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)) に適切なハンドラーへのメッセージを転送します。 必要に応じて、`WindowProc`呼び出し[DefWindowProc](#defwindowproc)追加のメッセージ処理のためです。 最後のメッセージが処理されない場合`WindowProc`は、次の処理します。  
  
-   ウィンドウをサブクラス化されたなかった場合は、サブクラスを実行します。  
  
-   `m_hWnd` を消去します。  
  
-   呼び出し[OnFinalMessage](#onfinalmessage)ウィンドウが破棄される前にします。  
  
 オーバーライドできます`WindowProc`メッセージを処理するためのさまざまなメカニズムを提供します。  
  
## <a name="see-also"></a>関連項目  
 [送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

