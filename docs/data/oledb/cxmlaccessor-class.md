---
title: "CXMLAccessor クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CXMLAccessor"
  - "CXMLAccessor"
  - "ATL.CXMLAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CXMLAccessor クラス"
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CXMLAccessor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ストアのスキーマ \(基になる構造\) が不明な場合には、文字列データとしてデータ ソースにアクセスできます。  
  
## 構文  
  
```  
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[GetXMLColumnData](../Topic/CXMLAccessor::GetXMLColumnData.md)|列情報を取得します。|  
|[GetXMLRowData](../Topic/CXMLAccessor::GetXMLRowData.md)|行には、テーブルの内容を取得します。|  
  
## 解説  
 ただし、`CXMLAccessor` は `CDynamicStringAccessorW` と XML 形式 \(番号付き\) データとしてデータ ストアからアクセスされるすべてのデータを変換することです。  つまり、XML 対応の Web ページの出力に適しています。  XML タグ名は、データ ストアの列名にできるだけ近いします。  
  
 列情報を取得するには `CDynamicAccessor` メソッドを使用します。  この列の情報は、実行時にアクセサーを動的に作成するときに使用します。  
  
 列情報は、このクラスによって作成および管理されるバッファーに格納されます。  列情報を [GetXMLColumnData](../Topic/CXMLAccessor::GetXMLColumnData.md) を使用して取得または行によって [GetXMLRowData](../Topic/CXMLAccessor::GetXMLRowData.md)を使用して列のデータを取得します。  
  
## 使用例  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/CPP/cxmlaccessor-class_1.cpp)]  
  
## 必要条件  
 **ヘッダー**: atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../Topic/CAccessor%20Class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA クラス](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW クラス](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor クラス](../Topic/CManualAccessor%20Class.md)