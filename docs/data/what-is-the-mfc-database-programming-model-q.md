---
title: "MFC データベースのプログラミング モデル | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], MFC"
  - "データ アクセス [C++], テクノロジ"
  - "データベース [C++], MFC"
  - "MFC [C++], データベース アプリケーション"
  - "ODBC [C++], MFC"
  - "ODBC クラス [C++], MFC データベース クラス"
ms.assetid: f6f15bb8-4115-41f2-ad68-036e74a11bd9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC データベースのプログラミング モデル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC による DAO と ODBC の実装は根本的にかなり異なっていますが、この 2 つのインターフェイスはよく似ています。したがって、アプリケーションの移植、特に ODBC から DAO への移植は、比較的簡単です。  ODBC から DAO への移植については、「[テクニカル ノート 55: MFC ODBC データベース クラス アプリケーションの MFC DAO クラスへの移行](../Topic/TN055:%20Migrating%20MFC%20ODBC%20Database%20Class%20Applications%20to%20MFC%20DAO%20Classes.md)」を参照してください。  MFC の DAO インターフェイスおよび ODBC インターフェイスは、Visual Basic のインターフェイスにもよく似ています。  
  
 MFC プログラミング モデルでは、開いているデータベースごとにデータベース オブジェクトを使います。  データベース オブジェクトは、データベースとの接続を表します。  クエリと更新は、レコードセット オブジェクトを使用して実行します。  DAO には、後で説明するように、テーブル構造体を使用したり、クエリを保存して再利用したりするためのオブジェクトも用意されています。  MFC は、これらの各オブジェクトに対してクラスを提供しています。DAO クラスと ODBC クラスは、別個に提供されています。  
  
 MFC を使用すると、データ アクセスが簡単になります。  DAO データベース クラスと ODBC データベース クラスは、高水準の抽象化を提供しているため、プログラマが DAO や ODBC を直接使う必要はありません。  MFC クラスを使うより、API へ書き込む方が複雑です。  特に、小型の比較的単純なアプリケーションを作成する場合は顕著です。  
  
 データベース クラスは、MFC クラス ライブラリに以下のコンポーネントを追加します。  
  
-   C\+\+ データベース クラス。DAO または ODBC を通じてデータベースにアクセスするための高水準 API を提供します。  
  
-   アプリケーション ウィザードおよびクラスの追加の拡張。アプリケーション固有のデータベース クラスを作成します。  
  
-   サンプル プログラム。クラスとウィザードの使用例です。  
  
-   オンライン ドキュメント。概要、プログラミングに関する記事、クラス リファレンスなどがあります。  
  
 これらのコンポーネントについては、「[ODBC と MFC](../data/odbc/odbc-and-mfc.md)」を参照してください。  
  
 詳細については、次のトピックを参照してください。  
  
-   [DAO と ODBC の使い分け](../data/should-i-use-dao-or-odbc-q.md)  
  
-   DAO および ODBC における [DDL および DML のサポート](../Topic/Are%20DDL%20and%20DML%20Supported?.md)  
  
-   [MFC データベース サポートのインストール](../data/installing-mfc-database-support.md)  
  
-   MFC の [ODBC](../data/odbc/odbc-and-mfc.md) クラス  
  
-   [MFC データベース ドキュメント](../data/mfc-database-documentation.md)  
  
-   [ODBC と MFC](../data/odbc/odbc-and-mfc.md)  
  
## 参照  
 [よく寄せられる質問 \- データ アクセス](../data/data-access-frequently-asked-questions-mfc-data-access.md)