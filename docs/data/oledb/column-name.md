---
title: "COLUMN_NAME |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_NAME
dev_langs: C++
helpviewer_keywords: COLUMN_NAME macro
ms.assetid: a213b9a0-2148-4a08-9111-d9fa8fdec462
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 83b65a0439591d9783595bd2e0868e2d63568143
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="columnname"></a>COLUMN_NAME
行セットの特定の列を行セットのバインドを表します。 ような[COLUMN_ENTRY](../../data/oledb/column-entry.md)ただし、このマクロは列の数値の代わりに列名を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
COLUMN_NAME(  
pszName  
,   
data  
 )  
  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszName`  
 [in]列の名前へのポインター。 名前は、Unicode 文字列にする必要があります。 たとえば、名前の前に 'L' を設定することによってこれを実行できます:`L"MyColumn"`です。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
## <a name="remarks"></a>コメント  
 **COLUMN_NAME_\*** マクロが場合と同じ場所で使用される[COLUMN_ENTRY](../../data/oledb/column-entry.md):  
  
-   間、 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)と[END_COLUMN_MAP](../../data/oledb/end-column-map.md)マクロです。  
  
-   間、 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)と[END_ACCESSOR](../../data/oledb/end-accessor.md)マクロです。  
  
-   間、 [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md)と[END_PARAM_MAP](../../data/oledb/end-param-map.md)マクロです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)