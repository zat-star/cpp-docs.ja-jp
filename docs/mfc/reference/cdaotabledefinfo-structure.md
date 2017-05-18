---
title: "CDaoTableDefInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 4d1ac5ca00f98f8c34332ce2eb1a180ab715e6ba
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo 構造体
`CDaoTableDefInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているテーブル定義のオブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 テーブル定義オブジェクトの一意名します。 このプロパティの値を直接取得するには、テーブル定義オブジェクトを呼び出す[GetName](../../mfc/reference/cdaotabledef-class.md#getname)メンバー関数。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 `m_bUpdatable`  
 変更をテーブルにできるかどうかを示します。 テーブルが更新可能かどうかをすばやく開くには、`CDaoTableDef`テーブルのオブジェクトし、オブジェクトの[CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate)メンバー関数。 `CanUpdate`常に 0 以外を返します (**TRUE**) の新しく作成されたテーブル定義オブジェクトおよび 0 (**FALSE**) のアタッチされたテーブル定義オブジェクト。 新しいテーブル定義オブジェクトは、現在のユーザーが書き込みアクセス許可を持つデータベースにのみ追加できます。 テーブルには、更新フィールドのみが含まれている場合`CanUpdate`0 を返します。 1 つまたは複数のフィールドが更新可能な`CanUpdate`0 以外を返します。 更新可能なフィールドだけを編集することができます。 詳細については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
 `m_lAttributes`  
 テーブル定義オブジェクトによって表されるテーブルの特性を指定します。 テーブル定義の現在の属性を取得するその[GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes)メンバー関数。 返される値は次の long 定数の組み合わせになります (ビットごとの OR を使用して (**|**) 演算子)。  
  
- **dbAttachExclusive** Microsoft Jet データベース エンジンを使用するデータベース、テーブルは、接続されているテーブルを排他的に開かれてことを示します。  
  
- **dbAttachSavePWD** Microsoft Jet データベース エンジンを使用してデータベースの場合は、ユーザー ID と接続されているテーブルのパスワードは接続情報が保存されていることを示します。  
  
- **dbSystemObject**テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。 システム テーブルは読み取り専用です。  
  
- **dbHiddenObject**テーブルが (一時的に使用) 用 Microsoft Jet データベース エンジンによって提供される非表示のテーブルであることを示します。 システム テーブルは読み取り専用です。  
  
- **dbAttachedTable**テーブルが Paradox データベースなどの非 ODBC データベースからの接続されているテーブルであることを示します。  
  
- **dbAttachedODBC**テーブルが Microsoft SQL Server などの ODBC データベースからの接続されているテーブルであることを示します。  
  
 `m_dateCreated`  
 日付と、テーブルが作成された時刻。 テーブルが作成された日付を直接取得する呼び出し、 [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 詳細については、次のコメントを参照してください。 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
 `m_dateLastUpdated`  
 日付とテーブルのデザインに加えられた最新の変更の時刻。 テーブルの最終更新日を直接取得する呼び出し、 [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 詳細については、次のコメントを参照してください。 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
 *m_strSrcTableName*  
 存在する場合は、接続されているテーブルの名前を指定します。 ソース テーブル名を直接取得する呼び出し、 [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。  
  
 `m_strConnect`  
 開いているデータベースのソースに関する情報を提供します。 このプロパティを確認するには呼び出すことによって、 [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect)のメンバー関数、`CDaoTableDef`オブジェクトです。 詳細については、接続文字列を参照してください`GetConnect`します。  
  
 `m_strValidationRule`  
 変更されたか、テーブルに追加のテーブル定義のフィールドのデータを検証する値。 検証は、Microsoft Jet データベース エンジンを使用するデータベースでのみサポートされます。 検証規則を直接取得する呼び出し、 [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule)のメンバー関数、`CDaoTableDef`テーブルに関連付けられているオブジェクト。 関連情報については、DAO ヘルプの「ValidationRule プロパティ」を参照してください。  
  
 `m_strValidationText`  
 ValidationRule プロパティで指定された検証規則が満たされていない場合、アプリケーションが表示されるメッセージのテキストを指定する値。 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
 *m_lRecordCount*  
 テーブル定義のオブジェクトにアクセスするレコードの数。 このプロパティの設定とは、読み取り専用です。 レコード カウントを直接取得する呼び出し、 [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount)のメンバー関数、`CDaoTableDef`オブジェクトです。 ドキュメントを`GetRecordCount`レコード数の詳細について説明します。 この数を取得できる時間のかかる操作、テーブルには、多くのレコードが含まれている場合に注意してください。  
  
## <a name="remarks"></a>コメント  
 テーブル定義がクラスのオブジェクト[どちら](../../mfc/reference/cdaotabledef-class.md)します。 プライマリ、セカンダリ データベースを上記のすべての参照がによって情報が返される方法を示す、[プライマリ](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo)クラスのメンバー関数`CDaoDatabase`します。  
  
 によって取得される情報、 [cdaodatabase::gettabledefinfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo)メンバー関数は、`CDaoTableDefInfo`構造体。 呼び出す、`GetTableDefInfo`のメンバー関数、 `CDaoDatabase` TableDefs コレクションでのテーブル定義のオブジェクトが格納されているオブジェクト。 `CDaoTableDefInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoTableDefInfo`オブジェクトです。  
  
 日付と時刻の設定は、ベース テーブルが作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境では、ユーザーはこれらの DateCreated で不一致を避けるため、ファイル サーバーから直接設定と LastUpdated のプロパティの設定を取得する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)

