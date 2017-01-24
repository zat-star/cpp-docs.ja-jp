---
title: "DAO と ODBC の使い分け | Microsoft Docs"
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
  - "DAO [C++], および ODBC"
  - "データベース クラス [C++], DAO"
  - "データベース クラス [C++], ODBC"
  - "ODBC [C++], および DAO"
ms.assetid: 9f67613f-0056-4ece-8c3a-9872e9563d57
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO と ODBC の使い分け
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Visual C\+\+ .NET では、Visual C\+\+ 開発環境およびウィザードでは DAO はサポートされなくなりました \(DAO クラスは含まれているので、このクラスを使うことはできます\)。  新規プロジェクトの作成には、\[OLE DB テンプレート\] または \[ODBC\] の使用をお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用してください。  
  
 DAO と ODBC のどちらの MFC クラスを使うかは、ニーズに応じて異なります。  
  
-   ODBC クラスは、ODBC データ ソースだけを使う場合に適しています。特に、MFC ODBC によってパフォーマンスが向上するクライアント サーバー環境で使います。  
  
-   DAO クラスは、主に Microsoft Jet \(.mdb\) データベース、または Microsoft Jet データベース エンジンで直接読み込むことができる他のデータベース形式を使用する場合に使用します。  これらのデータベース形式については、「[DAO と ODBC を使ってアクセスできるデータ ソース](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)」を参照してください。  
  
-   Microsoft Jet データベース エンジンの速度を上げたり、DAO クラスの付加機能を使用したりするには、DAO クラスを経由して ODBC データ ソースにアクセスします。  
  
    > [!NOTE]
    >  DAO を使用する場合は、ハード ディスクの容量を増やす必要があります。  
  
 DAO クラスには、以下の利点があります。  
  
-   主に Microsoft Jet \(.mdb\) データベースを使用する場合などにパフォーマンスが優れている。  
  
-   ODBC クラス、Microsoft Access Basic、Microsoft Visual Basic との互換性がある。  
  
-   検証規則にアクセスできる。  
  
-   テーブル間の関係を指定できる。  
  
-   データ アクセス モデルがより充実している。たとえば、DAO クラスはデータ定義言語 \(DDL: Data Definition Language\) やデータ操作言語 \(DML: Data Manipulation Language\) をサポートしています。  詳細については、「[DDL および DML のサポート](../Topic/Are%20DDL%20and%20DML%20Supported?.md)」を参照してください。  
  
 主な相違点を次の表に示します。この表に基づいてクラスを選択してください。  
  
### MFC の DAO クラスと ODBC クラスの使い分け  
  
|項目|DAO クラスの場合|ODBC クラスの場合|  
|--------|----------------|-----------------|  
|.MDB ファイルにアクセスする|Yes|Yes|  
|ODBC データ ソースにアクセスする|Yes|Yes|  
|16 ビットで使用できる|No|Yes|  
|32 ビットで使用できる|Yes|Yes|  
|64 ビットで使用できる|No|Yes|  
|データベースの圧縮|Yes|No|  
|データベース エンジンのサポート|Microsoft Jet データベース エンジン|対象の DBMS|  
|DDL サポート|Yes|ODBC を直接呼び出す場合だけ可|  
|DML サポート|Yes|Yes|  
|MFC への実装形態|DAO コア関数の "ラップ" クラス|ODBC API の "ラップ" ではなく、簡略化された抽象クラス|  
|最適な用途|.MDB ファイル \(Microsoft Access\)|対応するドライバーがある DBMS \(クライアント サーバー状況内を主とする\)|  
|トランザクションのサポート|ソリューション単位 \(ODBC データの場合はデータベース単位\)|データベース単位|  
  
 なお、ODBC ドライバーの機能はそれぞれ異なることを忘れないでください。  詳細については、『ODBC Programmer's Reference』と各 ODBC ドライバーのヘルプ ファイルを参照してください。  
  
## 参照  
 [よく寄せられる質問 \- データ アクセス](../data/data-access-frequently-asked-questions-mfc-data-access.md)