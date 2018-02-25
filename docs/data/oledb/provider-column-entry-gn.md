---
title: "PROVIDER_COLUMN_ENTRY_GN |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- PROVIDER_COLUMN_ENTRY_GN
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_GN macro
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ff73cda1e676387b4f8ca79ce1ef7cbf8fce13e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="providercolumnentrygn"></a>PROVIDER_COLUMN_ENTRY_GN
プロバイダーでサポートされている特定の列を表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
PROVIDER_COLUMN_ENTRY_GN (name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### <a name="parameters"></a>パラメーター  
 *name*  
 [in]列の名前。  
  
 `ordinal`  
 [in]列番号。 列は、ブックマーク列でない限り、列番号は 0 をできません。  
  
 `flags`  
 [in]データを返す方法を指定します。 参照してください、`dwFlags`説明[DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)です。  
  
 *colSize*  
 [in]列のサイズ。  
  
 `dbtype`  
 [in]値のデータ型を示します。 参照してください、 **wType**説明[DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)です。  
  
 *precision*  
 [in]場合にデータを取得するときに使用する有効桁数を示す*dbType*は`DBTYPE_NUMERIC`または**DBTYPE_DECIMAL**です。 参照してください、 **bPrecision**説明[DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)です。  
  
 `scale`  
 [in]DbType がある場合は、データを取得するときに使用する小数点以下桁数を示す`DBTYPE_NUMERIC`または**DBTYPE_DECIMAL**です。 参照してください、 **bScale**説明[DBBINDING 構造体](https://msdn.microsoft.com/en-us/library/ms716845.aspx)です。  
  
 `guid`  
 スキーマ行セットの GUID。 参照してください[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマ行セットとその Guid の一覧についてはします。  
  
## <a name="remarks"></a>コメント  
 列のサイズ、データ型、有効桁数、小数点以下桁数、およびスキーマ行セット GUID を指定できます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)