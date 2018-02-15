---
title: "Crowset::movetobookmark |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRowset::MoveToBookmark
- ATL::CRowset<TAccessor>::MoveToBookmark
- ATL.CRowset.MoveToBookmark
- ATL.CRowset<TAccessor>.MoveToBookmark
- MoveToBookmark
- CRowset::MoveToBookmark
- CRowset.MoveToBookmark
- CRowset<TAccessor>::MoveToBookmark
dev_langs:
- C++
helpviewer_keywords:
- MoveToBookmark method
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2e443cace051fc0d5c08381222f0cd6aa53bec8f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="crowsetmovetobookmark"></a>CRowset::MoveToBookmark
ブックマークまたは指定されたオフセット位置の行でマークされた行がフェッチされます (`lSkip`) そのブックマークからです。  
  
## <a name="syntax"></a>構文  
  
```cpp
HRESULT MoveToBookmark(const CBookmarkBase& bookmark,   
   LONG lSkip = 0) throw();  
```  
  
#### <a name="parameters"></a>パラメーター  
 `bookmark`  
 [in]データをフェッチする位置を示すブックマーク。  
  
 `lSkip`  
 [in]対象の行にブックマークからの行の数。 場合`lSkip`0 の場合は、フェッチされた最初の行は、ブックマークが付けられた行です。 場合`lSkip`1 の場合は、ブックマークが付けられた行の後ろには、行、最初の行をフェッチします。 場合`lSkip`-1 で、最初のフェッチされた行は、行のブックマークが付けられた行の前にします。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 このメソッドには、省略可能なインターフェイスが必要とする`IRowsetLocate`、する可能性がありますすべてのプロバイダーでサポートされていない以外の場合は、そうでは、返されます**E_NOINTERFACE**です。 設定する必要もあります**DBPROP_IRowsetLocate**に`VARIANT_TRUE`設定と**DBPROP_CANFETCHBACKWARDS**に`VARIANT_TRUE`呼び出す前に**開く**テーブルまたはコマンド行セットを含むです。  
  
 コンシューマーでのブックマークの使用方法の詳細については、次を参照してください。[を使用してブックマーク](../../data/oledb/using-bookmarks.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)