---
title: "BLOB_ENTRY_LENGTH |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BLOB_ENTRY_LENGTH
dev_langs: C++
helpviewer_keywords: BLOB_ENTRY_LENGTH macro
ms.assetid: 832d21ab-5fdd-49ad-af6e-4fca5722ec93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0de1707ab616aca49061590bfb76bf74360019ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="blobentrylength"></a>BLOB_ENTRY_LENGTH
と共に使用`BEGIN_COLUMN_MAP`と`END_COLUMN_MAP`バイナリ ラージ オブジェクトをバインドする ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx))。 ような[BLOB_ENTRY](../../data/oledb/blob-entry.md)も、このマクロは、BLOB 列のバイト単位の長さを取得する点を除いて、します。  
  
## <a name="syntax"></a>構文  
  
```  
  
BLOB_ENTRY_LENGTH(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
,   
length  
 )  
  
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
  
## <a name="example"></a>例  
 参照してください[BLOB を取得する方法ですか?](../../data/oledb/retrieving-a-blob.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)   
 [BLOB_ENTRY_STATUS](../../data/oledb/blob-entry-status.md)