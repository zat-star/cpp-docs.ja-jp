---
title: "IPropertyNotifySinkCP クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyNotifySinkCP
- atlctl/ATL::IPropertyNotifySinkCP
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- sinks, notifying of changes
- IPropertyNotifySinkCP class
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: feff2467d6d72e9d0a9186dc269f48eb26cbfee2
ms.lasthandoff: 03/17/2017

---
# <a name="ipropertynotifysinkcp-class"></a>IPropertyNotifySinkCP クラス
このクラスは、公開[IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)接続可能オブジェクトの送信インターフェイスとインターフェイスします。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, class CDV = CComDynamicUnkArray>  
class IPropertyNotifySinkCP 
   : public IConnectionPointImpl<T, &IID_IPropertyNotifySink, CDV>
```    
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラスに、`IPropertyNotifySinkCP`です。  
  
 `CDV`  
 接続ポイントとそのシンク間の接続を管理するクラス。 既定値は[CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)、無制限の接続を許可します。 使用することも[CComUnkArray](../../atl/reference/ccomunkarray-class.md)接続の数を指定します。  
  
## <a name="remarks"></a>コメント  
 `IPropertyNotifySinkCP`その基本クラスからのすべてのメソッドを継承[IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md)します。  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638)インターフェイスにより、シンク オブジェクトのプロパティの変更に関する通知を受信できます。 クラス`IPropertyNotifySinkCP`このインターフェイスが接続可能オブジェクトの送信インターフェイスとして公開します。 クライアントを実装する必要があります、`IPropertyNotifySink`シンク上のメソッドです。  
  
 クラスを派生`IPropertyNotifySinkCP`を表す接続ポイントを作成する場合、`IPropertyNotifySink`インターフェイスです。  
  
 ATL でのコネクション ポイントの使用に関する詳細については、記事を参照してください。[コネクション ポイント](../../atl/atl-connection-points.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlctl.h  
  
## <a name="see-also"></a>関連項目  
 [IConnectionPointImpl クラス](../../atl/reference/iconnectionpointimpl-class.md)   
 [入力したコネクション クラス](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

