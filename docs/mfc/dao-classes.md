---
title: "DAO クラス | Microsoft Docs"
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
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], クラス"
  - "データベース クラス [C++], DAO"
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DAO クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これらのクラスは、他のアプリケーション フレームワーク クラスを Microsoft Visual Basic や Microsoft Access と同じデータベース エンジンを使用する Data Access Object \(DAO\) のデータベースへの簡単なアクセスを提供するために使用します。  DAO クラスは、ODBC \(Open Database Connectivity\) ドライバーが使用できるさまざまなデータベースにアクセスできます。  
  
 DAO データベースを使用するプログラムに少なくとも `CDaoDatabase` オブジェクトと `CDaoRecordset` オブジェクトがあります。  
  
> [!NOTE]
>  Visual C\+\+ .NET では、Visual C\+\+ 開発環境およびウィザードでは DAO はサポートされなくなりました \(DAO クラスは含まれているので、このクラスを使うことはできます\)。  Microsoft では、新しい MFC プロジェクトに ODBC を使用することをお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用してください。  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 ログオンの名前付きで、パスワード保護されたなデータベース セッションからログオフするようにします。  大半のプログラムでは、既定のワークスペースを使用します。  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 データを操作するデータベースへの接続。  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 データ ソースから選択された 1 組のレコードセットを表現します。  
  
 [CDaoRecordView クラス](../mfc/reference/cdaorecordview-class.md)  
 コントロール内にデータベース レコードを表示するビューです。  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 クエリ定義は、データベースに格納されている通常 1 を表します。  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 DAO クラスから発生する例外状態を表します。  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 DAO データベース クラスで使われる DAO レコード フィールド エクスチェンジ \(DFX: DAO Record Field eXchange\) ルーチンをサポートします。  通常、このクラスを直接使用しません。  
  
## 関連クラス  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 ビットマップなどのバイナリ ラージ オブジェクト \(BLOB \(BLOB\) のストレージにハンドルをカプセル化します。  `CLongBinary` オブジェクトがデータベースのテーブルに格納されている大きいデータ オブジェクトを操作するために使用されます。  
  
 [COleCurrency](../Topic/COleCurrency%20Class.md)  
 整数部 15 桁、小数部 4 桁の固定小数点の数値型である OLE オートメーション型 **CURRENCY** のラッパー。  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE オートメーション型 **DATE** のラッパー。  日付と時間の値を表現します。  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE オートメーション型 **VARIANT** のラッパー。  **VARIANT** のデータは、いろいろな形式で格納されます。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)