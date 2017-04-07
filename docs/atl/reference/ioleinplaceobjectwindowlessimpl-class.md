---
title: "IOleInPlaceObjectWindowlessImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
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
ms.openlocfilehash: 06ce03a896c9948bff14b4f91ae48000d07c3edd
ms.lasthandoff: 02/24/2017

---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl クラス
このクラスは実装**IUnknown**ウィンドウなしのコントロールを使用しているウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加を有効にするためのメソッドを提供します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IOleInPlaceObjectWindowlessImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|状況依存のヘルプを有効にします。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|装置、`IDropTarget`サポートは、ドラッグ アンド ドロップ インプレース アクティブ、窓のないオブジェクトのインターフェイスです。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|ウィンドウ ハンドルを取得します。|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|アクティブな場所でコントロールを無効になります。|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|インプレースで有効になっているウィンドウなしのコントロールをコンテナーからのメッセージをディスパッチします。|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|以前に非アクティブ化されたコントロールを再アクティブ化します。 ATL の実装を返します**E_NOTIMPL**します。|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|インプレースでコントロールのどの部分が表示されていることを示します。|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|非アクティブにし、インプレース アクティブ化をサポートするユーザー インターフェイスを削除します。|  
  
## <a name="remarks"></a>コメント  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646)インターフェイスは、再アクティブ化を管理し、インプレースでの非アクティブ化を制御し、コントロールの量を表示するかを決定します。 [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304)ウィンドウなしのコントロールを使用しているウィンドウ メッセージを受信して、ドラッグ アンド ドロップ操作に参加できるようにするインターフェイスです。 クラス`IOleInPlaceObjectWindowlessImpl`の既定の実装を提供`IOleInPlaceObject`と`IOleInPlaceObjectWindowless`を実装および**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 返します。 **E_NOTIMPL**します。  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 返します。 **E_NOTIMPL**します。  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 コンテナーは、コントロールのウィンドウ ハンドルを取得するには、この関数を呼び出します。  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>コメント  
 コンテナーによっては、現在のウィンドウがある場合でも、ウィンドウなしされているコントロールでは動作しません。 ATL の実装で場合は、コントロール クラスのデータ メンバー`m_bWasOnceWindowless`は**TRUE**、関数を返します**E_FAIL**します。 それ以外の場合*phwnd*は**NULL**、`GetWindow`設定\* *phwnd*コントロール クラスのデータ メンバーに`m_hWnd`返します`S_OK`します。  
  
 参照してください[IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 インプレースでアクティブなコントロールを非アクティブ化するコンテナーによって呼び出されます。  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、コントロールの状態に応じて、完全または部分的な非アクティブ化を実行します。 必要に応じて、コントロールのユーザー インターフェイスが非アクティブ化し、存在する場合、コントロールのウィンドウは破棄されます。 コンテナーには、インプレース コントロールがアクティブでなくなったことが通知されます。 **埋め込み**領域の枠線し、そのメニューをネゴシエートするコンテナーによって使用されるインターフェイスを公開しました。  
  
 参照してください[IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 インプレースで有効になっているウィンドウなしのコントロールをコンテナーからのメッセージをディスパッチします。  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 返します。 **E_NOTIMPL**します。  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>コメント  
 参照してください[IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 コントロールのサイズや位置が変更されたことを通知するためのコンテナーによって呼び出されます。  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>コメント  
 コントロールの更新`m_rcPos`データ メンバーおよびコントロールの表示。 クリップ領域と交差しているコントロールの一部のみが表示されます。 コントロールの表示が以前にクリップされるクリッピングが削除された場合は、この関数がコントロールの完全なビューを再描画すると呼ばれることができます。  
  
 参照してください[IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 非アクティブにし、インプレース アクティブ化をサポートするコントロールのユーザー インターフェイスを削除します。  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>コメント  
 コントロール クラスのデータ メンバーを設定`m_bUIActive`に**FALSE**します。 ATL の実装この関数が常に返される`S_OK`です。  
  
 参照してください[IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

