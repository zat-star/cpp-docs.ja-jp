---
title: "CContainedWindowT クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContainedWindowT
- ATLWIN/ATL::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::CContainedWindowT
- ATLWIN/ATL::CContainedWindowT::Create
- ATLWIN/ATL::CContainedWindowT::DefWindowProc
- ATLWIN/ATL::CContainedWindowT::GetCurrentMessage
- ATLWIN/ATL::CContainedWindowT::RegisterWndSuperclass
- ATLWIN/ATL::CContainedWindowT::SubclassWindow
- ATLWIN/ATL::CContainedWindowT::SwitchMessageMap
- ATLWIN/ATL::CContainedWindowT::UnsubclassWindow
- ATLWIN/ATL::CContainedWindowT::WindowProc
- ATLWIN/ATL::CContainedWindowT::m_dwMsgMapID
- ATLWIN/ATL::CContainedWindowT::m_lpszClassName
- ATLWIN/ATL::CContainedWindowT::m_pfnSuperWindowProc
- ATLWIN/ATL::CContainedWindowT::m_pObject
dev_langs:
- C++
helpviewer_keywords:
- CContainedWindow class
- contained windows
- CContainedWindowT class
ms.assetid: cde0ca36-9347-4068-995a-d294dae57ca9
caps.latest.revision: 23
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
ms.openlocfilehash: e10aa4b455696fd217f88b6eb1de2421fccda6de
ms.lasthandoff: 02/24/2017

---
# <a name="ccontainedwindowt-class"></a>CContainedWindowT クラス
このクラスは、別のオブジェクト内に含まれるウィンドウを実装します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class TBase = CWindow, class TWinTraits = CControlWinTraits>  
class CContainedWindowT : public TBase
```  
  
#### <a name="parameters"></a>パラメーター  
 *TBase*  
 新しいクラスの基本クラス。 既定の基本クラスは`CWindow`です。  
  
 `TWinTraits`  
 ウィンドウのスタイルを定義する特徴 (traits) クラス。 既定値は、`CControlWinTraits` です。  
  
> [!NOTE]
> [CContainedWindow](ccontainedwindowt-class.md)特殊化`CContainedWindowT`します。 基本クラスまたは特徴 (traits) を変更する場合を使用して`CContainedWindowT`直接します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::CContainedWindowT](#ccontainedwindowt)|コンストラクターです。 指定するメッセージ マップが含まれているウィンドウのメッセージを処理するデータ メンバーを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::Create](#create)|ウィンドウを作成します。|  
|[CContainedWindowT::DefWindowProc](#defwindowproc)|既定のメッセージ処理を提供します。|  
|[CContainedWindowT::GetCurrentMessage](#getcurrentmessage)|現在のメッセージを返します。|  
|[CContainedWindowT::RegisterWndSuperclass](#registerwndsuperclass)|コンテナー内のウィンドウのウィンドウ クラスを登録します。|  
|[CContainedWindowT::SubclassWindow](#subclasswindow)|ウィンドウをサブクラス化します。|  
|[CContainedWindowT::SwitchMessageMap](#switchmessagemap)|変更をメッセージ マップが含まれているウィンドウのメッセージの処理に使用します。|  
|[CContainedWindowT::UnsubclassWindow](#unsubclasswindow)|前にサブクラス化されたウィンドウを復元します。|  
|[この段階](#windowproc)|(静的)コンテナー内のウィンドウに送信されたメッセージを処理します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CContainedWindowT::m_dwMsgMapID](#m_dwmsgmapid)|どのメッセージ マップが含まれているウィンドウのメッセージを処理を識別します。|  
|[CContainedWindowT::m_lpszClassName](#m_lpszclassname)|新しいウィンドウ クラスの基になる既存のウィンドウ クラスの名前を指定します。|  
|[CContainedWindowT::m_pfnSuperWindowProc](#m_pfnsuperwindowproc)|ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。|  
|[CContainedWindowT::m_pObject](#m_pobject)|親オブジェクトへのポインター。|  
  
## <a name="remarks"></a>コメント  
 `CContainedWindowT`別のオブジェクト内に含まれるウィンドウを実装します。 `CContainedWindowT`ウィンドウ プロシージャの使用が適切なハンドラーに直接メッセージを含んでいるオブジェクトのマップに、メッセージのです。 構築するときに、`CContainedWindowT`オブジェクトを指定する、メッセージ マップを使用する必要があります。  
  
 `CContainedWindowT`既存のウィンドウ クラスをスーパークラス化して、新しいウィンドウを作成できます。 **作成**メソッドは、まずは既存のクラスに基づいていますが、使用するウィンドウ クラスを登録`CContainedWindowT::WindowProc`します。 **作成**し、この新しいウィンドウ クラスに基づくウィンドウを作成します。 各インスタンス`CContainedWindowT`スーパークラス別のウィンドウ クラスのことができます。  
  
 `CContainedWindowT` は、ウィンドウのサブクラス化もサポートします。 `SubclassWindow` メソッドは、既存のウィンドウを `CContainedWindowT` オブジェクトにアタッチし、ウィンドウ プロシージャを `CContainedWindowT::WindowProc` に変更します。 `CContainedWindowT` の各インスタンスは、別のウィンドウをサブクラス化できます。  
  
> [!NOTE]
>  指定されたいずれかの`CContainedWindowT`オブジェクト、いずれかを呼び出す**作成**または`SubclassWindow`です。 同じオブジェクトで両方のメソッドを呼び出しません必要があります。  
  
 使用すると、**コントロールの追加**ウィザードが自動的に追加オプション、ATL プロジェクト ウィザードで、`CContainedWindowT`コントロールを実装するクラスにデータ メンバーです。 次の例では、コンテナー内のウィンドウを宣言する方法を示しています。  
  
 [!code-cpp[NVC_ATL_Windowing #&38;](../../atl/codesnippet/cpp/ccontainedwindowt-class_1.h)]  
  
 [!code-cpp[NVC_ATL_Windowing&#39;](../../atl/codesnippet/cpp/ccontainedwindowt-class_2.h)]  
  
 [!code-cpp[NVC_ATL_Windowing #&40;](../../atl/codesnippet/cpp/ccontainedwindowt-class_3.h)]  
  
|詳細情報:|参照トピック|  
|--------------------------------|---------|  
|コントロールの作成|[ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)|  
|ATL でのウィンドウの使用|[ATL ウィンドウ クラス](../../atl/atl-window-classes.md)|  
|ATL プロジェクト ウィザード|[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)|  
|Windows|[Windows](http://msdn.microsoft.com/library/windows/desktop/ms632595)とそれ以降のトピックでは、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `TBase`  
  
 `CContainedWindowT`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
  
##  <a name="ccontainedwindowt"></a>CContainedWindowT::CContainedWindowT  
 コンス トラクターは、データ メンバーを初期化します。  
  
```
CContainedWindowT(
    LPTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);

