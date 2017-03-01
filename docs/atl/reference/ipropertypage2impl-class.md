---
title: "IPropertyPage2Impl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 43680d12febbd94137009f66242198129d4b3630
ms.lasthandoff: 02/24/2017

---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl クラス
このクラスは実装**IUnknown**の既定の実装の継承と[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IPropertyPage2Impl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|プロパティ ページがアクティブになったときにどのプロパティ コントロールがフォーカスを受け取るを指定します。 ATL の実装を返します**E_NOTIMPL**します。|  
  
## <a name="remarks"></a>コメント  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996)拡張したインターフェイスで[IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)追加することで、`EditProperty`メソッドです。 このメソッドは、プロパティ ページのオブジェクトで特定のプロパティを選択するクライアントを使用します。  
  
 クラス`IPropertyPage2Impl`を返すだけ**E_NOTIMPL**の**IPropertyPage2::EditProperty**します。 ただし、既定の実装の継承[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)を実装および**IUnknown**ダンプ情報を送信することによってデバッグでデバイスをビルドします。  
  
 クラスは一般から派生するプロパティ ページを作成するときに`IPropertyPageImpl`します。 特別なサポートを提供する**IPropertyPage2**、クラス定義を変更し、オーバーライド、`EditProperty`メソッドです。  
  
 **関連資料** [ATL チュートリアル](../../atl/active-template-library-atl-tutorial.md)、 [ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
##  <a name="a-nameeditpropertya--ipropertypage2impleditproperty"></a><a name="editproperty"></a>IPropertyPage2Impl::EditProperty  
 プロパティ ページがアクティブになったときにどのプロパティ コントロールがフォーカスを受け取るを指定します。  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **E_NOTIMPL**します。  
  
### <a name="remarks"></a>コメント  
 参照してください[IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
## <a name="see-also"></a>関連項目  
 [IPerPropertyBrowsingImpl クラス](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl クラス](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

