---
title: "Crowset::movenext |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CRowset<TAccessor>.MoveNext
- ATL.CRowset.MoveNext
- ATL::CRowset<TAccessor>::MoveNext
- CRowset<TAccessor>.MoveNext
- CRowset.MoveNext
- CRowset<TAccessor>::MoveNext
- CRowset::MoveNext
- ATL::CRowset::MoveNext
dev_langs: C++
helpviewer_keywords: MoveNext method
ms.assetid: 0df3288c-2bce-494f-99c0-6344b54a4adf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e2b0a3a3a10ae2cc18ab83800cc50f25903a3607
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="crowsetmovenext"></a>CRowset::MoveNext
次のレコードにカーソルを移動します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT MoveNext( ) throw( );   
HRESULT MoveNext(   
   LONG lSkip,   
   bool bForward = true    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lSkip`  
 [in]フェッチする前にスキップする行の数。  
  
 `bForward`  
 [in]渡す**true**次のレコードに前方に移動する**false**後方移動します。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。 行セットの末尾に到達したときに返されます**DB_S_ENDOFROWSET**です。  
  
## <a name="remarks"></a>コメント  
 [次へ] の順次行のフェッチ、`CRowset`オブジェクト、前の位置を記憶します。 必要に応じて、スキップを選択できます`lSkip`行または旧バージョンと移動します。  
  
 このメソッドは、呼び出す前に、次のプロパティを設定することが必要です**開く**テーブルまたは行セットを含むコマンド。  
  
-   **DBPROP_CANSCROLLBACKWARDS**する必要があります`VARIANT_TRUE`場合`lSkip`< 0  
  
-   **DBPROP_CANFETCHBACKWARDS**する必要があります`VARIANT_TRUE`場合`bForward`= false  
  
 それ以外の場合 (場合`lSkip`> = 0 および`bForward`= true)、その他のプロパティを設定する必要はありません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CRowset クラス](../../data/oledb/crowset-class.md)   
 [Crowset::movefirst](../../data/oledb/crowset-movefirst.md)   
 [Crowset::movetobookmark](../../data/oledb/crowset-movetobookmark.md)   
 [Crowset::moveprev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)