---
title: "CEnumerator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CEnumerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumerator クラス"
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CEnumerator クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

すべてのデータ ソースと列挙子を説明する行セットを返すように [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) インターフェイスを公開する OLE DB 列挙子オブジェクトを使用します。  
  
## 構文  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[&#91;検索&#93;](../Topic/CEnumerator::Find.md)|指定した名前の 1 を検索します。使用できるプロバイダー \(データ ソース\) を検索します。|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|現在のレコードの `IMoniker` インターフェイスを取得します。|  
|[&#91;Open&#93;](../Topic/CEnumerator::Open.md)|列挙子を開きます。|  
  
## 解説  
 このクラスから **ISourcesRowset** データを間接的に取得できます。  
  
## 必要条件  
 **ヘッダー:**atldbcli.h  
  
## 参照  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)