---
title: "PROVIDER_COLUMN_ENTRY_STR |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROVIDER_COLUMN_ENTRY_STR
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_STR macro
ms.assetid: f1c27dd6-9ab8-4821-8685-d4dd15e76e88
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9e5f4d21d0ffae232a3e4b313c4156ed18311288
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="providercolumnentrystr"></a>PROVIDER_COLUMN_ENTRY_STR
プロバイダーでサポートされている特定の列を表します。  
  
## <a name="syntax"></a>構文  
  
```cpp
PROVIDER_COLUMN_ENTRY_STR(name  
, ordinal, member )  
```  
  
#### <a name="parameters"></a>パラメーター  
 *name*  
 [in]列の名前。  
  
 `ordinal`  
 [in]列番号。 列は、ブックマーク列でない限り、列番号は 0 をできません。  
  
 `member`  
 [in]データを格納するデータ クラスにメンバー変数です。  
  
## <a name="remarks"></a>コメント  
 列のデータが想定するときに、このマクロを使用して[DBTYPE_STR](https://msdn.microsoft.com/en-us/library/ms711251.aspx)です。  
  
## <a name="example"></a>例  
 参照してください[BEGIN_PROVIDER_COLUMN_MAP](../../data/oledb/begin-provider-column-map.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)