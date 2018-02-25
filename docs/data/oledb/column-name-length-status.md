---
title: COLUMN_NAME_LENGTH_STATUS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COLUMN_NAME_LENGTH_STATUS
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME_LENGTH_STATUS macro
ms.assetid: f73bd592-7ca7-461c-b106-9a8b1adbb01e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f29a8c9d856b95b85d60a29a12bf9359cebe0803
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="columnnamelengthstatus"></a>COLUMN_NAME_LENGTH_STATUS
行セットの特定の列を行セットのバインドを表します。 ような[COLUMN_NAME](../../data/oledb/column-name.md)ただし、このマクロは、列の長さと列の状態にも受け取ります。  
  
## <a name="syntax"></a>構文  
  
```cpp
COLUMN_NAME_LENGTH_STATUS(pszName, data, length, status )  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pszName`  
 [in]列の名前へのポインター。 名前は、Unicode 文字列にする必要があります。 たとえば、名前の前に 'L' を設定することによってこれを実行できます:`L"MyColumn"`です。  
  
 `data`  
 [in]ユーザー レコードに対応するデータ メンバーです。  
  
 *length*  
 [in]列の長さをバインドする変数です。  
  
 *status*  
 [in]列の状態にバインドする変数です。  
  
## <a name="remarks"></a>コメント  
 参照してください[COLUMN_NAME](../../data/oledb/column-name.md)場所について、 **COLUMN_NAME_\*** マクロを使用します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [マクロと OLE DB コンシューマー テンプレート用グローバル関数](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_NAME](../../data/oledb/column-name.md)   
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)