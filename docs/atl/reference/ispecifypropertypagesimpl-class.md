---
title: "ISpecifyPropertyPagesImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4d5f74de2ec6569527221cf94df6f7921f4bb4c9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl クラス
このクラスは実装**IUnknown**の既定の実装を提供し、 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217)インターフェイスです。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`ISpecifyPropertyPagesImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|UUID の配列のカウント値を格納します。 各 UUID は、オブジェクトのプロパティ シートに表示できるプロパティ ページのいずれかの CLSID に対応します。|  
  
## <a name="remarks"></a>コメント  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217)インターフェイスにより、クライアントはオブジェクトでサポートされているプロパティ ページの Clsid の一覧を取得します。 クラス`ISpecifyPropertyPagesImpl`このインターフェイスの既定の実装を提供しを実装する**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
> [!NOTE]
>  公開しないでください、 **ISpecifyPropertyPages**インターフェイスの場合は、オブジェクトがプロパティ ページをサポートしていません。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  
  
##  <a name="getpages"></a>ISpecifyPropertyPagesImpl::GetPages  
 配列を設定、 [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048)構造とオブジェクトのプロパティ シートに表示できるプロパティ ページの clsid が存在します。  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>コメント  
 ATL では、オブジェクトのプロパティ マップを使用して、各 CLSID を取得します。  
  
 参照してください[ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [IPropertyPageImpl クラス](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

