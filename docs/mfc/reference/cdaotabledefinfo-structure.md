---
title: "CDaoTableDefInfo 構造体 | Microsoft Docs"
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
  - "CDaoTableDefInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDefInfo 構造体"
  - "DAO (データ アクセス オブジェクト), TableDefs コレクション"
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoTableDefInfo 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDaoTableDefInfo` 構造体は、データ アクセス オブジェクト \(DAO\) に対して定義されているテーブル定義オブジェクトに関する情報が含まれます。  
  
## 構文  
  
```  
  
      struct CDaoTableDefInfo  
{  
   CString m_strName;               // Primary  
   BOOL m_bUpdatable;               // Primary  
   long m_lAttributes;              // Primary  
   COleDateTime m_dateCreated;      // Secondary  
   COleDateTime m_dateLastUpdated;  // Secondary  
   CString m_strSrcTableName;       // Secondary  
   CString m_strConnect;            // Secondary  
   CString m_strValidationRule;     // All  
   CString m_strValidationText;     // All  
   long m_lRecordCount;             // All  
};  
```  
  
#### パラメーター  
 `m_strName`  
 一意にテーブル定義オブジェクトという名前を付けます。  このプロパティの値を直接取得するには、テーブル定義オブジェクトの [GetName](../Topic/CDaoTableDef::GetName.md) メンバー関数を呼び出します。  詳細については、DAO ヘルプの「名前」プロパティの参照します。  
  
 `m_bUpdatable`  
 テーブルへの変更を加えることができるかどうかを示します。  テーブルが更新可能かどうかを調べる方法はテーブルの `CDaoTableDef` オブジェクトを開き、オブジェクトの [CanUpdate](../Topic/CDaoTableDef::CanUpdate.md) メンバー関数を呼び出します。  `CanUpdate` は 添付のテーブル定義オブジェクトで、新しく作成されたテーブル定義オブジェクトと 0 の 0 以外の \(**TRUE**\) \(**FALSE**\) を常に返します。  現在のユーザーがアクセス許可の記述を持つデータベースだけに新しいテーブル定義オブジェクトを付けることができます。  テーブルが nonupdatable フィールドのみが含まれる場合、`CanUpdate` 0 を返します。  一つ以上のフィールドが更新可能な場合は、`CanUpdate` は 0 以外の返します。  更新可能なフィールドを編集できます。  詳細については、DAO ヘルプの「更新可能なプロパティ」を参照します。  
  
 `m_lAttributes`  
 テーブル定義オブジェクトで表されるテーブルの特性を指定します。  テーブル定義の現在の属性を取得するには、[GetAttributes](../Topic/CDaoTableDef::GetAttributes.md) メンバー関数を呼び出します。  返される値はこれらの長い定数の組み合わせはです \(を使用してビットごとの OR \(  **&#124;**\) 演算子\) :  
  
-   の Microsoft Jet データベース エンジンを使用するデータベースの**dbAttachExclusive**、テーブルが排他的に使用するために開くアタッチされているテーブルであることを示します。  
  
-   の Microsoft Jet データベース エンジンを使用するデータベースの**dbAttachSavePWD** は、アタッチされているテーブルのユーザー id とパスワードが接続情報が格納されることを示します。  
  
-   **dbSystemObject**、テーブルがの Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。システム テーブルは読み取り専用です。  
  
-   **dbHiddenObject**、テーブルがの Microsoft Jet データベース エンジンによって提供された隠しテーブルがあることを示しています \(一時的な使用の場合\)。システム テーブルは読み取り専用です。  
  
-   **dbAttachedTable**Paradox、テーブルがデータベースのような非 ODBC データベースからアタッチされているテーブルであることを示します。  
  
-   **dbAttachedODBC**、テーブルが Microsoft SQL Server などの ODBC データベースのアタッチされているテーブルであることを示します。  
  
 `m_dateCreated`  
 テーブルが作成された日時。  テーブルを直接呼び出します。日付を取得するために作成するとき、テーブルに関連付けられている `CDaoTableDef` オブジェクトの [GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md) メンバー関数を。  詳細については、次のコメントを参照してください。  関連情報については、「DateCreated の DAO ヘルプ LastUpdated のプロパティ」を参照してください。  
  
 `m_dateLastUpdated`  
 変更したテーブルのデザインに対するほとんどの最新の変更日時。  最後にテーブルを直接呼び出します。日付を取得するために更新されたり、テーブルに関連付けられている `CDaoTableDef` オブジェクトの [GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md) メンバー関数を。  詳細については、次のコメントを参照してください。  関連情報については、「DateCreated の DAO ヘルプ LastUpdated のプロパティ」を参照してください。  
  
 *m\_strSrcTableName*  
 アタッチされているテーブルの名前を指定します。  直接ソース テーブル名を取得するために、テーブルに関連付けられている `CDaoTableDef` オブジェクトの [GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md) メンバー関数を呼び出します。  
  
 `m_strConnect`  
 開いているデータベースのソースに関する情報を提供します。  `CDaoTableDef` オブジェクトの [GetConnect](../Topic/CDaoTableDef::GetConnect.md) のメンバー関数を呼び出すことによって、このプロパティを確認できます。  接続文字列に関する詳細については、「`GetConnect`」を参照してください。  
  
 `m_strValidationRule`  
 テーブル定義にデータを検証する値がテーブルに変更または追加するように指定する。  検証は、Microsoft Jet データベース エンジンを使用するデータベースでのみサポートされます。  直接検証規則を取得するために、テーブルに関連付けられている `CDaoTableDef` オブジェクトの [GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md) メンバー関数を呼び出します。  関連情報については、" DAO ヘルプの「ValidationRule プロパティ」を参照してください。  
  
 `m_strValidationText`  
 ValidationRule のプロパティで指定される検証規則が満たしている表示するアプリケーションにあるメッセージのテキストを指定する値。  関連情報については、" DAO ヘルプの「ValidationText プロパティ」を参照してください。  
  
 *m\_lRecordCount*  
 レコードの数がテーブル定義オブジェクトにアクセスしています。  このプロパティ設定は読み取り専用です。  直接レコード数を取得するために、`CDaoTableDef` オブジェクトの [GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md) メンバー関数を呼び出します。  `GetRecordCount` のドキュメントはレコード数をさらに詳しく説明します。  テーブルに多数のレコードが含まれている場合は、この数を取得する、時間のかかる操作を指定できます。注意してください。  
  
## 解説  
 テーブル定義はクラス [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)オブジェクトです。  主要な、セカンダリへの参照は、上記のすべての情報をクラス `CDaoDatabase`の [GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md) メンバー関数によってどのように返されるかを示します。  
  
 [CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md) のメンバー関数によって取得される情報は `CDaoTableDefInfo` 構造に格納されます。  テーブル定義のコレクションでテーブル定義オブジェクトが格納されている `CDaoDatabase` オブジェクトの `GetTableDefInfo` メンバー関数を呼び出します。  `CDaoTableDefInfo` は、デバッグ ビルドの `Dump` のメンバー関数を定義します。  `CDaoTableDefInfo` オブジェクトの内容をダンプするために `Dump` を使用できます。  
  
 日付と時刻の設定はベース テーブルが最後に更新された作成されたコンピューターから派生されます。  マルチユーザー環境では、ユーザーはファイル サーバーから DateCreated と LastUpdated プロパティ設定の競合を回避するために、これらの設定を直接取得する必要があります。  
  
## 必要条件  
 **ヘッダー:** afxdao.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)   
 [CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)   
 [CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)   
 [CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)   
 [CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)   
 [CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)   
 [CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)   
 [CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)