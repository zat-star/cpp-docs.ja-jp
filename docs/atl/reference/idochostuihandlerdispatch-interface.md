---
title: "IDocHostUIHandlerDispatch インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDocHostUIHandlerDispatch
- atlbase/ATL::IDocHostUIHandlerDispatch
dev_langs:
- C++
helpviewer_keywords:
- IDocHostUIHandlerDispatch interface
ms.assetid: 6963a301-601a-4ac3-8bef-f7b252ea2fc6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ba89697fb1c0e81d648d8faaaff1a97bb6a5d9ea
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="idochostuihandlerdispatch-interface"></a>IDocHostUIHandlerDispatch インターフェイス
Microsoft HTML 解析およびレンダリング エンジンのインターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
interface IDocHostUIHandlerDispatch : IDispatch
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
> [!NOTE]
>  次の表のリンクが、INet SDK リファレンス トピックへのメンバーに対しては、 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)インターフェイスです。 `IDocHostUIHandlerDispatch`同じ機能を持ち**IDocUIHostHandler**、記述されていること、違い`IDocHostUIHandlerDispatch`ディスパッチ インターフェイスがありますが**IDocUIHostHandler**はカスタム インターフェイスです。  
  
|||  
|-|-|  
|[EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)|MSHTML 実装から呼び出される[IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115)します。 MSHTML モーダル UI を表示するときとも呼ばれます。|  
|[FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)|MSHTML MSHTML のデータ オブジェクトを置換するホストを許可するように使用して、ホストに対して呼び出されます。|  
|[GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)|別の方法を提供するホストを許可するようにドロップ先として使用している場合、MSHTML によって呼び出されます[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)します。|  
|[GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)|ホストの IDispatch インターフェイスを取得するために MSHTML によって呼び出されます。|  
|[GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)|MSHTML ホストの UI 機能を取得します。|  
|[GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)|MSHTML がユーザー設定を格納するレジストリ キーを返します。|  
|[HideUI](https://msdn.microsoft.com/library/aa753259.aspx)|MSHTML メニューおよびツールバーを削除するときに呼び出されます。|  
|[OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)|MSHTML 実装から呼び出される[IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281)します。|  
|[OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)|MSHTML 実装から呼び出される[IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969)します。|  
|[ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)|MSHTML 実装から呼び出される[IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053)します。|  
|[ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)|コンテキスト メニューを表示するために MSHTML から呼び出されます。|  
|[ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)|ホストが MSHTML メニューおよびツールバーを置換できるようにします。|  
|[TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)|MSHTML によって呼び出されるときに[IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360)または[IOleControlSite::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693756)が呼び出されます。|  
|[TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)|ホストに読み込まれる URL を変更することを許可するために MSHTML によって呼び出されます。|  
|[Updateui という](https://msdn.microsoft.com/library/aa753268.aspx)|コマンドの状態が変化したことをホストに通知します。|  
  
## <a name="remarks"></a>コメント  
 ホストは、メニューのツールバー、およびこのインターフェイスを実装することによって Microsoft HTML 解析およびレンダリング エンジン (MSHTML) で使用されるコンテキスト メニューに置き換えることができます。  
  
## <a name="requirements"></a>要件  
 このインターフェイスの定義は、次のようとして idl ファイルまたは C++ では、使用可能です。  
  
|定義の種類|ファイル|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h にも含まれます)|  
  
## <a name="see-also"></a>関連項目  
 [IDocUIHostHandler](https://msdn.microsoft.com/library/aa753260.aspx)










