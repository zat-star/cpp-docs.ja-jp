---
title: "IAccessorImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IAccessorImpl
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7cfc33432d12ac00c834d16f83cc26404e92c63e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl クラス
実装を提供、 [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, 
          class BindType = ATLBINDINGS,
          class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 行セットまたはコマンドのオブジェクト クラス。  
  
 `BindType`  
 バインディング情報の記憶域ユニットです。 既定値は、 **ATLBINDINGS**構造 (atldb.h を参照してください)。  
  
 `BindingVector`  
 列情報の記憶域ユニットです。 既定値は[CAtlMap](../../atl/reference/catlmap-class.md)ここで、重要な要素は、 **HACCESSOR**へのポインターを値と値の要素は、`BindType`構造体。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|コンストラクターです。|  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|既存のアクセサーには、参照カウントを追加します。|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|バインドのセットからアクセサーを作成します。|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|アクセサーのバインディングを返します。|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|アクセサーを解放します。|  
  
## <a name="remarks"></a>コメント  
 これは、行セットとコマンドでは必須です。 OLE DB プロバイダーを実装するを必要とする**HACCESSOR**、タグの配列には[DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx)構造体。 **HACCESSOR**によって提供される s`IAccessorImpl`のアドレス、`BindType`構造体。 既定では、`BindType`として定義されて、 **ATLBINDINGS**で`IAccessorImpl`のテンプレート定義。 `BindType` によって使用されるメカニズムを備えています`IAccessorImpl`内の要素の数を追跡するためにその**DBBINDING**参照の数およびアクセサーのフラグと配列。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)