---
title: "Cdynamicaccessor::getcolumninfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetColumnInfo
- ATL.CDynamicAccessor.GetColumnInfo
- ATL::CDynamicAccessor::GetColumnInfo
- CDynamicAccessor.GetColumnInfo
- CDynamicAccessor::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8091dec73a4a0d5f3c933988484fb59caaebae97
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicaccessorgetcolumninfo"></a>CDynamicAccessor::GetColumnInfo
ほとんどのコンシューマーが必要な列のメタデータを返します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT GetColumnInfo(IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pRowset`  
 [in]ポインター、 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx)インターフェイスです。  
  
 *pColumns*  
 [out]行セットの列の数を返すメモリへのポインターこの数には、1 つを使用する必要がある場合、ブックマーク列が含まれます。  
  
 *ppColumnInfo*  
 [out]配列を返すメモリへのポインター **DBCOLUMNINFO**構造体。 「DBCOLUMNINFO 構造体」を参照してください[icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 `ppStringsBuffer`  
 [out]すべての文字列値のストレージへのポインターを返すメモリへのポインター (内のいずれかの名前が使用される*columnid*または*pwszName*) 1 つのアロケーション ブロック内で。  
  
## <a name="return-value"></a>戻り値  
 標準の`HRESULT`値。  
  
## <a name="remarks"></a>コメント  
 参照してください[icolumnsinfo::getcolumninfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx)で、 *OLE DB プログラマーズ リファレンス*については、データ型に**DBORDINAL**、 **DBCOLUMNINFO**、および**OLECHAR**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)