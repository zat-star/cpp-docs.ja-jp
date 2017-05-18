---
title: "IQuickActivateImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4f6b75da64efa12e43fa160c57da4291acae03ca
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl クラス
このクラスは、1 回の呼び出しにコンテナーのコントロールの初期化を結合します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IQuickActivateImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|実行中のコントロールの現在の表示サイズを取得します。|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|読み込む対象のコントロールの初期化を迅速に実行します。|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|コンテナーが割り当てられて表示領域の量のコントロールに通知します。|  
  
## <a name="remarks"></a>コメント  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146)インターフェイスでは、1 回の呼び出しでは、初期化を組み合わせることによってコントロールの読み込み時に遅延を避けるためのコンテナーです。 `QuickActivate`メソッドを使用して、コンテナーへのポインターを渡すため、 [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630)構造、コントロールのすべてのインターフェイス ポインターを保持する必要があります。 戻り時に、制御が移りますバックアップへのポインター、[戻り値](http://msdn.microsoft.com/library/windows/desktop/ms693721)コンテナーで使用される、独自のインターフェイスへのポインターを保持する構造体。 クラス`IQuickActivateImpl`の既定の実装を提供**IQuickActivate**を実装および**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent  
 実行中のコントロールの現在の表示サイズを取得します。  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>コメント  
 サイズのコントロールの完全なレンダリングはであり HIMETRIC 単位で指定します。  
  
 参照してください[IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="quickactivate"></a>IQuickActivateImpl::QuickActivate  
 読み込む対象のコントロールの初期化を迅速に実行します。  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>コメント  
 構造体には、コントロールおよびそのアンビエント プロパティの値で必要なインターフェイスへのポインターが含まれています。 コントロールがへのポインターを渡す関数が戻るとき、[戻り値](http://msdn.microsoft.com/library/windows/desktop/ms693721)コンテナーを必要とする独自のインターフェイスとその他の状態情報へのポインターを格納する構造体。  
  
 参照してください[IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent  
 コンテナーが割り当てられて表示領域の量のコントロールに通知します。  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>コメント  
 サイズは、HIMETRIC 単位で指定されます。  
  
 参照してください[IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

