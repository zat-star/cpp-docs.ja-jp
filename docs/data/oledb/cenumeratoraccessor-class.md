---
title: "CEnumeratorAccessor クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CEnumeratorAccessor"
  - "CEnumeratorAccessor"
  - "ATL.CEnumeratorAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumeratorAccessor クラス"
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CEnumeratorAccessor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

列挙子の行セットからデータにアクセスするために [CEnumerator](../../data/oledb/cenumerator-class.md) に使用されます。  
  
## 構文  
  
```  
class CEnumeratorAccessor  
```  
  
## メンバー  
  
### データ メンバー  
  
|||  
|-|-|  
|[m\_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|行が列挙子は、列挙子が親列挙子であるかどうかを示す変数。|  
|[m\_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|行をデータ ソースまたは列挙子を表すかどうかを示す変数。|  
|[m\_szDescription](../Topic/CEnumeratorAccessor::m_szDescription.md)|データ ソースまたは列挙子の説明。|  
|[m\_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|データ ソースまたは列挙子の名前。|  
|[m\_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|データ ソースまたは列挙子のモニカーを取得するに [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) に渡す文字列。|  
  
## 解説  
 この行セットは現在の列挙子で表示されるデータ ソースと列挙子で構成されます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)