---
title: "ICommandPropertiesImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandPropertiesImpl class
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 36c524d8aae9223e47b39bfe6cbfdfafdaa006f6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl クラス
実装を提供、 [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生クラス。  
  
 `PropClass`  
 プロパティ クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|現在の行セット要求されている行セット プロパティ グループのプロパティの一覧を返します。|  
|[SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)|行セット プロパティ グループのプロパティを設定します。|  
  
## <a name="remarks"></a>コメント  
 これは、コマンドでは必須です。 によって定義された静的関数によって提供される、実装、 [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)マクロです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)