---
title: "Crowset::undo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset.Undo
- ATL::CRowset<TAccessor>::Undo
- CRowset<TAccessor>::Undo
- ATL.CRowset.Undo
- ATL.CRowset<TAccessor>.Undo
- CRowset<TAccessor>.Undo
- ATL::CRowset::Undo
- CRowset::Undo
- Undo
dev_langs: C++
helpviewer_keywords: Undo method
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d56be5cbaf5f8c3393527c59319cdda4aca124e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetundo"></a>CRowset::Undo
最後のフェッチ行に加えられた変更を元に戻すまたは[更新](../../data/oledb/crowset-update.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Undo(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pcRows`  
 [out]場所へのポインターを**を元に戻す**しようとするために必要な場合に、取り消す行の数を返します。  
  
 `phRow`  
 [out]場所へのポインターを**を元に戻す**しようとするために必要な場合に、取り消すすべての行ハンドルの配列を返します。  
  
 `pStatus`  
 [out]場所へのポインターを**を元に戻す**行の状態値を返します。 場合のステータスが返されない`pStatus`が null です。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetUpdate`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetUpdate**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたは行セットを含むコマンドをします。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)