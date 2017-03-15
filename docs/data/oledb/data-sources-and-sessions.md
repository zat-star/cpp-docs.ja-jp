---
title: "データ ソースとセッション | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "接続 [C++], データ ソース"
  - "データ ソース [C++], OLE DB"
  - "OLE DB コンシューマー テンプレート (C++), データ ソース"
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# データ ソースとセッション
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の図は、データ ソースとの接続とデータ ソースへのアクセスをサポートするクラスを示します。  各クラスは、標準の OLE DB コンポーネントの実装に基づいています。  
  
 ![データ ソースとセッション クラス](../../data/oledb/media/vcdatasourcesessionclasses.png "vcDataSourceSessionClasses")  
データ ソース クラスとセッション クラス  
  
 次のクラスがあります。  
  
-   [CDataSource](../Topic/CDataSource%20Class.md) このクラスはデータ ソース オブジェクトをインスタンス化し、OLE DB プロバイダーを通じたデータ ソースとの接続を作成および管理します。  データ ソースは、データ ソース アドレスや認証情報などの情報を接続文字列の形式で受け取ります。  
  
     システムに登録されている使用可能なプロバイダーの一覧を取得するために、接続の確立前にヘルパー クラスの [CEnumerator](../../data/oledb/cenumerator-class.md) を使用する場合もあります。  これにより、プロバイダーをデータ ソースとして選択できます。  たとえば、**\[データ リンク プロパティ\]** ダイアログ ボックスでは、このクラスを使用して、\[プロバイダー\] タブにプロバイダーの一覧を作成します。  これは、**SQLBrowseConnect** 関数または **SQLDriverConnect** 関数と等価です。  
  
-   [CSession](../../data/oledb/csession-class.md) このクラスは、データ ソースへの単一アクセス セッションを表すセッション オブジェクトをインスタンス化します。  ただし、1 つのデータ ソースに複数のセッションを作成できます。  各セッションに対して、行セット、コマンド、およびその他のオブジェクトを作成し、データ ソースのデータにアクセスできます。  セッションはトランザクションを処理します。  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)