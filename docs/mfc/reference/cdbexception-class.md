---
title: "CDBException クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
dev_langs:
- C++
helpviewer_keywords:
- CDBException class
- exceptions [C++], database
- database exceptions [C++]
- ODBC classes [C++], exceptions
- errors [C++], database
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
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
ms.openlocfilehash: fc3bf7be273bf509dd1ee79fb42e69050070e830
ms.lasthandoff: 02/24/2017

---
# <a name="cdbexception-class"></a>CDBException クラス
データベース クラスから発生する例外状態を表現します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|型のオープン データベース コネクティビティ (ODBC) 戻りコード**へ**します。|  
|[CDBException::m_strError](#m_strerror)|英数字の用語では、エラーを説明する文字列が含まれています。|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|ODBC によって返されるエラー コードの観点からエラーを説明する文字列が含まれています。|  
  
## <a name="remarks"></a>コメント  
 クラスには、例外の原因を特定するか、例外を説明するテキスト メッセージを表示に使用できる&2; つのパブリック データ メンバーが含まれます。 `CDBException`オブジェクトが構築され、データベース クラスのメンバー関数によってスローされます。  
  
> [!NOTE]
>  このクラスは、MFC のオープン データベース コネクティビティ (ODBC) クラスのいずれかです。 代わりに、データ アクセス オブジェクト (DAO) のクラスを使用する場合は使用[CDaoException](../../mfc/reference/cdaoexception-class.md)代わりにします。 DAO クラスの名前では、プレフィックスとして"CDao"があります。 詳細については、記事を参照してください。[の概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)します。  
  
 例外は、実行時の異常データ ソースなどのプログラムで制御できない条件に関連する場合や、ネットワーク I/O エラーです。 通常、プログラム実行の過程で表示することが期待されたエラーは通常の例外考慮されません。  
  
 これらのオブジェクトのスコープ内にアクセスすることができます、**キャッチ**式です。 スローも`CDBException`をコードからのオブジェクト、`AfxThrowDBException`グローバル関数。  
  
 [全般]、またはについての例外処理の詳細については`CDBException`オブジェクト、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)と[例外: データベースの例外](../../mfc/exceptions-database-exceptions.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
##  <a name="m_nretcode"></a>CDBException::m_nRetCode  
 型の ODBC エラー コードを表す**へ**ODBC アプリケーション プログラミング インターフェイス (API) 関数によって返されます。  
  
### <a name="remarks"></a>コメント  
 この型には、ODBC で定義されている SQL プレフィックスが付いたコードとデータベース クラスで定義されている AFX_SQL から始まるコードが含まれています。 `CDBException`、このメンバーには、次の値のいずれかが含まれます。  
  
- **AFX_SQL_ERROR_API_CONFORMANCE**用のドライバー、`CDatabase::OpenEx`または`CDatabase::Open`呼び出しが必要な ODBC API への準拠レベル 1 に準拠していません ( **SQL_OAC_LEVEL1**)。  
  
- **AFX_SQL_ERROR_CONNECT_FAIL**データ ソースに接続できませんでした。 渡されたする、 **NULL** `CDatabase`へのポインター、レコード セットのコンス トラクターと接続を作成後の試行がに基づいて`GetDefaultConnect`できませんでした。  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED**用のストレージを提供するよりも多くのデータを要求します。 指定されたデータ記憶域を増やす方法について`CString`または`CByteArray`データ型を参照してください、`nMaxLength`の引数[RFX_Text](http://msdn.microsoft.com/library/de3c7581-d26c-40cb-81f3-c492ef4809f6)と[RFX_Binary](http://msdn.microsoft.com/library/908ff945-3ad0-43a1-9932-cdcdc8b14915) 「マクロとグローバル」。  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED**への呼び出し`CRecordset::Open`ダイナセットの要求に失敗しました。 ダイナセットを使う場合は、ドライバーによってサポートされていません。  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST**テーブルを開こうとしました (または指定した識別できなかったプロシージャ呼び出しとしてまたは**選択**ステートメント) ではレコード フィールド エクス (チェンジ RFX) 関数呼び出しで指定された列が存在しない、`DoFieldExchange`をオーバーライドします。  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH**での RFX 関数の種類、`DoFieldExchange`上書きは、レコード セット内の列のデータ型と互換性がありません。  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE**と呼ばれる、`CRecordset::Update`以前を呼び出さずに`CRecordset::AddNew`または`CRecordset::Edit`です。  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** ODBC ドライバーがロックをサポートしていないために、更新用のレコードをロックする要求を処理できませんでした。  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED**と呼ばれる、`CRecordset::Update`または**削除**ない一意のキーを持つテーブルの複数のレコードを変更します。  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD**を編集または削除されたレコードを削除しようとしました。 削除後、新しいレコードをスクロールする必要があります。  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES**要求 ODBC ドライバーがサポートしていないために、ダイナセットを処理できませんでしたの位置指定更新します。  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED**と呼ばれる、`CRecordset::Update`または**削除**レコードが見つかりません不要になった操作を開始したとき。  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** ODBC を読み込もうとしました。DLL に失敗しました。Windows は見つかりませんでした。 または、この DLL を読み込むことができません。 このエラーは致命的です。  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED**レベル 2 に準拠した ODBC ドライバーが必要なために、ダイナセットへの要求を処理できませんでした。  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY**データ ソースは後方スクロールをサポートしていないために、スクロールしようは成功しませんでした。  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED**への呼び出し`CRecordset::Open`スナップショットを要求に失敗しました。 スナップショットは、ドライバーによってサポートされていません。 (これを実行するだけと ODBC カーソル ライブラリ â €"ODBCCURS します。DLL の â €"は存在しません)。  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE**用のドライバー、`CDatabase::OpenEx`または`CDatabase::Open`呼び出しは、「最小」の必須の ODBC SQL 準拠レベルに準拠していません (**以上でなければなりません**)。  
  
- **返せない場合**、ODBC ドライバーはの合計サイズを指定することが、`CLongBinary`データ値。 グローバル メモリ ブロックが事前しないのでこの操作は失敗します。  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY**読み取り専用レコード セットを更新しようとするか、データ ソースが読み取り専用です。 レコード セットと更新操作を実行しない、または`CDatabase`に関連付けられたオブジェクト。  
  
- **SQL_ERROR**関数が失敗しました。 ODBC 関数から返されたエラー メッセージ**SQLError**に格納されて、 **m_strError**データ メンバーです。  
  
- **SQL_INVALID_HANDLE**関数に無効な環境ハンドル、接続ハンドル、またはステートメント ハンドルのため失敗しました。 これは、プログラミング エラーを示します。 ODBC 関数からその他の情報はありません**SQLError**します。  
  
 SQL プレフィックスが付いたコードは、ODBC によって定義されます。 AFX プレフィックスが付いたコードは、AFXDB で定義されます。H に定義しています。  
  
##  <a name="m_strerror"></a>CDBException::m_strError  
 例外の原因となったエラーを説明する文字列が含まれています。  
  
### <a name="remarks"></a>コメント  
 文字列は、英数字の用語ではエラーを説明します。 詳細な情報と例についてを参照してください。 **m_strStateNativeOrigin**します。  
  
##  <a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin  
 例外の原因となったエラーを説明する文字列が含まれています。  
  
### <a name="remarks"></a>コメント  
 文字列は、フォーム"の状態: %s、ネイティブ: %ld 原点: %s"、次の順序での書式コードが記述する値を置き換え。  
  
-   **SQLSTATE**で返される&5; 文字のエラー コードを含む null で終わる文字列、 *szSqlState* ODBC 関数のパラメーター **SQLError**します。 **SQLSTATE**値は、「付録 A: [ODBC エラー コード](https://msdn.microsoft.com/library/ms714687.aspx)で、 *ODBC プログラマ リファレンス*します。 例:"S0022"です。  
  
-   データ ソースに固有のネイティブ エラー コードが返される、 *pfNativeError*のパラメーター、 **SQLError**関数です。 例: 207 します。  
  
-   返されるエラー メッセージ テキスト、*後*のパラメーター、 **SQLError**関数です。 このメッセージは、いくつかのかっこで囲まれた名前で構成されます。 エラーは、ユーザーにそのソースから渡される、として各 ODBC コンポーネント (データ ソース、ドライバー、ドライバー マネージャー) は、独自の名前を追加します。 この情報は、エラーの原因を突き止めるのに役立ちます。 例: [Microsoft] [ODBC SQL Server Driver] [SQL Server]  
  
 フレームワークは、エラー文字列を解釈し、そのコンポーネントに**m_strStateNativeOrigin**場合**m_strStateNativeOrigin**情報が含まれています、エラーが改行で区切って複数のエラーの場合。 フレームワークは、英数字のエラー テキストを**m_strError**します。  
  
 この文字列を構築するためのコードの詳細については、次を参照してください。、 [SQLError](https://msdn.microsoft.com/library/ms716312.aspx)で機能、 *ODBC プログラマ リファレンス*します。  
  
### <a name="example"></a>例  
  ODBC: から"の状態: S0022、ネイティブ:&207;、原点: [Microsoft] [ODBC SQL Server Driver] [SQL Server] 無効な列名 'ColName'"  
  
 **M_strStateNativeOrigin**:"の状態: S0022、ネイティブ:&207;、原点: [Microsoft] [ODBC SQL Server Driver] [SQL Server]」  
  
 **M_strError**:「無効な列名 'ColName'」  
  
## <a name="see-also"></a>関連項目  
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException クラス](../../mfc/reference/cexception-class.md)

