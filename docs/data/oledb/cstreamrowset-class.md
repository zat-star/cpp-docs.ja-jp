---
title: "CStreamRowset クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
dev_langs:
- C++
helpviewer_keywords:
- CStreamRowset class
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 817d9454ad97580cdfb3eb6d68fbc819ed64dd90
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cstreamrowset-class"></a>CStreamRowset クラス
使用される、`CCommand`または`CTable`宣言します。  
  
## <a name="syntax"></a>構文

```cpp
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TAccessor`  
 アクセサー クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|コンストラクターです。 インスタンスを作成し、初期化、`CStreamRowset`オブジェクト。|  
|[閉じる](../../data/oledb/cstreamrowset-close.md)|リリース、 [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx)クラスのインターフェイス ポインター。|  
  
## <a name="remarks"></a>コメント  
 使用して`CStreamRowset`で、`CCommand`または`CTable`例については、宣言します。  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/cpp/cstreamrowset-class_1.cpp)]  
  
 または  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/cpp/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` 返します、`ISequentialStream`に格納されているポインター`m_spStream`です。 使用して、**読み取り**の XML 形式 (Unicode 文字列) のデータを取得します。 例:  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 では、XML 書式設定でを実行し、すべての列と 1 つの XML 文字列として、行セットのすべての行に返されます。  
  
> [!NOTE]
>  この機能は、SQL Server 2000 でのみ動作します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)