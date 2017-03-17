---
title: "CComCompositeControl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCompositeControl
- ATLCTL/ATL::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::CComCompositeControl
- ATLCTL/ATL::CComCompositeControl::AdviseSinkMap
- ATLCTL/ATL::CComCompositeControl::CalcExtent
- ATLCTL/ATL::CComCompositeControl::Create
- ATLCTL/ATL::CComCompositeControl::CreateControlWindow
- ATLCTL/ATL::CComCompositeControl::SetBackgroundColorFromAmbient
- ATLCTL/ATL::CComCompositeControl::m_hbrBackground
- ATLCTL/ATL::CComCompositeControl::m_hWndFocus
dev_langs:
- C++
helpviewer_keywords:
- CComCompositeControl class
- composite controls, CComCompositeControl class
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
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
ms.openlocfilehash: ab99b8682e8b529cc124fbda1e6facaac48d0927
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcompositecontrol-class"></a>CComCompositeControl クラス
このクラスは、複合コントロールを実装するために必要なメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class CComCompositeControl : public CComControl<T,CAxDialogImpl<T>>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)または[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)複合コントロールをサポートするために必要なその他のインターフェイスからも、です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](#ccomcompositecontrol)|コンストラクターです。|  
|[CComCompositeControl:: ~ CComCompositeControl](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](#advisesinkmap)|複合コントロールでホストされているすべてのコントロールをアドバイズするか、このメソッドを呼び出します。|  
|[CComCompositeControl::CalcExtent](#calcextent)|サイズを計算するには、このメソッドを呼び出す**HIMETRIC**複合コントロールをホストするために使用するダイアログ リソースの単位です。|  
|[CComCompositeControl::Create](#create)|このメソッドは複合コントロールのコントロール ウィンドウを作成します。|  
|[CComCompositeControl::CreateControlWindow](#createcontrolwindow)|コントロールのウィンドウを作成し、ホストされるコントロールをアドバイズするには、このメソッドを呼び出します。|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](#setbackgroundcolorfromambient)|コンテナーの背景色を使用して複合コントロールの背景色を設定するには、このメソッドを呼び出します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CComCompositeControl::m_hbrBackground](#m_hbrbackground)|背景のブラシ。|  
|[CComCompositeControl::m_hWndFocus](#m_hwndfocus)|現在フォーカスがあるウィンドウのハンドル。|  
  
## <a name="remarks"></a>コメント  
 クラスから派生したクラス`CComCompositeControl`ActiveX 複合コントロールの機能を継承します。 ActiveX コントロールから派生した`CComCompositeControl`標準のダイアログ ボックスによってホストされます。 この種のコントロールは、その他のコントロール (ネイティブの Windows のコントロールおよび ActiveX コントロール) をホストすることがためには複合コントロールと呼ばれます。  
  
 `CComCompositeControl`子クラスに、列挙データ メンバーを探し、複合コントロールの作成に使用するダイアログ リソースを識別します。 この子クラスのメンバー IDD はコントロールのウィンドウとして使用されるダイアログ ボックス リソースのリソース ID に設定されます。 クラスから派生するデータ メンバーの例を次に示します`CComCompositeControl`コントロールのウィンドウに使用するダイアログ リソースを識別するために含める必要があります。  
  
 [!code-cpp[NVC_ATL_COM&#13;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_1.h)]  
  
> [!NOTE]
>  複合コントロールはウィンドウを持つコントロールでは常にウィンドウなしのコントロールを含めることができます。  
  
 によって実装される、コントロール、`CComCompositeControl`の派生クラスが既定の組み込みの動作をタブ移動します。 アプリケーション内でのタブ操作によってコントロールがフォーカスを受け取ると、連続して TAB キーを押してが発生するすべての複合コントロールのコンテナー内のコントロール、およびコンテナーのタブ オーダーの次の項目には、複合コントロールを循環したにフォーカスします。 ホストされるコントロールのタブ オーダーは、ダイアログ リソースによって決定され、順序を決定するタブ移動で発生します。  
  
> [!NOTE]
>  アクセラレータで正しく動作するために、 `CComCompositeControl`、アクセラレータ テーブルを読み込み、コントロールが作成されると、ハンドルおよびにアクセラレータの数を渡す必要がある[IOleControlImpl::GetControlInfo](../../atl/reference/iolecontrolimpl-class.md#getcontrolinfo)、および最後に、コントロールがリリースされたときにテーブルを破棄します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#14;](../../atl/codesnippet/cpp/ccomcompositecontrol-class_2.h)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="advisesinkmap"></a>CComCompositeControl::AdviseSinkMap  
 複合コントロールでホストされているすべてのコントロールをアドバイズするか、このメソッドを呼び出します。  
  
```
HRESULT AdviseSinkMap(bool bAdvise);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAdvise`  
 すべてのコントロールがすることに注意している場合は trueそれ以外の場合は false。  
  
### <a name="return-value"></a>戻り値  
 `S_OK`  
 すべてのコントロール、イベント シンク マップに接続されたか、イベント ソースから正常に切断します。  
  
 **E_FAIL**  
 すべてを制御、イベント シンク マップは接続されているか、イベント ソースから正常に切断された可能性があります。  
  
 `E_POINTER`  
 このエラーは、コントロールのイベント シンク マップ内のエントリに問題があるかで使用されるテンプレート引数に問題に通常を示して、`IDispEventImpl`または`IDispEventSimpleImpl`基本クラスです。  
  
 **CONNECT_E_ADVISELIMIT**  
 コネクション ポイントは、接続の上限に既に達してし、その他を受け付けることができません。  
  
 **CONNECT_E_CANNOTCONNECT**  
 シンクは、この接続ポイントに必要なインターフェイスをサポートしていません。  
  
 **CONNECT_E_NOCONNECTION**  
 Cookie の値には、有効な接続は表しません。 このエラーは、コントロールのイベント シンク マップ内のエントリに問題があるかで使用されるテンプレート引数に問題に通常を示して、`IDispEventImpl`または`IDispEventSimpleImpl`基本クラスです。  
  
### <a name="remarks"></a>コメント  
 このメソッドの基本実装は、イベント シンク マップのエントリを検索します。 その後、アドバイスまたはアドバイズ シンクのエントリをイベント シンク マップのによって記述された COM オブジェクトに接続ポイント。 また、このメソッドは、派生クラスが&1; つのインスタンスから継承されるという事実に依存`IDispEventImpl`のすべての制御を伝えたかアドバイズ シンク マップします。  
  
##  <a name="calcextent"></a>CComCompositeControl::CalcExtent  
 サイズを計算するには、このメソッドを呼び出す**HIMETRIC**複合コントロールをホストするために使用するダイアログ リソースの単位です。  
  
```
BOOL CalcExtent(SIZE& size);
```  
  
### <a name="parameters"></a>パラメーター  
 `size`  
 参照、**サイズ**このメソッドが格納される構造体。  
  
### <a name="return-value"></a>戻り値  
 コントロールがダイアログ ボックスでホストされている場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 返されたサイズ、`size`パラメーター。  
  
##  <a name="create"></a>CComCompositeControl::Create  
 このメソッドは複合コントロールのコントロール ウィンドウを作成します。  
  
```
HWND Create(
    HWND hWndParent,
    RECT& /* rcPos */,
    LPARAM dwInitParam = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 コントロールの親ウィンドウへのハンドル。  
  
 `rcPos`  
 予約済み。  
  
 `dwInitParam`  
 コントロールの作成時に、コントロールに渡されるデータ。 として渡されたデータ`dwInitParam`として表示される、 **LPARAM**のパラメーター、 [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428)を取得、作成時に、複合コントロールに送信されるメッセージ。  
  
### <a name="return-value"></a>戻り値  
 新しく作成された複合コントロールのダイアログ ボックスへのハンドル。  
  
### <a name="remarks"></a>コメント  
 通常、このメソッドは、コントロールのインプレース アクティブ化時に呼び出されます。  
  
##  <a name="ccomcompositecontrol"></a>CComCompositeControl::CComCompositeControl  
 コンストラクターです。  
  
```
CComCompositeControl();
```  
  
### <a name="remarks"></a>コメント  
 初期化、 [CComCompositeControl::m_hbrBackground](#m_hbrbackground)と[CComCompositeControl::m_hWndFocus](#m_hwndfocus)データ メンバーを NULL にします。  
  
##  <a name="dtor"></a>CComCompositeControl:: ~ CComCompositeControl  
 デストラクターです。  
  
```
~CComCompositeControl();
```  
  
### <a name="remarks"></a>コメント  
 存在する場合は、バック グラウンド オブジェクトを削除します。  
  
##  <a name="createcontrolwindow"></a>CComCompositeControl::CreateControlWindow  
 コントロールのウィンドウを作成し、ホストされるコントロールをアドバイズするには、このメソッドを呼び出します。  
  
```
virtual HWND CreateControlWindow(
    HWND hWndParent,
    RECT& rcPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 コントロールの親ウィンドウへのハンドル。  
  
 `rcPos`  
 クライアントでの複合コントロールの位置四角形を基準となる調整`hWndParent`します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成された複合コントロール ダイアログ ボックスのハンドルを返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す[CComCompositeControl::Create](#create)と[CComCompositeControl::AdviseSinkMap](#advisesinkmap)します。  
  
##  <a name="m_hbrbackground"></a>CComCompositeControl::m_hbrBackground  
 背景のブラシ。  
  
```
HBRUSH m_hbrBackground;
```  
  
##  <a name="m_hwndfocus"></a>CComCompositeControl::m_hWndFocus  
 現在フォーカスがあるウィンドウのハンドル。  
  
```
HWND m_hWndFocus;
```  
  
##  <a name="setbackgroundcolorfromambient"></a>CComCompositeControl::SetBackgroundColorFromAmbient  
 コンテナーの背景色を使用して複合コントロールの背景色を設定するには、このメソッドを呼び出します。  
  
```
HRESULT SetBackgroundColorFromAmbient();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗に関するエラーの hresult 値を返します。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [複合コントロールの基本](../../atl/atl-composite-control-fundamentals.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

