---
title: "Ctable::open |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e664ddb310892004b95c81c8c7d93d8035b82cd3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ctableopen"></a>CTable::Open
テーブルを開きます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `session`  
 [in]対象のテーブルが開いているセッションです。  
  
 *wszTableName*  
 [in]開くには、テーブルの名前は、Unicode 文字列として渡されます。  
  
 *szTableName*  
 [in]開くには、テーブルの名前は、ANSI 文字列として渡されます。  
  
 *dbid*  
 [in]**DBID**を開くには、テーブルのです。  
  
 *pPropSet*  
 [in]配列へのポインター [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)プロパティと設定する値を含む構造体。 参照してください[プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx)で、 *OLE DB プログラマーズ リファレンス*Windows SDK にします。 既定値は NULL には、プロパティは指定しません。  
  
 `ulPropSets`  
 [in]数[DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)に渡された構造体、 *pPropSet*引数。  
  
## <a name="return-value"></a>戻り値  
 標準の `HRESULT`。  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [iopenrowset::openrowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CTable クラス](../../data/oledb/ctable-class.md)