---
title: "CDBPropSet クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet
- ATL.CDBPropSet
- ATL::CDBPropSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropSet class
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 692bb3ccb20373a0bc2765675138eb15daadcb0e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cdbpropset-class"></a>CDBPropSet クラス
継承、 **DBPROPSET**構造体し、キー フィールドを初期化するコンス トラクターを追加するだけでなく`AddProperty`メソッドにアクセスします。  
  
## <a name="syntax"></a>構文

```cpp
class CDBPropSet : public tagDBPROPSET  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|プロパティ セットに、プロパティを追加します。|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|コンストラクターです。|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|セット、**コンス トラクターは**のフィールド、 **DBPROPSET**構造体。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator =](../../data/oledb/cdbpropset-operator-equal.md)|1 つのプロパティ セットを他の内容を割り当てます。|  
  
## <a name="remarks"></a>コメント  
 OLE DB プロバイダーとコンシューマーの使用**DBPROPSET**構造体の配列を渡す`DBPROP`構造体。 各`DBPROP`構造体を設定できる 1 つのプロパティを表します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet クラス](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET 構造体](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP 構造体](https://msdn.microsoft.com/en-us/library/ms717970.aspx)