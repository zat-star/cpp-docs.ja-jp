---
title: "ISessionPropertiesImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISessionPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fafd303e6b03d5a78b11d9c6deb95233b082fd28
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="isessionpropertiesimpl-class"></a>ISessionPropertiesImpl クラス
実装を提供、 [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`ISessionPropertiesImpl`です。  
  
 `PropClass`  
 その既定値はユーザー定義プロパティ クラス`T`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|セッションで現在設定されているセッション プロパティ グループ内のプロパティの一覧を返します。|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|セッション プロパティ グループのプロパティを設定します。|  
  
## <a name="remarks"></a>コメント  
 セッションの必須インターフェイス。 このクラスでは、セッションのプロパティを実装によって定義された静的関数を呼び出すことによって、[プロパティ セット マップ](../../data/oledb/begin-propset-map.md)です。 セッション クラスでは、プロパティ セットのマップを指定してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)