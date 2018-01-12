---
title: "BLOB_ENTRY_LENGTH_STATUS |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY_LENGTH_STATUS
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY_LENGTH_STATUS macro
ms.assetid: 09da67de-421b-4853-9a26-760e38324502
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1362fd9b74e415a2502c64245b580acec6fba729
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="blobentrylengthstatus"></a>BLOB_ENTRY_LENGTH_STATUS
と共に使用`BEGIN_COLUMN_MAP`と`END_COLUMN_MAP`バイナリ ラージ オブジェクトをバインドする ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx))。 ような[BLOB_ENTRY](../../data/oledb/blob-entry.md)ただし、このマクロは、長さと、BLOB 列の状態も取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BLOB_ENTRY_LENGTH_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
, length, status )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `nOrdinal`  
 [in]列番号。  
  
 *IID*  
 [in]インターフェイスの GUID、よう**IDD_ISequentialStream**BLOB を取得するために使用します。  
  
 `flags`  
 [in]OLE 構造化ストレージ モデルで定義されているストレージ モード フラグを設定 (たとえば、 **STGM_READ**)。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
 *length*  
 [out]BLOB 列の (実際) の長さ (バイト単位)。  
  
 *status*  
 [out]BLOB のデータ列の状態。  
  
## <a name="example"></a>例  
 参照してください[BLOB を取得する方法ですか?](../../data/oledb/retrieving-a-blob.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)