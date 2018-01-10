---
title: "CTableConstraints、CTableConstraintInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szTableSchema
- CONSTRAINT_TYPE
- m_szCatalog
- CTableConstraints
- m_bInitiallyDeferred
- CONSTRAINT_NAME
- m_szTableCatalog
- m_szType
- m_szSchema
- INITIALLY_DEFERRED
- CTableConstraintInfo
- m_szTableName
- m_bIsDeferrable
- m_szName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- IS_DEFERRABLE
dev_langs: C++
helpviewer_keywords:
- DESCRIPTION class data member
- CTableConstraints typedef class
- IS_DEFERRABLE
- m_szSchema
- m_bInitiallyDeferred
- CONSTRAINT_CATALOG
- m_szTableSchema
- TABLE_CATALOG
- m_szType
- m_szCatalog
- TABLE_NAME
- CONSTRAINT_NAME
- CONSTRAINT_TYPE
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szName
- m_szTableCatalog
- m_szDescription
- CTableConstraintInfo parameter class
- m_szTableName
- INITIALLY_DEFERRED
- m_bIsDeferrable
ms.assetid: aaa07ade-0bfa-41d0-94df-8342152a4ff0
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 12645df8ba7bf53d562b91917e85797681120f86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ctableconstraints-ctableconstraintinfo"></a>CTableConstraints、CTableConstraintInfo
Typedef クラスを呼び出す**CTableConstraints**そのパラメーター クラスを実装する**CTableConstraintInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、テーブルの制約をカタログで定義されている特定のユーザーによって所有されているを識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[TABLE_CONSTRAINTS 行セット](https://msdn.microsoft.com/en-us/library/ms715921.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szType|CONSTRAINT_TYPE|  
|m_bIsDeferrable|IS_DEFERRABLE|  
|m_bInitiallyDeferred|INITIALLY_DEFERRED|  
|m_szDescription|説明|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)