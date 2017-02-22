---
title: "データベース サポートのインストール (MFC/ATL) | Microsoft Docs"
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
  - "ATL [C++], データベースのサポート"
  - "データ アクセス [C++], インストール (データベース サポートを)"
  - "データベース [C++], インストール (データベース サポートを)"
  - "インストール (データベース サポートを)"
ms.assetid: 3820ba96-4fb8-4405-83dd-bb3bc5998667
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# データベース サポートのインストール (MFC/ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ .NET のセットアップを実行すると、次のデータベース コンポーネントが自動的にインストールされます。  
  
-   すべての必要な ATL OLE DB コンポーネント。  詳細については、「[ATL データベース サポートのインストール](../data/installing-atl-database-support.md)」を参照してください。  
  
-   ODBC ドライバー マネージャーおよび ODBC 管理者プログラムを含む、一連の ODBC ドライバー。  詳細については、「[MFC データベース サポートのインストール](../data/installing-mfc-database-support.md)」で「ODBC ドライバーのインストール」および「ODBC SDK コンポーネントのインストール」を参照してください。  
  
-   DAO ソフトウェア開発キット \(SDK\) の必要なコンポーネント。  これにはヘルプ ファイルが含まれますが、このドキュメントにヘルプ ファイルは同梱されていません。  ただし、DAO を使用する場合は、オペレーティング システムと互換性のあるバージョンの Jet をインストールする必要があります。  詳細については、「[MFC データベース サポートのインストール](../data/installing-mfc-database-support.md)」で「DAO SDK コンポーネントのインストール」を参照してください。  
  
 ベースライン インストールの一部として、セットアップでは Microsoft Data Access Components \(MDAC\) もインストールされます。MDAC は、Visual C\+\+ .NET でのデータ アクセス プログラミングをサポートするために必要です。  
  
 Visual C\+\+ .NET では、MDAC 2.7 SDK がインストールされます。  MDAC SDK の更新とニュースについては、Microsoft Universal Data Access の Web サイト \([http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548)\) を参照してください。  
  
 データ アクセス アプリケーションを再配布する場合は、MDAC 2.7 再配布プログラムも必要です。  MDAC 2.7 SDK は、Visual Studio .NET Prerequisites CD\-ROM の MDAC ディレクトリに含まれている MDAC 2.7 再配布プログラム \(Mdac\_typ.exe\) と共に使用するために設計されています。  前述の MDAC 2.7 SDK のダウンロード リンクから Mdac\_typ.exe をダウンロードすることもできます。  コンポーネントの再配布の詳細については、「[コントロールを再配布する](../Topic/Redistributing%20Controls.md)」を参照してください。  
  
## 参照  
 [データ アクセス](../Topic/Data%20Access%20in%20Visual%20C++.md)