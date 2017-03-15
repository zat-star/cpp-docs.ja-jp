---
title: "CDataConnection クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataConnection"
  - "ATL.CDataConnection"
  - "CDataConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataConnection クラス"
ms.assetid: 77432d85-4e20-49ec-a0b0-142137828471
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# CDataConnection クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソースの接続を管理します。  
  
## 構文  
  
```  
class CDataConnection  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CDataConnection](../../data/oledb/cdataconnection-cdataconnection.md)|コンストラクターです。  `CDataConnection` オブジェクトをインスタンス化し、初期化します。|  
|[&#91;Copy&#93;](../../data/oledb/cdataconnection-copy.md)|既存のデータ接続のコピーを作成します。|  
|[&#91;Open&#93;](../../data/oledb/cdataconnection-open.md)|初期化文字列を使用してデータ ソースへの接続を開きます。|  
|[OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)|現在の接続の新しいセッションが開きます。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)|現在のセッションが開いているかどうかを判定します。|  
|[operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)|現在のセッションが開いているかどうかを判定します。|  
|[CDataSource 演算子&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)|`CDataSource` に含まれるオブジェクトへの参照を返します。|  
|[CDataSource\* 演算子](../Topic/CDataConnection::operator%20CDataSource*.md)|`CDataSource` に含まれるオブジェクトへのポインターを返します。|  
|[CSession 演算子&](../../data/oledb/cdataconnection-operator-csession-amp.md)|`CSession` に含まれるオブジェクトへの参照を返します。|  
|[CSession\* 演算子](../../data/oledb/cdataconnection-operator-csession-star.md)|`CSession` に含まれるオブジェクトへのポインターを返します。|  
  
## 解説  
 `CDataConnection` は 必要なオブジェクト \(データ ソースとセッション\)、それをする必要がある作業をカプセル化するので、クライアントを作成するための便利なクラスは、データ ソースに接続する場合  
  
 `CDataConnection`なしで、`CDataSource` オブジェクトを作成し、[CSession](../../data/oledb/csession-class.md) オブジェクトのインスタンスを呼び出し、[CCommand](../../data/oledb/ccommand-class.md) オブジェクトを作成するに [開く](../../data/oledb/csession-open.md) のメソッドを作成するに [OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md) のメソッドを、および呼び出し、**開く**\*にメソッドを呼び出す必要があります。  
  
 `CDataConnection`によって、接続オブジェクトを作成する必要があります。これに初期化文字列を渡しましたり、開くコマンドにより、その接続を使用します。  データベースへの接続を繰り返し使用することを計画している場合は、接続を開始することをお勧め `CDataConnection` であり、この方法が便利な方法を提供します。  
  
> [!NOTE]
>  複数のセッションを処理する必要があるデータベース アプリケーションを作成する [OpenNewSession](../../data/oledb/cdataconnection-opennewsession.md)を使用する必要があります。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)