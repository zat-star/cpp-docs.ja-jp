---
title: "CCheckConstraints、CCheckConstraintInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCheckConstraintInfo
- CHECK_CONSTRAINTS
- m_szCatalog
- CCheckConstraints
- CONSTRAINT_NAME
- m_szSchema
- CHECK_CLAUSE
- m_szCheckClause
- m_szName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
dev_langs: C++
helpviewer_keywords:
- DESCRIPTION class data member
- m_szSchema
- CONSTRAINT_CATALOG
- m_szCatalog
- CONSTRAINT_NAME
- CONSTRAINT_SCHEMA
- CCheckConstraints typedef class
- CHECK_CLAUSE
- m_szName
- m_szDescription
- CCheckConstraintInfo parameter class
- m_szCheckClause
- CHECK_CONSTRAINTS
ms.assetid: e53e79a5-01e5-42b7-aa8c-164aec94b011
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0741db31ba0b509a1ed2788bace5d99f8eed4faf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccheckconstraints-ccheckconstraintinfo"></a>CCheckConstraints、CCheckConstraintInfo
Typedef クラスを呼び出す**CCheckConstraints**そのパラメーター クラスを実装する**CCheckConstraintInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、check 制約、カタログで定義されている特定のユーザーによって所有されているを識別します。 Check 制約は、データ値またはテーブル内の 1 つまたは複数の列で許容される形式を指定します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[CHECK_CONSTRAINTS 行セット](https://msdn.microsoft.com/en-us/library/ms712845.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szCheckClause|CHECK_CLAUSE|  
|m_szDescription|説明|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>参照  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)