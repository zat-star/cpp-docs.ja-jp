---
title: "データ アクセス プログラミング (MFC/ATL) | Microsoft Docs"
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
  - "データ [C++], データ アクセス テクノロジ"
  - "データ アクセス [C++], クラス ライブラリ (データベース用)"
  - "データベース [C++], MFC"
  - "MFC [C++], データ アクセス アプリケーション"
  - "OLE DB [C++], データ アクセス テクノロジ"
ms.assetid: def97b2c-b5a6-445f-afeb-308050fd4852
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# データ アクセス プログラミング (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、さまざまな方法でデータベースにアクセスできます。  データ アクセス プログラミングには、データベース API での処理が簡単になるように、ATL \(Active Template Class Library\)、MFC \(Microsoft Foundation Class\) ライブラリなどのクラス ライブラリの 1 つを使用することをお勧めします。  
  
> [!NOTE]
>  このトピックでは、Visual C\+\+ でのデータベース プログラミングに使用できる以前のテクノロジについて説明します。  Visual C\+\+ および SQL Server 2005 を使用したデータ アクセス プログラミングについては、「[データ アクセス](../dotnet/data-access-using-adonet-cpp-cli.md)」、「[Visual Studio でのデータへのアクセス](../Topic/Accessing%20data%20in%20Visual%20Studio.md)」、および「[Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ja-jp/5358a825-e19b-49aa-8214-674ce5fed1da)」を参照してください。  
  
 ライブラリ クラスでは以下の種類のデータ アクセスをサポートします。  
  
-   ATL に用意されている OLE DB テンプレートとデータベース属性  
  
-   MFC に用意されているオープン データベース コネクティビティ \(ODBC: Open Database Connectivity\) と ODBC ドライバー  
  
 これらのライブラリは、データベースの使い方を簡略化するための抽象化をサポートしており、C\+\+ のスピード、パワー、柔軟性を完備しています。  いずれの方法も、データにアクセスする作業をライブラリのアプリケーション フレームワークに統合しています。  
  
 また、データベースの API 関数は、COM、ODBC、または DAO の SDK \(Software Development Kit\) から直接呼び出すこともできます。  COM、DAO、または ODBC の API 関数を直接使用するプログラミングについては、COM SDK、DAO SDK、または ODBC SDK を参照してください。  
  
 データの格納形式に関係なく、データにアクセスする必要がある場合は、ATL OLE DB を使用します。  Microsoft Jet \(.mdb\) データベースを使用しておらず、データ ソースを完全に切り離して独立のものとして使用するために ODBC API を操作するには、MFC ODBC クラスを使用します。  Microsoft Jet \(.mdb\) データベースまたは外部データベース \(ODBC データ ソースなど\) を操作する場合は、MFC DAO クラスを使用します。  
  
> [!NOTE]
>  Microsoft は、新しいプロジェクトには OLE DB または ODBC を使用することをお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用します。  
  
 データベース機能は、スタンドアロンのアプリケーションとして記述するだけでなく、さまざまなプログラムでデータの格納\/再抽出のための機構として有効に活用できます。  
  
|詳細情報|参照トピック|  
|----------|------------|  
|**データベース テクノロジの選択**||  
|ODBC と   DAO|[DAO と ODBC の使い分け](../data/should-i-use-dao-or-odbc-q.md)|  
|製品サポート技術者が記述したデータベース トピックの追加項目を検索するための Microsoft サポート技術情報の使用方法|[データベース トピックに関する Microsoft サポート技術情報の項目の検索](../data/where-can-i-find-microsoft-knowledge-base-articles-on-database-topics-q.md)|  
|**ATL データベース サポート \(OLE DB\)**||  
|OLE DB プログラミング \(概念説明のトピック\)|[OLE DB プログラミングの概要](../data/oledb/ole-db-programming-overview.md)|  
|OLE DB コンシューマー テンプレートの使用方法 \(概念説明のトピック\)|[OLE DB コンシューマー テンプレート](../data/oledb/ole-db-consumer-templates-cpp.md)|  
|OLE DB コンシューマー属性|[OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)|  
|OLE DB プロバイダー テンプレートの使用方法 \(概念説明のトピック\)|[OLE DB プロバイダー テンプレート](../data/oledb/ole-db-provider-templates-cpp.md)|  
|MFC プロジェクトへの OLE DB コンシューマーの追加|[OLE DB コンシューマーの作成](../data/oledb/creating-an-ole-db-consumer.md)|  
|**MFC データベース サポート \(ODBC と DAO\)**||  
|DAO と ODBC について|[DAO と ODBC の相違](../data/what-are-dao-and-odbc-q.md)|  
|MFC データベース クラスをいつ使用するか|[データベース クラスを使う場面](../data/when-should-i-use-the-database-classes-q.md)|  
|MFC データベース プログラミング モデルについて学ぶには|[MFC データベースのプログラミング モデル](../data/what-is-the-mfc-database-programming-model-q.md)|  
|MFC DAO クラスと MFC ODBC クラスを使い分けるには|[DAO と ODBC の使い分け](../data/should-i-use-dao-or-odbc-q.md)|  
|DAO と ODBC を使ってアクセスできるデータ ソース|[DAO と ODBC を使ってアクセスできるデータ ソース](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)|  
|ODBC \(Open Database Connectivity\)|[ODBC と MFC](../data/odbc/odbc-and-mfc.md)|  
|クラス使用時の DAO または ODBC API を直接呼び出し|[DAO または ODBC の直接呼び出し](../data/can-i-call-dao-or-odbc-directly-q.md)|  
|提供される ODBC ドライバーの種類|[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)|  
|データベース クラスが MFC のドキュメント\/ビュー アーキテクチャを利用する方法|[MFC : ドキュメントとビューを用いたデータベース クラスの使用](../data/mfc-using-database-classes-with-documents-and-views.md)|  
|MFC データベース サポートのインストール。Visual C\+\+ に既定でインストールされる ODBC ドライバー。インストールされる ODBC および DAO SDK コンポーネント|[MFC データベース サポートのインストール](../data/installing-mfc-database-support.md)|  
|**データ バインディング コントロール \(ADO および RDO\)**||  
|データ バインディング コントロールを使用するプログラムの書き方|[データ バインディング コントロール \(ADO および RDO\)](../Topic/Data-Bound%20Controls%20\(ADO%20and%20RDO\).md)|  
|ActiveX コントロールを使用したデータ バインディング|[MFC ActiveX コントロール : ActiveX コントロールにおけるデータ バインディングの使用](../mfc/mfc-activex-controls-using-data-binding-in-an-activex-control.md)|  
|ActiveX コントロールの配布|[MFC ActiveX コントロール : ActiveX コントロールの配布](../mfc/mfc-activex-controls-distributing-activex-controls.md)|  
  
## 参照  
 [データ アクセス](../Topic/Data%20Access%20in%20Visual%20C++.md)