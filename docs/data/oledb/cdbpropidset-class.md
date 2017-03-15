---
title: "CDBPropIDSet クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropIDSet"
  - "ATL.CDBPropIDSet"
  - "ATL::CDBPropIDSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropIDSet クラス"
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDBPropIDSet クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**DBPROPIDSET** 構造体から継承し、キー フィールド、または [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) のアクセス方法を初期化するコンストラクターを追加します。  
  
## 構文  
  
```  
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|プロパティ ID を設定するプロパティを追加します。|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|コンストラクターです。|  
|[SetGUID](../Topic/CDBPropIDSet::SetGUID.md)|ID プロパティ設定の GUID を設定します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../../data/oledb/cdbpropidset-operator-equal.md)|別の要素に設定される 1 種類のプロパティ ID に割り当てます。|  
  
## 解説  
 OLE DB コンシューマーは、コンシューマーがプロパティ情報を取得する必要があるプロパティの ID の配列を渡すために **DBPROPIDSET** 構造を使用します。  [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) の単一の構造で識別されるプロパティは、1 種類のプロパティ セットに属しています。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)