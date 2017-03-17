---
title: "CComControl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComControl
- ATLCTL/ATL::CComControl
- ATLCTL/ATL::CComControl::CComControl
- ATLCTL/ATL::CComControl::ControlQueryInterface
- ATLCTL/ATL::CComControl::CreateControlWindow
- ATLCTL/ATL::CComControl::FireOnChanged
- ATLCTL/ATL::CComControl::FireOnRequestEdit
- ATLCTL/ATL::CComControl::MessageBox
dev_langs:
- C++
helpviewer_keywords:
- control flags
- CComControlBase class, CComControl class
- stock properties, ATL
- CComControl class
- controls [ATL], control helper functions
- ambient properties
- controls [ATL], properties
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
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
ms.openlocfilehash: 387d38f89e8d783c7ae85c2ab960d5e59c1c4009
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontrol-class"></a>CComControl クラス
このクラスは、作成および ATL のコントロールを管理するためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class WinBase = CWindowImpl<T>>  
class ATL_NO_VTABLE CComControl : public CComControlBase,
    public WinBase;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コントロールを実装するクラスです。  
  
 *WinBase*  
 ウィンドウ関数を実装する基本クラス。 既定値は[CWindowImpl](../../atl/reference/cwindowimpl-class.md)します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComControl::CComControl](#ccomcontrol)|コンストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](#controlqueryinterface)|要求されたインターフェイスへのポインターを取得します。|  
|[CComControl::CreateControlWindow](#createcontrolwindow)|コントロールのウィンドウを作成します。|  
|[CComControl::FireOnChanged](#fireonchanged)|コントロールのプロパティが変更されたコンテナーのシンクに通知します。|  
|[CComControl::FireOnRequestEdit](#fireonrequestedit)|コントロールのプロパティが変更されようとしてがあると、オブジェクトが要求している、シンクの続行方法は、コンテナーのシンクを通知します。|  
|[CComControl::MessageBox](#messagebox)|作成、表示、およびメッセージ ボックスを操作するには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 `CComControl`コントロールの便利なヘルパー関数と ATL のコントロールの重要なデータ メンバーのセットです。 標準コントロールまたは ATL コントロール ウィザードを使用して、DHTML コントロールを作成する場合、ウィザードは自動的の派生クラスから`CComControl`します。 `CComControl`メソッドのほとんどの派生元[CComControlBase](../../atl/reference/ccomcontrolbase-class.md)します。  
  
 コントロールの作成方法の詳細については、次を参照してください。、 [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)します。 ATL プロジェクト ウィザードの詳細については、記事を参照してください。 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)します。  
  
 例については`CComControl`メソッドとデータ メンバーを参照してください、[円](../../visual-cpp-samples.md)サンプルです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="ccomcontrol"></a>CComControl::CComControl  
 コンストラクターです。  
  
```
CComControl();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し、 [CComControlBase](ccomcontrolbase-class.md#ccomcontrolbase)コンス トラクターを渡して、`m_hWnd`を通じてデータ メンバーが継承[CWindowImpl](../../atl/reference/cwindowimpl-class.md)します。  
  
##  <a name="controlqueryinterface"></a>CComControl::ControlQueryInterface  
 要求されたインターフェイスへのポインターを取得します。  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid, void** ppv);
```  
  
### <a name="parameters"></a>パラメーター  
 `iid`  
 [in]要求されているインターフェイスの GUID です。  
  
 `ppv`  
 [out]によって識別されるインターフェイス ポインターへのポインター `iid`、または**NULL**インターフェイスが見つからない場合。  
  
### <a name="remarks"></a>コメント  
 COM マップ テーブル内のインターフェイスを処理のみです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#15;](../../atl/codesnippet/cpp/ccomcontrol-class_1.cpp)]  
  
##  <a name="createcontrolwindow"></a>CComControl::CreateControlWindow  
 既定では、呼び出すことによって、コントロールのウィンドウを作成`CWindowImpl::Create`します。  
  
```
virtual HWND CreateControlWindow(HWND hWndParent, RECT& rcPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `hWndParent`  
 [in]親またはオーナー ウィンドウへのハンドルします。 有効なウィンドウ ハンドルを指定する必要があります。 コントロールのウィンドウは、親ウィンドウの領域に限定されます。  
  
 `rcPos`  
 [in]初期サイズと作成するウィンドウの位置。  
  
### <a name="remarks"></a>コメント  
 このメソッドをオーバーライドして、何かの操作を実行する場合以外の&1; つのウィンドウを作成、たとえば、2 つのウィンドウを作成するうちの&1; つになります、コントロールのツールバー。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&#16;](../../atl/codesnippet/cpp/ccomcontrol-class_2.cpp)]  
  
##  <a name="fireonchanged"></a>CComControl::FireOnChanged  
 コントロールのプロパティが変更されたコンテナーのシンクに通知します。  
  
```
HRESULT FireOnChanged(DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dispID*  
 [in]変更されたプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 コントロール クラスから派生する場合[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)、このメソッドを呼び出す[CFirePropNotifyEvent::FireOnChanged](cfirepropnotifyevent-class.md#fireonchanged)すべてに通知する、接続されている`IPropertyNotifySink`指定したコントロール プロパティが変更されたインターフェイスです。 コントロール クラスがから派生していない場合`IPropertyNotifySink`、このメソッドが戻る`S_OK`します。 
  
 このメソッドは、コントロールは、接続ポイントをサポートしない場合でもを呼び出しても安全です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&17;](../../atl/codesnippet/cpp/ccomcontrol-class_3.cpp)]  
  
##  <a name="fireonrequestedit"></a>CComControl::FireOnRequestEdit  
 コントロールのプロパティが変更されようとしてがあると、オブジェクトが要求している、シンクの続行方法は、コンテナーのシンクを通知します。  
  
```
HRESULT FireOnRequestEdit(DISPID dispID);
```  
  
### <a name="parameters"></a>パラメーター  
 *dispID*  
 [in]変更するプロパティの識別子。  
  
### <a name="return-value"></a>戻り値  
 標準の HRESULT 値の&1; つ。  
  
### <a name="remarks"></a>コメント  
 コントロール クラスから派生する場合[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)、このメソッドを呼び出す[CFirePropNotifyEvent::FireOnRequestEdit](cfirepropnotifyevent-class.md#fireonrequestedit)すべてに通知する、接続されている`IPropertyNotifySink`インターフェイスを指定したコントロール プロパティが変更されようとしています。 コントロール クラスがから派生していない場合`IPropertyNotifySink`、このメソッドが戻る`S_OK`します。  

  
 このメソッドは、コントロールは、接続ポイントをサポートしない場合でもを呼び出しても安全です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_COM&18;](../../atl/codesnippet/cpp/ccomcontrol-class_4.cpp)]  
  
##  <a name="messagebox"></a>CComControl::MessageBox  
 作成、表示、およびメッセージ ボックスを操作するには、このメソッドを呼び出します。  
  
```
int MessageBox(
    LPCTSTR lpszText,
    LPCTSTR lpszCaption = _T(""),
    UINT nType = MB_OK);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszText`  
 メッセージ ボックスに表示されるテキスト。  
  
 `lpszCaption`  
 ダイアログ ボックスのタイトル。 場合は NULL (既定)、「エラー」が使用されるタイトルです。  
  
 `nType`  
 内容と、ダイアログ ボックスの動作を指定します。 参照してください、[メッセージ ボックス](http://msdn.microsoft.com/library/windows/desktop/ms645505)内のエントリ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]利用可能なさまざまなメッセージ ボックスの一覧については、ドキュメントです。 既定では、単純な**OK**  ボタンをクリックします。  
  
### <a name="return-value"></a>戻り値  
 下に表示 メニュー項目の値のいずれかを示す整数値を返す[メッセージ ボックス](http://msdn.microsoft.com/library/windows/desktop/ms645505)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]ドキュメントです。  
  
### <a name="remarks"></a>コメント  
 `MessageBox`開発時と、エラーまたは警告メッセージをユーザーに表示する簡単な方法としては役立ちます。  
  
## <a name="see-also"></a>関連項目  
 [CWindowImpl クラス](../../atl/reference/cwindowimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComControlBase クラス](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl クラス](../../atl/reference/ccomcompositecontrol-class.md)