CContainedWindowT(
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0)
    CContainedWindowT();
```     
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 [in]コンテナー内のウィンドウの基になる既存のウィンドウ クラスの名前。  
  
 `pObject`  
 [in]メッセージ マップを宣言する親オブジェクトへのポインター。 このオブジェクトのクラスから派生しなければなりません[CMessageMap](../../atl/reference/cmessagemap-class.md)します。  
  
 `dwMsgMapID`  
 [in]コンテナー内のウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値 0 は、指定で宣言された既定のメッセージ マップ[送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)します。 宣言された代替のメッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)、渡す`msgMapID`します。  
  
### <a name="remarks"></a>コメント  
 新しいウィンドウを作成する場合は、[作成](#create)の既存のウィンドウ クラスの名前を渡す必要があります、`lpszClassName`パラメーター。 例については、次を参照してください。、 [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md)の概要です。  
  
 次の&3; つのコンス トラクターがあります。  
  
-   3 つの引数を持つコンス トラクターと通常呼ばれる&1; つです。  
  
-   2 つの引数を持つコンス トラクターからクラス名を使用して**トラクター**します。  
  
-   引数なしのコンス トラクターは、後で、引数を指定する場合に使用されます。 呼び出すと、ウィンドウ クラス名、メッセージ マップ オブジェクト、およびメッセージ マップの ID を指定する必要があります**作成**します。  
  
 場合は、既存のウィンドウをサブクラスから[SubclassWindow](#subclasswindow)、`lpszClassName`値は使用されません。 したがって、渡すことができます**NULL**このパラメーターにします。  
  
##  <a name="create"></a>CContainedWindowT::Create  
 呼び出し[RegisterWndSuperclass](#registerwndsuperclass)は既存のクラスに基づいていますが、使用されるウィンドウ クラスを登録する[この段階](#windowproc)します。  
  
```
HWND Create(  
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);

