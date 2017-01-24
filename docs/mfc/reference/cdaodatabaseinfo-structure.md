---
title: "CDaoDatabaseInfo 構造体 | Microsoft Docs"
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
  - "CDaoDatabaseInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabaseInfo 構造体"
  - "DAO (データ アクセス オブジェクト), Databases コレクション"
ms.assetid: 68e9e0da-8382-4fc6-8115-1b1519392ddb
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoDatabaseInfo 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDaoDatabaseInfo` 構造体は、データ アクセス オブジェクト \(DAO\) に定義されているデータベース オブジェクトに関する情報が含まれています。  
  
## 構文  
  
```  
  
      struct CDaoDatabaseInfo  
{  
   CString m_strName;       // Primary  
   BOOL m_bUpdatable;       // Primary  
   BOOL m_bTransactions;    // Primary  
   CString m_strVersion;    // Secondary  
   long m_lCollatingOrder;  // Secondary  
   short m_nQueryTimeout;   // Secondary  
   CString m_strConnect;    // All  
};  
```  
  
#### パラメーター  
 `m_strName`  
 一意にデータベース オブジェクトを指定します。  直接このプロパティを取得するために、[CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md)を呼び出します。  詳細については、" DAO ヘルプの「名前プロパティ」を参照してください。  
  
 `m_bUpdatable`  
 データベースに変更を加えることができるかどうかを示します。  直接このプロパティを取得するために、[CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md)を呼び出します。  詳細については、" DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
 *m\_bTransactions*  
 データ ソースがトランザクション— \(キャンセル\) またはコミット後にロールバックされることができる一連の変更の記録\) をサポートするかどうかを示します \(保存します。  データベースでの Microsoft Jet データベース エンジンを基に、トランザクションのプロパティは 0 以外のであり、トランザクションを使用できます。  他のデータベース エンジンは、トランザクションをサポートしない可能性があります。  直接このプロパティを取得するために、[CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md)を呼び出します。  詳細については、" DAO ヘルプの「トランザクション プロパティ」を参照してください。  
  
 *m\_strVersion*  
 の Microsoft Jet データベース エンジンのバージョンを示します。  このプロパティの値を直接取得するには、データベース オブジェクトの [GetVersion](../Topic/CDaoDatabase::GetVersion.md) メンバー関数を呼び出します。  詳細については、" DAO ヘルプの「Version Property」を参照してください。  
  
 `m_lCollatingOrder`  
 文字列比較または並べ替えることのテキストで並べ替え順序のシーケンスを指定します。  次の値を使用できます。  
  
-   **dbSortGeneral**使用の概要 \(英語、フランス語、ドイツ語、イタリア語、スペイン語、ポルトガル語最新の並べ替え順序\)。  
  
-   **dbSortArabic**並べ替え順序がアラビア語の使用  
  
-   **dbSortCyrillic**の使用ロシア語の並べ替え順序。  
  
-   **dbSortCzech**の使用チェコの並べ替え順序。  
  
-   **dbSortDutch** の使用オランダの並べ替え順序。  
  
-   **dbSortGreek**の使用ギリシャの並べ替え順序。  
  
-   **dbSortHebrew**の使用ヘブライ語並べ替え順序。  
  
-   **dbSortHungarian**の使用ハンガリーの並べ替え順序。  
  
-   **dbSortIcelandic**を使用アイスランドの並べ替え順序。  
  
-   **dbSortNorwdan**を使用またはノルウェー デンマークの並べ替え順序。  
  
-   **dbSortPDXIntl**の使用 Paradox の国際並べ替え順序。  
  
-   **dbSortPDXNor**の使用の Paradox ノルウェー語またはデンマークの並べ替え順序。  
  
-   **dbSortPDXSwe**の使用 Paradox からスウェーデンまたはフィンランドの並べ替え順序。  
  
-   **dbSortPolish**を使用ポーランドの並べ替え順序。  
  
-   **dbSortSpanish**の使用スペイン語の並べ替え順序。  
  
-   **dbSortSwedFin**を使用またはフィンランド スウェーデンの並べ替え順序。  
  
-   **dbSortTurkish**の使用トルコ語の並べ替え順序。  
  
-   **dbSortUndefined**は並べ替え順序、または不明未定義です。  
  
 詳細については、トピック「DAO ヘルプ データ アクセス用の Windows レジストリの設定を」カスタマイズを参照します。  
  
 *m\_nQueryTimeout*  
 クエリが ODBC データベースで実行しているときにタイムアウト エラーが発生する前に、Microsoft Jet データベース エンジンを待機する秒数。  既定のタイムアウト値は 60 秒です。  QueryTimeout が 0 に設定されている場合、タイムアウトが発生しない; これにより、プログラムの応答が停止することがあります。  このプロパティの値を直接取得するには、データベース オブジェクトの [GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md) メンバー関数を呼び出します。  詳細については、" DAO ヘルプの「QueryTimeout プロパティ」を参照してください。  
  
 `m_strConnect`  
 開いているデータベースのソースに関する情報を提供します。  の接続文字列に関する情報とともにこのプロパティの値を直接取得する方法については、[CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md) メンバー関数を参照してください。  詳細については、"が「DAO ヘルプの」プロパティを接続するのを参照します。  
  
## 解説  
 データベース クラスは [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)の MFC オブジェクトの基になる DAO のオブジェクトです。  主要な、セカンダリへの参照は、上記のすべての情報が [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md) メンバー関数によってどのように返されるかを示します。  
  
 [CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md) のメンバー関数によって取得される情報は `CDaoDatabaseInfo` 構造に格納されます。  データベースのコレクションでデータベース オブジェクトを格納する `CDaoWorkspace` オブジェクトの呼び出し `GetDatabaseInfo`。  `CDaoDatabaseInfo` は、デバッグ ビルドの `Dump` のメンバー関数を定義します。  `CDaoDatabaseInfo` オブジェクトの内容をダンプするために `Dump` を使用できます。  
  
## 必要条件  
 **ヘッダー:** afxdao.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)