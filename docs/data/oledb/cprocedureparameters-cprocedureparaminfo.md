---
title: "CProcedureParameters、CProcedureParamInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szDefault
- CProcedureParameters
- m_bHasDefault
- CProcedureParamInfo
- IS_NULLABLE
- m_szCatalog
- ORDINAL_POSITION
- m_nOrdinalPosition
- NUMERIC_PRECISION
- m_nDataType
- m_szSchema
- CHARACTER_OCTET_LENGTH
- NUMERIC_SCALE
- m_szParameterName
- m_nMaxLength
- CHARACTER_MAXIMUM_LENGTH
- m_nPrecision
- m_szName
- DATA_TYPE
- m_nOctetLength
- m_nType
- m_bIsNullable
- m_nScale
dev_langs: C++
helpviewer_keywords:
- NUMERIC_PRECISION
- DATA_TYPE
- ORDINAL_POSITION
- m_nMaxLength
- DESCRIPTION class data member
- m_szParameterName
- m_szSchema
- m_nType
- m_bHasDefault
- CHARACTER_OCTET_LENGTH
- CProcedureParameters typedef class
- m_szCatalog
- m_nPrecision
- m_nOrdinalPosition
- NUMERIC_SCALE
- m_nOctetLength
- IS_NULLABLE
- m_szName
- m_bIsNullable
- CProcedureParamInfo parameter class
- m_szDescription
- m_szDefault
- m_nDataType
- m_nScale
- CHARACTER_MAXIMUM_LENGTH
ms.assetid: 61f8d55a-684a-47a3-b102-068cc3f52d84
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d3f4a28a882a9de9bdb3630ebc2bb7d2adda48c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cprocedureparameters-cprocedureparaminfo"></a>CProcedureParameters、CProcedureParamInfo
Typedef クラスを呼び出す**CProcedureParameters**そのパラメーター クラスを実装する**、CProcedureParamInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、パラメーターおよびプロシージャのリターン コードに関する情報を返します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[PROCEDURE_PARAMETERS 行セット](https://msdn.microsoft.com/en-us/library/ms713623.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szCatalog|PROCEDURE_CATALOG|  
|m_szSchema|PROCEDURE_SCHEMA|  
|m_szName|PROCEDURE_NAME|  
|m_szParameterName|PARAMETER_NAME|  
|m_nOrdinalPosition|ORDINAL_POSITION|  
|m_nType|PARAMETER_TYPE|  
|m_bHasDefault|PARAMETER_HASDEFAULT|  
|m_szDefault|PARAMETER_DEFAULT|  
|m_bIsNullable|IS_NULLABLE|  
|m_nDataType|DATA_TYPE|  
|m_nMaxLength|CHARACTER_MAXIMUM_LENGTH|  
|m_nOctetLength|CHARACTER_OCTET_LENGTH|  
|m_nPrecision|NUMERIC_PRECISION|  
|m_nScale|NUMERIC_SCALE|  
|m_szDescription|説明|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)