HWND Create(
    LPCTSTR lpszClassName,
    CMessageMap* pObject,
    DWORD dwMsgMapID,
    HWND hWndParent,
    _U_RECT rect,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 [in]コンテナー内のウィンドウの基になる既存のウィンドウ クラスの名前。  
  
 `pObject`  
 [in]メッセージ マップを宣言する親オブジェクトへのポインター。 このオブジェクトのクラスから派生しなければなりません[CMessageMap](../../atl/reference/cmessagemap-class.md)します。  
  
 `dwMsgMapID`  
 [in]コンテナー内のウィンドウのメッセージを処理するメッセージ マップを識別します。 既定値 0 は、指定で宣言された既定のメッセージ マップ[送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)します。 宣言された代替のメッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)、渡す`msgMapID`します。  
  
 `hWndParent`  
 [in]親またはオーナー ウィンドウへのハンドル。  
  
 `rect`  
 [in]A [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)ウィンドウの位置を指定する構造体。 `RECT`ポインターまたは参照渡しで渡すことができます。  
  
 `szWindowName`  
 [in]ウィンドウの名前を指定します。 既定値は**NULL**します。  
  
 `dwStyle`  
 [in]ウィンドウのスタイル。 既定値は**WS_CHILD |WS_VISIBLE**します。 使用可能な値の一覧は、次を参照してください。 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwExStyle`  
 [in]拡張ウィンドウ スタイル。 既定値は 0、拡張スタイルは使いません。 使用可能な値の一覧は、次を参照してください。 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `MenuOrID`  
 [in]子ウィンドウの場合、ウィンドウの識別子。 最上位レベルのウィンドウのメニューはウィンドウのハンドルします。 既定値は**0 u**します。  
  
 `lpCreateParam`  
 [in]ウィンドウの作成のデータへのポインター。 詳細については、最終パラメーターの説明を参照して[CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、新しく作成されたウィンドウを識別するハンドルそれ以外の場合、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 既存のウィンドウ クラス名に保存[m_lpszClassName](#m_lpszclassname)します。 **作成**し、この新しいクラスに基づくウィンドウを作成します。 新しく作成されたウィンドウが自動的にアタッチ、`CContainedWindowT`オブジェクトです。  
  
> [!NOTE]
>  呼び出す必要はありません**作成**既にを呼び出した場合[SubclassWindow](#subclasswindow)します。  
  
> [!NOTE]
>  値として 0 が使用する場合、`MenuOrID`パラメーター 0 u として指定する必要があります (既定値) コンパイラのエラーを回避します。  
  
##  <a name="defwindowproc"></a>CContainedWindowT::DefWindowProc  
 によって呼び出される[WindowProc](#windowproc)メッセージ マップで処理されないメッセージを処理します。  
  
```
LRESULT DefWindowProc()
LRESULT DefWindowProc(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam);
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
  
##  <a name="getcurrentmessage"></a>CContainedWindowT::GetCurrentMessage  
 現在のメッセージを返します ( **m_pCurrentMsg**)。  
  
```
const _ATL_MSG* GetCurrentMessage();
```  
  
### <a name="return-value"></a>戻り値  
 現在のメッセージ内にパッケージ化、`MSG`構造体。  
  
##  <a name="m_dwmsgmapid"></a>CContainedWindowT::m_dwMsgMapID  
 コンテナー内のウィンドウの現在使用されているメッセージ マップの識別子を保持します。  
  
```
DWORD m_dwMsgMapID;
```  
  
