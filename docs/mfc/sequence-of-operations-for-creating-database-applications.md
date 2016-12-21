---
title: "データベース アプリケーションの作成手順 | Microsoft Docs"
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
  - "アプリケーション [MFC], データベース"
  - "データベース アプリケーション [C++]"
  - "データベース アプリケーション [C++], 作成"
  - "MFC [C++], データベース アプリケーション"
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データベース アプリケーションの作成手順
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の表は、書き込みのデータベース アプリケーションのロールおよびフレームワークの役割を示しています。  
  
> [!NOTE]
>  Visual C\+\+ .NET では、Visual C\+\+ 開発環境およびウィザードでは DAO はサポートされなくなりました \(DAO クラスは含まれているので、このクラスを使うことはできます\)。  Microsoft では、新しい MFC プロジェクトに ODBC を使用することをお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用してください。  
  
### データベース アプリケーションの作成  
  
|タスク|プログラマの作業|フレームワークの働き|  
|---------|--------------|----------------|  
|ODBC データベースまたは MFC DAO クラスを使用するかどうかを決定します。|新しい MFC のプロジェクトで ODBC を使用します。  既存のアプリケーションを保守するためだけに DAO を使用します。  [私は、DAO や ODBC を使用すればよいでしょうか。](../data/should-i-use-dao-or-odbc-q.md)を参照してください。  概要については、[データ アクセス プログラミング](../data/data-access-programming-mfc-atl.md)記事を参照してください。|フレームワークは、データベース アクセスをサポートするクラスが用意されています。|  
|データベース オプションとスケルトン アプリケーションを作成します。|MFC アプリケーション ウィザードを実行します。  データベース サポート ページでオプションを選択します。  レコード ビューを作成するオプションを選択した場合は、指定する:<br /><br /> -   データ ソースとテーブル名または<br />-   クエリ名か。|MFC アプリケーション ウィザードでは、ファイルを作成し、必要な値を含むを指定します。  このファイルは、指定したオプションによってレコードセット クラスを含めることができます。|  
|データベースのフォームをデザインします。|レコード ビュー クラスのダイアログ テンプレート リソースを基にコントロールを配置するには、Visual C\+\+ ダイアログ エディターを使用します。|MFC アプリケーション ウィザードが表示するための空のダイアログ テンプレート リソースを作成します。|  
|必要に応じて、追加レコード ビューとレコードセット クラスを作成します。|クラスとダイアログ エディター ビューをデザイン時に作成するには、クラス ビューを使用してください。|クラス ビューでは、新しいクラスの追加ファイルを作成します。|  
|コードで必要なレコードセット オブジェクトを作成します。  使用するレコードを操作するために各レコードセットを…|レコードセットは、ウィザードで [CRecordset](../Topic/CRecordset%20Class.md) から派生されるクラスに基づいています。|ODBC は、データベースとレコードセットのフィールド データ メンバー間でデータを交換するレコード フィールド エクスチェンジ \(RFX\) "を参照してください。  レコード ビュー、ダイアログのレコード ビューのコントロールとレコードセット間のダイアログ データ エクスチェンジ \(DDX\) データ交換を使用します。|  
|…または開くデータベースごとのコード内で明示 [CDatabase](../mfc/reference/cdatabase-class.md) を作成します。|データベース オブジェクトにレコードセット オブジェクトを適用します。|データベース オブジェクトは、データ ソースへのインターフェイスを提供します。|  
|レコードセットの動的にバインドされます。|ODBC では、バインディングを管理するために派生レコードセット クラスにコードを追加します。  [レコードセット: データ列を動的に結び付ける方法 \(ODBC\)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)記事を参照してください。||  
  
## 参照  
 [フレームワークを使ったアプリケーションの作成](../mfc/building-on-the-framework.md)   
 [MFC アプリケーションの作成手順](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [OLE アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [ActiveX コントロールの作成手順](../mfc/sequence-of-operations-for-creating-activex-controls.md)