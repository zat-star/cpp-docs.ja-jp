---
title: "ATL データベース クラス (OLE DB テンプレート) | Microsoft Docs"
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
  - "データベース クラス [C++], ATL"
  - "データベース クラス [C++], OLE DB"
  - "OLE DB テンプレート [C++], ATL データベース クラス"
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# ATL データベース クラス (OLE DB テンプレート)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft には、OLE DB のいくつかの実装が用意されています。OLE DB は、各種の情報源にさまざまな形式で格納されているデータに同じ方法でアクセスできる、COM インターフェイスのセットです。  
  
 OLE DB テンプレートは ATL の C\+\+ テンプレートであり、一般に使用されている多くの OLE DB インターフェイスを実装するクラスを提供することで、パフォーマンスの高い OLE DB データベース テクノロジを使いやすくしています。  
  
 このテンプレート ライブラリは 2 つの部分から構成されます。  
  
-   [OLE DB コンシューマー テンプレート](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB クライアント \(コンシューマー\) アプリケーションの実装に使用します。  
  
-   [OLE DB プロバイダー テンプレート](../data/oledb/ole-db-provider-templates-cpp.md) OLE DB サーバー \(プロバイダー\) アプリケーションの実装に使用します。  
  
 また、[OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)には、OLE DB コンシューマーを簡単に作成する方法が用意されています。  OLE DB 属性は、OLE DB コンシューマー テンプレートに基づいてコードを挿入し、OLE DB コンシューマーを作成します。  
  
 MFC ライブラリには、データベース レコードをコントロールに表示する [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) という 1 つのクラスが含まれています。  ビューは、`CRowset` オブジェクトに直接接続されるフォーム ビューであり、`CRowset` オブジェクトのフィールドをダイアログ テンプレートのコントロールに表示します。  
  
 詳細については、[OLE DB のプログラミング](../data/oledb/ole-db-programming.md) を参照します [OLE DB Programmer's Guide の](http://go.microsoft.com/fwlink/?LinkId=121548)。  
  
## 参照  
 [OLE DB コンシューマーの作成](../data/oledb/creating-an-ole-db-consumer.md)   
 [OLE DB プロバイダーの作成](../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB プロバイダー テンプレート リファレンス](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB Templates Samples](http://msdn.microsoft.com/ja-jp/08958863-0b5f-41ad-ae99-fca7440c553c)