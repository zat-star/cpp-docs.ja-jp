---
title: "CDynamicStringAccessor クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessor クラス"
ms.assetid: 138dc4de-c7c3-478c-863e-431e48249027
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース スキーマ \(データベースの基になる構造\) が不明な場合にデータ ソースにアクセスできます。  
  
## 構文  
  
```  
  
      template< typename BaseType, DBTYPEENUM OleDbType >  
class CDynamicStringAccessorT : public CDynamicAccessor  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[GetString](../Topic/CDynamicStringAccessor::GetString.md)|指定された列データを文字列として取得します。|  
|[SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)|文字列として指定された列データを設定します。|  
  
## 解説  
 [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) がプロバイダーによって報告されたネイティブな形式でデータを要求しますが、`CDynamicStringAccessor` はすべてのデータが文字列データとしてデータ ストアからアクセスされたプロバイダーのフェッチ要求します。  これは、特にデータ ストアのコンテンツの表示または印刷などのように、データ ストアの値の計算を要求しない単純なタスクで役に立ちます。  
  
 データ ストアの列データのネイティブ型は重要ではありません; プロバイダーがデータ変換をサポートできる場合は、文字列のデータを指定します。  プロバイダーがネイティブ データ型から \(共通\) 文字列への変換をサポートする、要求の呼び出しは成功値 **DB\_S\_ERRORSOCCURED**を返し、対応する列のステータスが **DBSTATUS\_E\_CANTCONVERTVALUE**と変換の問題を示します。  
  
 列情報を取得するには `CDynamicStringAccessor` メソッドを使用します。  この列の情報は、実行時にアクセサーを動的に作成するときに使用します。  
  
 列情報は、このクラスによって作成および管理されるバッファーに格納されます。  バッファーからデータを [GetString](../Topic/CDynamicStringAccessor::GetString.md)を使用して取得またはバッファーに [SetString](../../data/oledb/cdynamicstringaccessor-setstring.md)で保存します。  
  
 動的なアクセサー クラスを説明と使用例については、[動的なアクセサーを使用して](../../data/oledb/using-dynamic-accessors.md)を参照してください。  
  
## 必要条件  
 **ヘッダー**: atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor クラス](../Topic/CAccessor%20Class.md)   
 [CDynamicParameterAccessor クラス](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor クラス](../Topic/CManualAccessor%20Class.md)   
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessorA クラス](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW クラス](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CXMLAccessor クラス](../../data/oledb/cxmlaccessor-class.md)