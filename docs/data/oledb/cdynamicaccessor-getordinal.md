---
title: "Cdynamicaccessor::getordinal |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicAccessor.GetOrdinal
- ATL::CDynamicAccessor::GetOrdinal
- CDynamicAccessor::GetOrdinal
- ATL.CDynamicAccessor.GetOrdinal
- GetOrdinal
dev_langs: C++
helpviewer_keywords: GetOrdinal method
ms.assetid: 2095b71c-a7a4-4034-89a1-77a78cb9633f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b86ce9f5b27e7dc51cbebdbbd24b90dd9effa5fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorgetordinal"></a>CDynamicAccessor::GetOrdinal
列名を指定した列番号を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool GetOrdinal(  
   const CHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
bool GetOrdinal(  
   const WCHAR* pColumnName,  
   DBORDINAL* pOrdinal   
) const throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `pColumnName`  
 [in]列名を含む文字列へのポインター。  
  
 *pOrdinal*  
 [out]列番号へのポインター。  
  
## <a name="return-value"></a>戻り値  
 返します**true**指定した名前の列が検出された場合。 この関数を返しますそれ以外の場合、 **false**です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)