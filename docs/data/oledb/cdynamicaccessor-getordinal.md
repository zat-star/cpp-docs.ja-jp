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
ms.openlocfilehash: 6ea8e4e4478b47a333facfbb38bfeb856ef08fe3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)