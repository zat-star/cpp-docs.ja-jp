---
title: "ICommandPropertiesImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
dev_langs: C++
helpviewer_keywords: ICommandPropertiesImpl class
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1c00256109998dbef41c1c16d8e66d9bea3b57b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="icommandpropertiesimpl-class"></a>ICommandPropertiesImpl クラス
実装を提供、 [ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```  
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)