### <a name="remarks"></a>コメント  
 このメッセージ マップは、親オブジェクトで宣言する必要があります。  
  
 宣言された既定のメッセージ マップ[送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)、常に&0; で識別されます。 宣言された、代替のメッセージ マップ[ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)、によって識別される`msgMapID`します。  
  
 `m_dwMsgMapID`コンス トラクターによって最初に初期化され、呼び出すことにより変更できます[SwitchMessageMap](#switchmessagemap)します。 例については、次を参照してください。、 [「](../../atl/reference/ccontainedwindowt-class.md)します。  
  
##  <a name="m_lpszclassname"></a>CContainedWindowT::m_lpszClassName  
 既存のウィンドウ クラスの名前を指定します。  
  
```
LPTSTR m_lpszClassName;
```  
  
### <a name="remarks"></a>コメント  
 ウィンドウを作成するときに[作成](#create)は既存のクラスに基づいていますが、使用する新しいウィンドウ クラスが登録[この段階](#windowproc)します。  
  
 `m_lpszClassName`コンス トラクターで初期化されます。 例については、次を参照してください。、 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要です。  
  
##  <a name="m_pfnsuperwindowproc"></a>CContainedWindowT::m_pfnSuperWindowProc  
 コンテナー内のウィンドウをサブクラス化すると場合、`m_pfnSuperWindowProc`ウィンドウ クラスの元のウィンドウ プロシージャをポイントします。  
  
```
WNDPROC m_pfnSuperWindowProc;
```  
  
### <a name="remarks"></a>コメント  
 コンテナー内のウィンドウがスーパークラスの場合を既存のクラスを変更するウィンドウ クラスに基づく、つまり`m_pfnSuperWindowProc`既存のウィンドウ クラスのウィンドウ プロシージャをポイントします。  
  
 [DefWindowProc](#defwindowproc)メソッドに保存されているウィンドウ プロシージャにメッセージの情報を送信する`m_pfnSuperWindowProc`です。  
  
##  <a name="m_pobject"></a>CContainedWindowT::m_pObject  
 オブジェクトを指す、`CContainedWindowT`オブジェクトです。  
  
```
CMessageMap* m_pObject;
```  
  
### <a name="remarks"></a>コメント  
 このコンテナーは、そのクラスから派生しなければなりません[CMessageMap](../../atl/reference/cmessagemap-class.md)、コンテナー内のウィンドウで使用されるメッセージ マップを宣言します。  
  
 `m_pObject`コンス トラクターで初期化されます。 例については、次を参照してください。、 [CContainedWindowT](../../atl/reference/ccontainedwindowt-class.md)の概要です。  
  
##  <a name="registerwndsuperclass"></a>CContainedWindowT::RegisterWndSuperclass  
 によって呼び出されます[作成](#create)コンテナー内のウィンドウのウィンドウ クラスを登録します。  
  
```
ATOM RegisterWndSuperClass();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、atom を一意に識別する登録されるウィンドウ クラスそれ以外の場合、0 を返します。  
  
### <a name="remarks"></a>コメント  
 このウィンドウ クラスは、既存のクラスに基づきますが、使用[この段階](#windowproc)します。 既存のウィンドウ クラスの名前とウィンドウ プロシージャ[m_lpszClassName](#m_lpszclassname)と[コンテナー内](#m_pfnsuperwindowproc)、それぞれします。  
  
##  <a name="subclasswindow"></a>CContainedWindowT::SubclassWindow  
 識別される、ウィンドウのサブクラス`hWnd`に接続し、`CContainedWindowT`オブジェクトです。  
  
```
BOOL SubclassWindow(HWND hWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWnd`  
 [in]サブクラス化されているウィンドウのハンドル。  
  
### <a name="return-value"></a>戻り値  
 **TRUE**ウィンドウが正常にサブクラス化された、それ以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 では、サブクラス化されたウィンドウ[この段階](#windowproc)します。 元のウィンドウ プロシージャ[コンテナー内](#m_pfnsuperwindowproc)します。  
  
> [!NOTE]
>  呼び出す必要はありません`SubclassWindow`既にを呼び出した場合[作成](#create)します。  
  
##  <a name="switchmessagemap"></a>CContainedWindowT::SwitchMessageMap  
 含まれているウィンドウのメッセージの処理に使用されるどのメッセージ マップを変更します。  
  
```
void SwitchMessageMap(DWORD dwMsgMapID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMsgMapID`  
 [in]メッセージ マップの識別子。 宣言された既定のメッセージ マップを使用する[送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)0 を渡します。 宣言された代替のメッセージ マップを使用して[ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)、渡す`msgMapID`します。  
  
### <a name="remarks"></a>コメント  
 メッセージ マップは、親オブジェクトで定義する必要があります。  
  
 最初に、コンス トラクターでメッセージ マップの識別子を指定します。  
  
##  <a name="unsubclasswindow"></a>CContainedWindowT::UnsubclassWindow  
 サブクラス化されたウィンドウのデタッチ、`CContainedWindowT`オブジェクトし、復元に保存されている元のウィンドウ プロシージャ[コンテナー内](#m_pfnsuperwindowproc)します。  
  
```
HWND UnsubclassWindow(BOOL bForce = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bForce`  
 [in]設定**TRUE**を復元する元のウィンドウ プロシージャを強制的に場合でもこのウィンドウ プロシージャ`CContainedWindowT`オブジェクトは現在アクティブではありません。 場合`bForce`に設定されている**FALSE**とウィンドウのウィンドウ プロシージャ`CContainedWindowT`オブジェクトが現在アクティブなは、元のウィンドウ プロシージャは復元されません。  
  
### <a name="return-value"></a>戻り値  
 以前にサブクラス化されたウィンドウのハンドル。 場合`bForce`に設定されている**FALSE**とウィンドウのウィンドウ プロシージャ`CContainedWindowT`オブジェクトが現在アクティブでない、返す**NULL**します。  
  
### <a name="remarks"></a>コメント  
 ウィンドウが破棄される前に、元のウィンドウ プロシージャを復元する場合は、このメソッドを使用します。 それ以外の場合、 [WindowProc](#windowproc)ウィンドウが破棄されるときに、これは自動的にします。  
  
##  <a name="windowproc"></a>この段階  
 この静的メソッドでは、ウィンドウ プロシージャを実装します。  
  
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
 `WindowProc`識別されるメッセージ マップにメッセージを送信[m_dwMsgMapID](#m_dwmsgmapid)します。 必要に応じて、`WindowProc`呼び出し[DefWindowProc](#defwindowproc)追加のメッセージ処理のためです。  
  
## <a name="see-also"></a>関連項目  
 [CWindow クラス](../../atl/reference/cwindow-class.md)   
 [CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)   
 [CMessageMap クラス](../../atl/reference/cmessagemap-class.md)   
 [送るに](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [クラスの概要](../../atl/atl-class-overview.md)

