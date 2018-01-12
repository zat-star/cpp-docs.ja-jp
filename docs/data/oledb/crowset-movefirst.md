---
title: "Crowset::movefirst |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRowset<TAccessor>::MoveFirst
- ATL::CRowset::MoveFirst
- CRowset<TAccessor>.MoveFirst
- CRowset::MoveFirst
- CRowset.MoveFirst
- ATL.CRowset.MoveFirst
- ATL.CRowset<TAccessor>.MoveFirst
- ATL::CRowset<TAccessor>::MoveFirst
dev_langs: C++
helpviewer_keywords: MoveFirst method
ms.assetid: a17c0799-ead9-4d85-9a1d-8b17188d01e3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 405549f94e5aad7ea241a5b6ed4687084aa73ff0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetmovefirst"></a>CRowset::MoveFirst
最初の位置にカーソルを移動し、最初の行を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
HRESULT MoveFirst( ) throw( );  
  
```  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 呼び出し[irowset::restartposition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)を初期位置 (行セットの作成時に、次のフェッチ位置をした位置) に次のフェッチ位置の位置を変更して、最初の行を取得します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [Crowset::movenext](../../data/oledb/crowset-movenext.md)   
 [Crowset::movetobookmark](../../data/oledb/crowset-movetobookmark.md)   
 [Crowset::moveprev](../../data/oledb/crowset-moveprev.md)   
 [Crowset::movelast](../../data/oledb/crowset-movelast.md)   
 [Irowset::restartposition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)