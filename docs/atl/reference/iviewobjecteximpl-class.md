---
title: "クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl
- ATLCTL/ATL::IViewObjectExImpl::Draw
- ATLCTL/ATL::IViewObjectExImpl::Freeze
- ATLCTL/ATL::IViewObjectExImpl::GetAdvise
- ATLCTL/ATL::IViewObjectExImpl::GetColorSet
- ATLCTL/ATL::IViewObjectExImpl::GetExtent
- ATLCTL/ATL::IViewObjectExImpl::GetNaturalExtent
- ATLCTL/ATL::IViewObjectExImpl::GetRect
- ATLCTL/ATL::IViewObjectExImpl::GetViewStatus
- ATLCTL/ATL::IViewObjectExImpl::QueryHitPoint
- ATLCTL/ATL::IViewObjectExImpl::QueryHitRect
- ATLCTL/ATL::IViewObjectExImpl::SetAdvise
- ATLCTL/ATL::IViewObjectExImpl::Unfreeze
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], drawing
- IViewObjectEx ATL implementation
- advise sinks
- IViewObjectExImpl class
ms.assetid: ad6de760-1ee5-4883-b033-ae57beffc369
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 2b585a056324507cc631e64e6dbe9d0ed610361d
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="iviewobjecteximpl-class"></a>クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および[IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE IViewObjectExImpl 
   : public IViewObjectEx
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IViewObjectExImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IViewObjectExImpl::Draw](#draw)|デバイス コンテキスト上にコントロールの内部表現を描画します。|  
|[IViewObjectExImpl::Freeze](#freeze)|コントロールの描画された画像をフリーズするまで変更できないように、`Unfreeze`です。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IViewObjectExImpl::GetAdvise](#getadvise)|1 つを使用する必要がある場合は、コントロールで、既存のアドバイズ シンクの接続を取得します。|  
|[IViewObjectExImpl::GetColorSet](#getcolorset)|コントロールによって描画に使用される論理パレットを返します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IViewObjectExImpl::GetExtent](#getextent)|コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。|  
|[IViewObjectExImpl::GetNaturalExtent](#getnaturalextent)|ユーザーがサイズを変更とを使用するオブジェクトのコンテナーからサイズ変更のヒントを提供します。|  
|[IViewObjectExImpl::GetRect](#getrect)|要求された描画の外観を示す四角形を返します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IViewObjectExImpl::GetViewStatus](#getviewstatus)|オブジェクトとどのような描画の側面がサポートされているの不透明度に関する情報を返します。|  
|[IViewObjectExImpl::QueryHitPoint](#queryhitpoint)|指定したポイントで指定された四角形はし、返すことを確認、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`です。|  
|[IViewObjectExImpl::QueryHitRect](#queryhitrect)|セルの内容かどうか、コントロールの表示する四角形の指定した場所の四角形と重なっている返します、**中**値`pHitResult`です。|  
|[IViewObjectExImpl::SetAdvise](#setadvise)|シンクは、コントロールのビューでの変更について通知できるように、コントロールとアドバイズ シンク間の接続を設定します。|  
|[IViewObjectExImpl::Unfreeze](#unfreeze)|コントロールの描画の表示を解除します。 ATL の実装を返します**E_NOTIMPL**します。|  
  
## <a name="remarks"></a>コメント  
 [IViewObject](http://msdn.microsoft.com/library/windows/desktop/ms680763)、 [IViewObject2](http://msdn.microsoft.com/library/windows/desktop/ms691318)、および[IViewObjectEx](http://msdn.microsoft.com/library/windows/desktop/ms682375)インターフェイス自体を直接表示する、作成してコントロールの表示の変更のコンテナーに通知するアドバイズ シンクを管理するためのコントロールを有効にします。 **IViewObjectEx**インターフェイスではちらつきなしの描画、四角形ではないと透明なコントロール、およびヒット テスト (たとえば、どのくらい近づいてマウスをクリックする必要がありますコントロールと見なされるに) などのコントロール拡張機能をサポートします。 クラス`IViewObjectExImpl`これらのインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IViewObjectEx`  
  
 `IViewObjectExImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="draw"></a>IViewObjectExImpl::Draw  
 デバイス コンテキスト上にコントロールの内部表現を描画します。  
  
```
STDMETHOD(Draw)(
    DWORD dwDrawAspect,
    LONG lindex,
    void* pvAspect,
    DVTARGETDEVICE* ptd,
    HDC hicTargetDev,
    LPCRECTL prcBounds,
    LPCRECTL prcWBounds,
    BOOL(_stdcall* /* pfnContinue*/) (DWORD_PTR dwContinue),
    DWORD_PTR /* dwContinue */);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出す**CComControl::OnDrawAdvanced**をさらに、コントロール クラスの`OnDraw`メソッドです。 `OnDraw`メソッドは ATL コントロール ウィザードを使用して、コントロールを作成するときに、自動的にコントロール クラスに追加します。 ウィザードの既定`OnDraw`ラベル"ATL 3.0"を持つ四角形を描画します。  
  
 参照してください[IViewObject::Draw](http://msdn.microsoft.com/library/windows/desktop/ms688655)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="freeze"></a>IViewObjectExImpl::Freeze  
 コントロールの描画された画像をフリーズするまで変更できないように、`Unfreeze`です。 ATL の実装を返します**E_NOTIMPL**します。  
  
```
STDMETHOD(Freeze)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DWORD* /* pdwFreeze */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject::Freeze](http://msdn.microsoft.com/library/windows/desktop/ms688728)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getadvise"></a>IViewObjectExImpl::GetAdvise  
 1 つを使用する必要がある場合は、コントロールで、既存のアドバイズ シンクの接続を取得します。  
  
```
STDMETHOD(GetAdvise)(
    DWORD* /* pAspects */,
    DWORD* /* pAdvf */,
    IAdviseSink** /* ppAdvSink */);
```  
  
### <a name="remarks"></a>コメント  
 アドバイズ シンクがコントロール クラスのデータ メンバーに格納されている[アドバイズ](../../atl/reference/ccomcontrolbase-class.md#m_spadvisesink)します。  
  
 参照してください[IViewObject::GetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692772)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getcolorset"></a>IViewObjectExImpl::GetColorSet  
 コントロールによって描画に使用される論理パレットを返します。 ATL の実装を返します**E_NOTIMPL**します。  
  
```
STDMETHOD(GetColorSet)(
    DWORD /* dwAspect */,
    LONG /* lindex */,
    void* /* pvAspect */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    LOGPALETTE** /* ppColorSet */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject::GetColorSet](http://msdn.microsoft.com/library/windows/desktop/ms686553)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getextent"></a>IViewObjectExImpl::GetExtent  
 コントロール クラスのデータ メンバーから、コントロールの表示サイズを HIMETRIC 単位 (0.01 ミリメートル単位) を取得[この](../../atl/reference/ccomcontrolbase-class.md#m_sizeextent)します。  
  
```
STDMETHOD(GetExtent)(
    DWORD /* dwDrawAspect */,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    LPSIZEL* lpsizel);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject2::GetExtent](http://msdn.microsoft.com/library/windows/desktop/ms684032)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getnaturalextent"></a>IViewObjectExImpl::GetNaturalExtent  
 ユーザーがサイズを変更とを使用するオブジェクトのコンテナーからサイズ変更のヒントを提供します。  
  
```
STDMETHOD(GetNaturalExtent)(
    DWORD dwAspect,
    LONG /* lindex */,
    DVTARGETDEVICE* /* ptd */,
    HDC /* hicTargetDevice */,
    DVEXTENTINFO* pExtentInfo,
    LPSIZEL psizel);
```  
  
### <a name="remarks"></a>コメント  
 場合`dwAspect`は`DVASPECT_CONTENT`と*dwExtentMode-> pExtentInfo*は**DVEXTENT_CONTENT**、設定 *`psizel`コントロール クラスのデータ メンバーに[CComControlBase::m_sizeNatural](../../atl/reference/ccomcontrolbase-class.md#m_sizenatural)します。 それ以外の場合、エラーが返されます`HRESULT`します。  
  
 参照してください[IViewObjectEx::GetNaturalExtent](http://msdn.microsoft.com/library/windows/desktop/ms683718)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getrect"></a>IViewObjectExImpl::GetRect  
 要求された描画の外観を示す四角形を返します。 ATL の実装を返します**E_NOTIMPL**します。  
  
```
STDMETHOD(GetRect)(DWORD /* dwAspect */, LPRECTL /* pRect */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObjectEx::GetRect](http://msdn.microsoft.com/library/windows/desktop/ms695246)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getviewstatus"></a>IViewObjectExImpl::GetViewStatus  
 オブジェクトとどのような描画の側面がサポートされているの不透明度に関する情報を返します。  
  
```
STDMETHOD(GetViewStatus)(DWORD* pdwStatus);
```  
  
### <a name="remarks"></a>コメント  
 既定では、ATL の設定`pdwStatus`コントロールがサポートすることを示すために**VIEWSTATUS_OPAQUE** (使用できる値は、[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)列挙型)。  
  
 参照してください[IViewObjectEx::GetViewStatus](http://msdn.microsoft.com/library/windows/desktop/ms693371)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="queryhitpoint"></a>IViewObjectExImpl::QueryHitPoint  
 指定したポイントで指定された四角形はし、返すことを確認、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`です。  
  
```
STDMETHOD(QueryHitPoint)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    POINT ptlLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>コメント  
 値には、いずれかを指定できます**この**または**値**です。  
  
 場合`dwAspect`equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318)、メソッドが戻る`S_OK`します。 それ以外の場合、メソッドが返す**E_FAIL**します。  
  
 参照してください[IViewObjectEx::QueryHitPoint](http://msdn.microsoft.com/library/windows/desktop/ms691209)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="queryhitrect"></a>IViewObjectExImpl::QueryHitRect  
 セルの内容かどうか、コントロールの表示する四角形の指定した場所の四角形と重なっている返します、[中](http://msdn.microsoft.com/library/windows/desktop/ms682187)値`pHitResult`です。  
  
```
STDMETHOD(QueryHitRect)(
    DWORD dwAspect,
    LPCRECT pRectBounds,
    LPRECT prcLoc,
    LONG /* lCloseHit */,
    DWORD* /* pHitResult */);
```  
  
### <a name="remarks"></a>コメント  
 値には、いずれかを指定できます**この**または**値**です。  
  
 場合`dwAspect`equals [DVASPECT_CONTENT](http://msdn.microsoft.com/library/windows/desktop/ms690318)、メソッドが戻る`S_OK`します。 それ以外の場合、メソッドが返す**E_FAIL**します。  
  
 参照してください[IViewObjectEx::QueryHitRect](http://msdn.microsoft.com/library/windows/desktop/ms693797)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setadvise"></a>IViewObjectExImpl::SetAdvise  
 シンクは、コントロールのビューでの変更について通知できるように、コントロールとアドバイズ シンク間の接続を設定します。  
  
```
STDMETHOD(SetAdvise)(
    DWORD /* aspects */,
    DWORD /* advf */,
    IAdviseSink* pAdvSink);
```  
  
### <a name="remarks"></a>コメント  

 ポインター、 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)アドバイズ シンク上のインターフェイスがコントロール クラスのデータ メンバーに格納されている[アドバイズ](ccomcontrolbase-class.md#m_spadvisesink)します。  

  
 参照してください[IViewObject::SetAdvise](http://msdn.microsoft.com/library/windows/desktop/ms683950)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="unfreeze"></a>IViewObjectExImpl::Unfreeze  
 コントロールの描画の表示を解除します。 ATL の実装を返します**E_NOTIMPL**します。  
  
```
STDMETHOD(Unfreeze)(DWORD /* dwFreeze */);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IViewObject::Unfreeze](http://msdn.microsoft.com/library/windows/desktop/ms686641)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="closehandle"></a>IWorkerThreadClient::CloseHandle  
 このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。  
  
```
HRESULT CloseHandle(HANDLE hHandle);
```  
  
### <a name="parameters"></a>パラメーター  
 *hHandle*  
 終了するハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、または失敗に関するエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドに渡されるハンドルがへの呼び出しで既にこのオブジェクトとの関連付けられている[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。  
  
### <a name="example"></a>例  
 次のコードの単純な実装を示しています。`IWorkerThreadClient::CloseHandle`します。  
  
 [!code-cpp[NVC_ATL_Utilities #&135;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_1.cpp)]  
  
##  <a name="execute"></a>IWorkerThreadClient::Execute  
 このオブジェクトに関連付けられたハンドルがシグナル状態にコードを実行するには、このメソッドを実装します。  
  
```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwParam`  
 ユーザーのパラメーターです。  
  
 `hObject`  
 このハンドルは、シグナル状態になっています。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、または失敗に関するエラーの hresult 値に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 ハンドルおよび DWORD/へのポインターのこのメソッドに渡される以前に関連付けられていたこのオブジェクトへの呼び出しによって[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。  
  
### <a name="example"></a>例  
 次のコードの単純な実装を示しています。`IWorkerThreadClient::Execute`します。  
  
 [!code-cpp[NVC_ATL_Utilities #&136;](../../atl/codesnippet/cpp/iviewobjecteximpl-class_2.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX コントロールのインターフェイス](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [チュートリアル](../../atl/active-template-library-atl-tutorial.md)   
 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

