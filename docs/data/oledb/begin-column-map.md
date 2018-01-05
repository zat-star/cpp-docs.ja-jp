---
title: "BEGIN_COLUMN_MAP |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_COLUMN_MAP macro
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9edcaa47bccf0665ddeabf4e65e16ab1642de885
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="begincolumnmap"></a>BEGIN_COLUMN_MAP
列マップ エントリの先頭を示します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 *x*  
 [入力] `CAccessor`から派生したユーザー レコード クラスの名前。  
  
## <a name="remarks"></a>コメント  
 このマクロは、行セットに対してアクセサーが 1 つしか必要ない場合に使用します。 1 つの行セットに対して複数のアクセサーが必要な場合は、 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)を使用します。  
  
 `BEGIN_COLUMN_MAP` マクロは `END_COLUMN_MAP` マクロで終了します。 このマクロは、ユーザー レコードで 1 つのアクセサーだけが必要な場合に使用します。  
  
 列は、バインドする行セットのフィールドに相当します。  
  
## <a name="example"></a>例  
 列およびパラメーター マップのコード例を次に示します。  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)