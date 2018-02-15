---
title: "IDBPropertiesImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl
- ATL.IDBPropertiesImpl
- ATL.IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl<T>
- ATL::IDBPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBPropertiesImpl class
ms.assetid: a7f15a8b-95b2-4316-b944-d5d03f8d74ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2cc488ac71afedaaf590ef93dbc8d43997e30d0c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="idbpropertiesimpl-class"></a>IDBPropertiesImpl クラス
実装を提供、`IDBProperties`インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
template <class T>   
class ATL_NO_VTABLE IDBPropertiesImpl   
   : public IDBProperties, public CUtlProps<T>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 派生したクラス、`IDBPropertiesImpl`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)|データ ソース オブジェクトで現在設定されている初期化プロパティ グループ内のプロパティの値に設定されているデータ ソース、データ ソース情報、および初期化プロパティ グループのプロパティの値を返す、列挙子。|  
|[GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)|プロバイダーでサポートされているすべてのプロパティに関する情報を返します。|  
|[SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)|列挙子のデータ ソースと初期化プロパティ グループのデータ ソース オブジェクトまたは Initialization プロパティ グループのプロパティを設定します。|  
  
## <a name="remarks"></a>コメント  
 [IDBProperties](https://msdn.microsoft.com/en-us/library/ms719607.aspx)はデータ ソース オブジェクトに必要なインターフェイスと列挙子のオプションのインターフェイスです。 ただし、列挙子を公開する場合[IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx)、公開している`IDBProperties`です。 `IDBPropertiesImpl` 実装する`IDBProperties`によって定義された静的関数を使用して[BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)