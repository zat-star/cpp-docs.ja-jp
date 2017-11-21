---
title: "CCollations、CCollationInfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLLATION_CATALOG
- m_szCatalog
- CCollationInfo
- CCollations
- CHARACTER_SET_NAME
- CHARACTER_SET_SCHEMA
- m_szCharSetName
- m_szSchema
- CHARACTER_SET_CATALOG
- m_szCharSetSchema
- m_szCharSetCatalog
- m_szPadAttribute
- COLLATION_NAME
- COLLATION_SCHEMA
- m_szName
- COLLATIONS
dev_langs: C++
helpviewer_keywords:
- m_szSchema
- COLLATION_SCHEMA
- m_szCharSetCatalog
- m_szCatalog
- COLLATIONS recordset
- COLLATION_CATALOG
- CCollationInfo parameter class
- m_szName
- COLLATION_NAME
- m_szPadAttribute
- CHARACTER_SET_NAME
- m_szCharSetName
- CHARACTER_SET_SCHEMA
- CHARACTER_SET_CATALOG
- m_szCharSetSchema
- CCollations typedef class
ms.assetid: d8b43c4d-9dd5-4043-b4c8-38c03bfa0c72
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99bf8120d048298ca570ea4b318c7ae9c04da811
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ccollations-ccollationinfo"></a>CCollations、CCollationInfo
Typedef クラスを呼び出す**CCollations**そのパラメーター クラスを実装する**CCollationInfo**です。  
  
## <a name="remarks"></a>コメント  
 参照してください[スキーマ行セット クラスと Typedef クラス](../../data/oledb/schema-rowset-classes-and-typedef-classes.md)typedef クラスの使用に関する詳細についてはします。  
  
 このクラスは、文字の照合順序、カタログで定義されているが、特定のユーザー アクセスを識別します。  
  
 次の表には、クラスのデータ メンバーとその対応する OLE DB 列が一覧表示します。 参照してください[照合順序の行セット](https://msdn.microsoft.com/en-us/library/ms715783.aspx)で、 *OLE DB プログラマーズ リファレンス*スキーマと列の詳細についてはします。  
  
|データ メンバー|OLE DB 列|  
|------------------|--------------------|  
|m_szCatalog|COLLATION_CATALOG|  
|m_szSchema|COLLATION_SCHEMA|  
|m_szName|COLLATION_NAME|  
|m_szCharSetCatalog|CHARACTER_SET_CATALOG|  
|m_szCharSetSchema|CHARACTER_SET_SCHEMA|  
|m_szCharSetName|CHARACTER_SET_NAME|  
|m_szPadAttribute|PAD_ATTRIBUTE|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbsch.h  
  
## <a name="see-also"></a>関連項目  
 [CRestrictions クラス](../../data/oledb/crestrictions-class.md)