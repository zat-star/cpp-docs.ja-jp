---
title: "OLE DB アーキテクチャのデザインの問題 | Microsoft Docs"
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
  - "OLE DB, アプリケーション デザインの考慮事項"
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# OLE DB アーキテクチャのデザインの問題
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB アプリケーションの作成を開始する前に、以下の問題について検討する必要があります。  
  
 **OLE DB アプリケーションの作成に使用するプログラミング実装**  
 Microsoft には、実装に使用できるいくつかのライブラリ \(OLE DB テンプレート ライブラリ、OLE DB 属性、および OLE DB SDK の生の OLE DB インターフェイス\) が用意されています。  また、プログラムの作成に役立つウィザードもあります。  これらの実装については、「[OLE DB テンプレート、属性、およびその他の実装](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md)」で説明されています。  
  
 **独自のプロバイダーを作成する必要があるかどうか**  
 ほとんどの開発者は、独自のプロバイダーを作成する必要がありません。  Microsoft が複数のプロバイダーを用意しています。  データ接続を作成するたび \(たとえば、ATL OLE DB コンシューマー ウィザードを使用してプロジェクトにコンシューマーを追加するとき\) に、システムに登録されているすべての使用可能なプロバイダーが **\[データ リンク プロパティ\]** ダイアログ ボックスに一覧表示されます。  これらのプロバイダーのうち、データ ストアとデータ アクセス アプリケーションに適しているプロバイダーがあれば、そのプロバイダーを使用するのが最も簡単です。  ただし、データ ストアがこれらのカテゴリのいずれにも適さない場合は、独自のプロバイダーを作成する必要があります。  プロバイダーの作成の詳細については、「[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)」を参照してください。  
  
 **コンシューマーに必要なサポートのレベル**  
 コンシューマーには、きわめて基本的なものもあれば複雑なものもあります。  OLE DB オブジェクトの機能は、プロパティによって指定されます。  ATL OLE DB コンシューマー ウィザードを使用してコンシューマーを作成するとき、または、データベース プロバイダー ウィザードを使用してプロバイダーを作成するときに、これらのウィザードで、機能の標準セットを提供するために適切なオブジェクト プロパティが設定されます。  ただし、ウィザードで生成されたコンシューマー クラスまたはプロバイダー クラスで必要な機能の一部がサポートされない場合は、[OLE DB テンプレート ライブラリ](../Topic/OLE%20DB%20Templates.md)でこれらのクラスのインターフェイスを参照する必要があります。  これらのインターフェイスは、生の OLE DB インターフェイスをラップし、使いやすくするための特別な実装を提供します。  
  
 たとえば、行セットのデータを更新する必要があるのに、ウィザードでコンシューマーを作成したときにこの機能を指定していなかった場合は、コマンド オブジェクトで **DBPROP\_IRowsetChange** プロパティと **DBPROP\_UPDATABILITY** プロパティを設定することによって後から機能を指定できます。  この場合、行セットが作成されたときに、その行セットは `IRowsetChange` インターフェイスを持ちます。  
  
 **Do you have older code using another data access technology \(ADO, ODBC, or DAO\)?**  
 考えられるテクノロジの組み合わせ \(ADO コンポーネントと OLE DB コンポーネントを組み合わせて使用する、ODBC コードを OLE DB に移行するなど\) について、あらゆる状況を説明することは、Visual C\+\+ のドキュメントの範囲外です。  ただし、さまざまなシナリオについて説明している多くの項目を以下の Microsoft の Web サイトで参照できます。  
  
-   [Microsoft ヘルプとサポート](http://go.microsoft.com/fwlink/?LinkId=148218)  
  
-   [Microsoft Data Access の技術文書の概要](http://go.microsoft.com/fwlink/?LinkId=148217)  
  
-   [Visual Studio ソリューションのセンター](http://go.microsoft.com/fwlink/?LinkId=148215)  
  
-   [検索 Microsoft.com](http://search.microsoft.com/)  
  
 検索を実行するときは、シナリオに最も適したキーワードの組み合わせを入力します。たとえば、ADO オブジェクトを OLE DB プロバイダーと共に使用している場合は、「**ADO AND "OLE DB"**」と指定してブール検索を試します。  ODBC に古い DAO コードを移行する場合は、「すべての単語」を選択します **migrating DAO**などの文字列を指定します。  
  
## 参照  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)