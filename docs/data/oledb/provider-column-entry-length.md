---
title: "PROVIDER_COLUMN_ENTRY_LENGTH |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PROVIDER_COLUMN_ENTRY_LENGTH
dev_langs: C++
helpviewer_keywords: PROVIDER_COLUMN_ENTRY_LENGTH macro
ms.assetid: b4a67246-c049-4622-bb65-242cc8cae4be
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e7f0d4ed3eeff7d60aa91849d62446d17765ce52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="providercolumnentrylength"></a>PROVIDER_COLUMN_ENTRY_LENGTH
プロバイダーでサポートされている特定の列を表します。  
  
## <a name="syntax"></a>構文  
  
```  
  
PROVIDER_COLUMN_ENTRY_LENGTH(  
name  
, ordinal, size, member )  
```  
  
#### <a name="parameters"></a>パラメーター  
 *name*  
 [in]列の名前。  
  
 `ordinal`  
 [in]列番号。 列は、ブックマーク列でない限り、列番号は 0 をできません。  
  
 `size`  
 [in]列のサイズ (バイト単位)。  
  
 `member`  
 [in]内のメンバー変数`dataClass`列のデータを格納します。  
  
## <a name="remarks"></a>コメント  
 列のサイズを指定できます。  
  
## <a name="example"></a>例  
 参照してください[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)