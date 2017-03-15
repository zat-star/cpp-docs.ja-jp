---
title: "CArrayRowset クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CArrayRowset<TAccessor>"
  - "ATL.CArrayRowset"
  - "CArrayRowset"
  - "ATL::CArrayRowset"
  - "ATL::CArrayRowset<TAccessor>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArrayRowset クラス"
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CArrayRowset クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

配列の構文を使用して、行セットの要素にアクセスします。  
  
## 構文  
  
```  
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
#### パラメーター  
 `TAccessor`  
 これを使用して、行セットにするアクセサー クラスの型。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CArrayRowset](../../data/oledb/carrayrowset-carrayrowset.md)|コンストラクターです。|  
|[&#91;スナップショット&#93;](../../data/oledb/carrayrowset-snapshot.md)|メモリに行全体の設定を読み込みます。|  
  
### 演算子  
  
|||  
|-|-|  
|[&#91;&#93;演算子&#93;](../Topic/CArrayRowset::operator.md)|行セットの要素にアクセスします。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[CArrayRowset::m\_nRowsRead](../../data/oledb/carrayrowset-m-nrowsread.md)|既に読み込んだ行数。|  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset クラス](../Topic/CRowset%20Class.md)