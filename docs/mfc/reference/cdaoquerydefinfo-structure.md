---
title: "CDaoQueryDefInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoQueryDefInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), QueryDefs collection
- CDaoQueryDefInfo structure
ms.assetid: e20837dc-e78d-4171-a195-1b4075fb5d2a
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 80e681345091ef54e2be2e3f1c1ea6ccaefd9d17
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoquerydefinfo-structure"></a>CDaoQueryDefInfo 構造体
`CDaoQueryDefInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているクエリ定義のオブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoQueryDefInfo  
{  
    CString m_strName;               // Primary  
    short m_nType;   // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    BOOL m_bUpdatable;               // Secondary  
    BOOL m_bReturnsRecords;          // Secondary  
    CString m_strSQL;                // All  
    CString m_strConnect;            // All  
    short m_nODBCTimeout;            // All  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 クエリ定義オブジェクトの一意名します。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。 呼び出す[CDaoQueryDef::GetName](../../mfc/reference/cdaoquerydef-class.md#getname)のため、このプロパティを直接取得します。  
  
 `m_nType`  
 クエリ定義オブジェクトの操作の型を示す値です。 値は、次のいずれかになります。  
  
- **dbQSelect**選択、クエリを作成します。  
  
- **dbQAction**アクション-クエリは、移動、またはデータの変更レコードが返されません。  
  
- **dbQCrosstab**クロス集計表形式: クエリでは、スプレッドシートのような形式でデータを返します。  
  
- **dbQDelete**削除-クエリが指定された行のセットを削除します。  
  
- **dbQUpdate**更新など、クエリが一連のレコードを変更します。  
  
- **dbQAppend** Append-クエリがテーブルまたはクエリの末尾に新しいレコードを追加します。  
  
- **dbQMakeTable**テーブルの作成、クエリでは、レコード セットから新しいテーブルを作成します。  
  
- **dbQDDL**データ定義、クエリのテーブルまたはその一部の構造に影響を与えます。  
  
- **dbQSQLPassThrough**パススルー-SQL ステートメントは、中間処理なしでデータベースのバックエンドに直接渡されます。  
  
- **dbQSetOperation**共用体、クエリが&2; つの指定したすべてのレコードからデータを含むスナップショット タイプのレコード セット オブジェクトを作成または重複するレコードと他のテーブルを削除します。 重複するものは、キーワードを追加**すべて**クエリ定義の SQL ステートメントにします。  
  
- **dbQSPTBulk**併用**dbQSQLPassThrough**レコードを返さないクエリを指定します。  
  
> [!NOTE]
>  SQL パススルー クエリを作成するに設定しない、 **dbQSQLPassThrough**定数です。 これは自動的に設定 Microsoft Jet データベース エンジンによってクエリ定義オブジェクトを作成し、接続プロパティを設定します。  
  
 詳細については、DAO ヘルプの「型プロパティ」を参照してください。  
  
 `m_dateCreated`  
 日付とクエリ定義が作成された時刻。 クエリ定義が作成された日付を直接取得する呼び出し、 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 詳細については、次のコメントを参照してください。 DAO のヘルプでは、トピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
 `m_dateLastUpdated`  
 日付とクエリ定義に加えられた最新の変更の時刻。 テーブルの最終更新日を直接取得する呼び出し、 [GetDateLastUpdated](../../mfc/reference/cdaoquerydef-class.md#getdatelastupdated)クエリ定義のメンバー関数。 詳細については、次のコメントを参照してください。 DAO ヘルプの「「DateCreated LastUpdated プロパティ」を参照してください。  
  
 `m_bUpdatable`  
 クエリ定義のオブジェクトへの変更を行うことができるかどうかを示します。 このプロパティは、する場合**TRUE**は、クエリ定義は更新可能な以外の場合。 更新可能では、クエリ定義オブジェクトのクエリ定義を変更することを意味します。 クエリ定義オブジェクトの更新可能なプロパティに設定**TRUE**かどうか、クエリ定義を更新できる場合でも、結果のレコード セットは更新できません。 このプロパティを直接取得するには、クエリ定義を呼び出す[CanUpdate](../../mfc/reference/cdaoquerydef-class.md#canupdate)メンバー関数。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
 *m_bReturnsRecords*  
 外部データベースに SQL パススルー クエリがレコードを返すかどうかを示します。 このプロパティは、する場合**TRUE**レコードが返されます。 このプロパティを直接取得する呼び出し[CDaoQueryDef::GetReturnsRecords](../../mfc/reference/cdaoquerydef-class.md#getreturnsrecords)します。 外部データベースへのすべての SQL パススルー クエリは、レコードを返します。 SQL など**更新**ステートメントは、SQL の中に、レコードを返さずにレコードを更新**選択**ステートメントはレコードを返します。 詳細については、DAO のヘルプで「レコード表示プロパティ」を参照してください。  
  
 *m_strSQL*  
 クエリ定義オブジェクトによって実行されるクエリを定義する SQL ステートメント。 SQL のプロパティには、レコードの選択方法、グループ化、および順序付けられたクエリを実行するときを決定する SQL ステートメントが含まれています。 ダイナセット型またはスナップショットのレコード セット オブジェクトに含めるレコードを選択するのにクエリを使用できます。 レコードを返さずにデータを変更する一括クエリを定義することもできます。 このプロパティの値を取得するには、クエリ定義を呼び出すことによって直接[GetSQL](../../mfc/reference/cdaoquerydef-class.md#getsql)メンバー関数。  
  
 `m_strConnect`  
 パススルー クエリで使用されるデータベースのソースに関する情報を提供します。 この情報は、接続文字列の形式をとります。 詳細については、文字列を約接続し、このプロパティの値を直接取得する方法の詳細については、次を参照してください。、 [CDaoDatabase::GetConnect](../../mfc/reference/cdaodatabase-class.md#getconnect)メンバー関数。  
  
 *m_nODBCTimeout*  
 Microsoft Jet データベース エンジンがタイムアウト エラーの前に待機する秒数は、ODBC データベース クエリの実行時に発生します。 Microsoft SQL Server などの ODBC データベースを使用している場合がある遅延 ODBC サーバーのネットワーク トラフィックや複雑な使用のため。 無限に待機するのではなく、Microsoft Jet エンジンがエラーを生成するまでに待機する時間を指定できます。 既定のタイムアウト値は、60 秒です。 このプロパティの値を取得するには、クエリ定義を呼び出すことによって直接[GetODBCTimeout](../../mfc/reference/cdaoquerydef-class.md#getodbctimeout)メンバー関数。 詳細については、DAO ヘルプの「補足プロパティ」を参照してください。  
  
## <a name="remarks"></a>コメント  
 クエリ定義クラスのオブジェクトである[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)します。 プライマリ、セカンダリ データベースを上記のすべての参照がによって情報が返される方法を示す、 [GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)クラスのメンバー関数`CDaoDatabase`します。  
  
 によって取得される情報、 [CDaoDatabase::GetQueryDefInfo](../../mfc/reference/cdaodatabase-class.md#getquerydefinfo)メンバー関数は、`CDaoQueryDefInfo`構造体。 呼び出す`GetQueryDefInfo`QueryDefs コレクションでのクエリ定義オブジェクトが格納されているデータベース オブジェクト用です。 `CDaoQueryDefInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoQueryDefInfo`オブジェクトです。 クラス`CDaoDatabase`も直接アクセスすることで返されるプロパティのすべてのメンバー関数を提供、`CDaoQueryDefInfo`オブジェクトを呼び出す必要がありますおそらくほとんど`GetQueryDefInfo`します。  
  
 新しいフィールドまたはパラメーター オブジェクトをクエリ定義オブジェクトのフィールドまたはパラメーターのコレクションに追加する場合は、基になるデータベースが新しいオブジェクトの指定されたデータ型をサポートしていない場合、例外がスローされます。  
  
 日付と時刻の設定は、クエリ定義が作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境で、使用して、ファイル サーバーから直接のこれらの設定を取得する必要があります、**時の net** DateCreated および LastUpdated のプロパティの設定の不一致を避けるためのコマンドです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)

