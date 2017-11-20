---
title: "CStreamRowset クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CStreamRowset<TAccessor>
- ATL::CStreamRowset
- CStreamRowset
- ATL.CStreamRowset<TAccessor>
- ATL.CStreamRowset
dev_langs: C++
helpviewer_keywords: CStreamRowset class
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 003b6b84195c491d1c72c3de289de375459ba261
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cstreamrowset-class"></a>CStreamRowset クラス
使用される、`CCommand`または`CTable`宣言します。  
  
## <a name="syntax"></a>構文  
  
```  
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
  
 `ICommand::Execute`返します、`ISequentialStream`に格納されているポインター`m_spStream`です。 使用して、**読み取り**の XML 形式 (Unicode 文字列) のデータを取得します。 例:  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/cpp/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 では、XML 書式設定でを実行し、すべての列と 1 つの XML 文字列として、行セットのすべての行に返されます。  
  
> [!NOTE]
>  この機能は、SQL Server 2000 でのみ動作します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)