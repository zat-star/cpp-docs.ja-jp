---
title: "Crowset::updateall |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowset::UpdateAll
- ATL.CRowset.UpdateAll
- CRowset<TAccessor>.UpdateAll
- ATL.CRowset<TAccessor>.UpdateAll
- UpdateAll
- CRowset.UpdateAll
- ATL::CRowset<TAccessor>::UpdateAll
- CRowset<TAccessor>::UpdateAll
- ATL::CRowset::UpdateAll
dev_langs:
- C++
helpviewer_keywords:
- UpdateAll method
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 759b00cddb37a2ceab97fe25762b88d53e3ec0ab
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetupdateall"></a>CRowset::UpdateAll
保留中の最後のフェッチで、以降のすべての行に行われた変更を送信または**更新**それで呼び出します。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT UpdateAll(DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pcRows`  
 [out]場所へのポインターを`UpdateAll`試行されると必要な場合、更新するには行の数を返します。  
  
 `pphRow`  
 [out]メモリへのポインター`UpdateAll`を更新しようとしましたが、行のハンドルを返します。 場合はハンドルが返されない`pphRow`が null です。  
  
 `ppStatus`  
 [out]場所へのポインターを**更新**行の状態値を返します。 場合のステータスが返されない`ppStatus`が null です。  
  
## <a name="remarks"></a>コメント  
 保留中のこれらの行が最後にフェッチされたかを使用して更新後のすべての行に加えられた変更を送信[更新](../../data/oledb/crowset-update.md)または`UpdateAll`です。 `UpdateAll` 変更されたかどうかがあるハンドルに関係なくすべての行を更新 (を参照してください`pphRow`) か。  
  
 使用する場合など、**挿入**行を挿入する 5 つの行セットで、いずれかの呼び出しをでした**更新**5 回または呼び出し`UpdateAll`更新すべてを 1 回です。  
  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetUpdate`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetUpdate**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)