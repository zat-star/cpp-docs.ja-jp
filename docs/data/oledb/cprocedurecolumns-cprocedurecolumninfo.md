---
title: "CProcedureColumns、CProcedureColumnInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- m_guidType
- CProcedureColumnInfo
- IS_NULLABLE
- m_szCatalog
- m_nRowsetNumber
- m_nColumnPropID
- ORDINAL_POSITION
- m_nOrdinalPosition
- COLUMN_GUID
- m_szColumnName
- NUMERIC_PRECISION
- m_nDataType
- m_szSchema
- CHARACTER_OCTET_LENGTH
- NUMERIC_SCALE
- COLUMN_PROPID
- m_guidColumn
- m_nMaxLength
- CHARACTER_MAXIMUM_LENGTH
- m_nPrecision
- m_szName
- CProcedureColumns
- DATA_TYPE
- m_nOctetLength
- m_bIsNullable
- m_nScale
dev_langs:
- C++
helpviewer_keywords:
- NUMERIC_PRECISION
- COLUMN_PROPID
- DATA_TYPE
- ORDINAL_POSITION
- m_nMaxLength
- DESCRIPTION class data member
- m_guidType
- m_szSchema
- CHARACTER_OCTET_LENGTH
- m_szCatalog
- CProcedureColumns typedef class
- m_nPrecision
- m_nOrdinalPosition
- m_nColumnPropID
- NUMERIC_SCALE
- m_nRowsetNumber
- m_szColumnName
- COLUMN_NAME
- m_nOctetLength
- IS_NULLABLE
- m_szName
- m_bIsNullable
- m_szDescription
- m_nDataType
- m_nScale
- COLUMN_GUID
- CHARACTER_MAXIMUM_LENGTH
- m_guidColumn
- CProcedureColumnInfo parameter class
ms.assetid: c82626c4-8047-4b9c-b342-e35bf37b7611
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 79b782a97ac96f54d951836662b69d06e097123c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="cprocedurecolumns-cprocedurecolumninfo"></a>CProcedureColumns、CProcedureColumnInfo
Typedef クラスを呼び出す**CProcedureColumns**そのパラメーター クラスを実装する**CProcedureColumnInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、プロシージャによって返される行セットの列に関する情報を返します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[PROCEDURE_COLUMNS 行セット](https://msdn.microsoft.com/en-us/library/ms723092.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szCatalog|PROCEDURE_CATALOG|  
|m_szSchema|PROCEDURE_SCHEMA|  
|m_szName|PROCEDURE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_nRowsetNumber|ROWSET_NUMBER|  
|m_nOrdinalPosition|ORDINAL_POSITION|  
|m_bIsNullable|IS_NULLABLE|  
|m_nDataType|DATA_TYPE|  
|m_guidType|TYPE_GUID|  
|m_nMaxLength|CHARACTER_MAXIMUM_LENGTH|  
|m_nOctetLength|CHARACTER_OCTET_LENGTH|  
|m_nPrecision|NUMERIC_PRECISION|  
|m_nScale|NUMERIC_SCALE|  
|m_szDescription|説明|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)