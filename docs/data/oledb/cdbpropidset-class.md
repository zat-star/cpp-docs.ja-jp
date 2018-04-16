---
title: "CDBPropIDSet クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBPropIDSet
- ATL.CDBPropIDSet
- ATL::CDBPropIDSet
dev_langs:
- C++
helpviewer_keywords:
- CDBPropIDSet class
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ee03feb715ebf96bd4de1af5374a2029f52bbf86
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cdbpropidset-class"></a>CDBPropIDSet クラス
継承、**コンス トラクターは**構造体し、キー フィールドを初期化するコンス トラクターを追加するだけでなく[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)メソッドにアクセスします。  
  
## <a name="syntax"></a>構文

```cpp
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|プロパティ ID セットにプロパティを追加します。|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|コンストラクターです。|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|プロパティ ID の GUID を設定します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator =](../../data/oledb/cdbpropidset-operator-equal.md)|割り当て ID の 1 つのプロパティの内容は、別に設定されます。|  
  
## <a name="remarks"></a>コメント  
 OLE DB コンシューマーを使用して**コンス トラクターは**プロパティ情報を取得するコンシューマーは、これに関するプロパティ Id の配列を渡すための構造体。 1 つの指定されたプロパティ[コンス トラクターは](https://msdn.microsoft.com/en-us/library/ms717981.aspx)構造体が 1 つのプロパティ セットに属しています。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)