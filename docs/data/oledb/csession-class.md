---
title: "CSession クラス | Microsoft Docs"
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
  - "CSession"
  - "ATL::CSession"
  - "ATL.CSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession クラス"
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一つのデータベース アクセス セッションを表します。  
  
## 構文  
  
```  
class CSession  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[&#91;中止&#93;](../Topic/CSession::Abort.md)|\(\-\-\) トランザクションを取り消します。|  
|[&#91;閉じる&#93;](../../data/oledb/csession-close.md)|セッションを終了します。|  
|[&#91;確定&#93;](../../data/oledb/csession-commit.md)|トランザクションをコミットします。|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|トランザクションに関する情報を返します。|  
|[&#91;Open&#93;](../../data/oledb/csession-open.md)|データ ソース オブジェクトの新しいセッションが開きます。|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|このセッションの新しいトランザクションを開始します。|  
  
## 解説  
 一つ以上のセッションを [CDataSource](../Topic/CDataSource%20Class.md) オブジェクトによって表される各プロバイダー コネクション \(データ ソース\) に関連付けることができます。  `CDataSource`の新しい `CSession` を作成するには、[CSession::Open](../../data/oledb/csession-open.md)を呼び出します。  データベース トランザクションを開始するには、`CSession` は `StartTransaction` のメソッドを提供します。  トランザクションを開始した場合、**コミット** のメソッドを使用してそのファイルにコミットしたり、**中止** のメソッドを使用してこれをキャンセルします。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CatDB サンプル : データ ソース スキーマ ブラウザー](../../top/visual-cpp-samples.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)