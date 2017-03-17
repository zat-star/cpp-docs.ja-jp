---
title: "CRecordset クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
dev_langs:
- C++
helpviewer_keywords:
- database records [C++]
- CRecordset class
- ODBC recordsets [C++], CRecordset objects
- sets of records [C++]
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f7a05a5eefd6f55a68c6e9f1726dfb7c29f399f2
ms.lasthandoff: 02/24/2017

---
# <a name="crecordset-class"></a>CRecordset クラス
データ ソースから選択された&1; 組のレコードセットを表現します。  
  
## <a name="syntax"></a>構文  
  
```  
class CRecordset : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRecordset::CRecordset](#crecordset)|`CRecordset` オブジェクトを構築します。 派生クラスでは、この関数を呼び出すコンス トラクターを提供する必要があります。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|新しいレコードを追加する準備をします。 呼び出す`Update`追加を完了します。|  
|[CRecordset::CanAppend](#canappend)|使用してレコード セットに新しいレコードを追加できる場合は&0; 以外を返す、`AddNew`メンバー関数。|  
|[値](#canbookmark)|レコード セットは、ブックマークをサポートする場合は&0; 以外を返します。|  
|[CRecordset::Cancel](#cancel)|非同期操作または&2; 番目のスレッドからのプロセスをキャンセルします。|  
|[CRecordset::CancelUpdate](#cancelupdate)|期限に保留中の更新プログラムを選択解除、`AddNew`または`Edit`操作します。|  
|[CRecordset::CanRestart](#canrestart)|0 以外の場合を返します。`Requery`レコード セットのクエリを再実行を呼び出すことができます。|  
|[CRecordset::CanScroll](#canscroll)|レコードをスクロールする場合は&0; 以外を返します。|  
|[CRecordset::CanTransact](#cantransact)|データ ソースには、トランザクションがサポートしている場合は&0; 以外を返します。|  
|[CRecordset::CanUpdate](#canupdate)|レコード セットを更新する場合は&0; 以外を返します (することができますを追加、更新、またはレコードを削除) します。|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|レコードをフェッチ中に生成されたエラーの処理と呼ばれます。|  
|[ような場合](#close)|レコード セットと、ODBC 閉じます**HSTMT**関連付けられています。|  
|[CRecordset::Delete](#delete)|レコード セットから現在のレコードを削除します。 削除された後は、別のレコードに明示的にスクロールする必要があります。|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|バルク行をデータ ソースからレコード セットへのデータを交換するには、呼び出されます。 レコード フィールド エクス チェンジ (Bulk RFX) の一括を実装します。|  
|[CRecordset::DoFieldExchange](#dofieldexchange)|データ ソースに対応するレコードとレコード セットのフィールド データ メンバーの間で双方向) の「データを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ RFX) をを実装します。|  
|[CRecordset::Edit](#edit)|現在のレコードへの変更を準備します。 呼び出す`Update`編集を完了します。|  
|[CRecordset::FlushResultSet](#flushresultset)|別の結果がある場合は&0; 以外を返します。 は、定義済みクエリを使用する場合に取得する設定します。|  
|[CRecordset::GetBookmark](#getbookmark)|パラメーター オブジェクトには、レコードのブックマークの値を割り当てます。|  
|[:Getdefaultconnect](#getdefaultconnect)|既定の接続文字列を取得するには、呼び出されます。|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|実行する既定の SQL 文字列を取得するには、呼び出されます。|  
|[CRecordset::GetFieldValue](#getfieldvalue)|レコード セット内のフィールドの値を返します。|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|レコード セットのフィールドの数を返します。|  
|[に](#getodbcfieldinfo)|レコード セットから特定の種類のフィールドについての情報を返します。|  
|[CRecordset::GetRecordCount](#getrecordcount)|レコード セットのレコードの数を返します。|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|1 回のフェッチ時に取得するレコードの数を返します。|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|フェッチ中に取得される行の実際の数を返します。|  
|[CRecordset::GetRowStatus](#getrowstatus)|フェッチ後に、行の状態を返します。|  
|[CRecordset::GetSQL](#getsql)|レコード セットのレコードを選択するために使用する SQL 文字列を取得します。|  
|[CRecordset::GetStatus](#getstatus)|レコード セットの状態を取得します。 現在のレコード、および最終的な数のレコードが取得されたかどうかのインデックス。|  
|[CRecordset::GetTableName](#gettablename)|レコード セットの基になるテーブルの名前を取得します。|  
|[CRecordset::IsBOF](#isbof)|レコード セットは、最初のレコードの前に位置付けられている場合は&0; 以外を返します。 現在のレコードがありません。|  
|[CRecordset::IsDeleted](#isdeleted)|レコード セットが削除されたレコードに配置されている場合は&0; 以外を返します。|  
|[CRecordset::IsEOF](#iseof)|レコード セットは、最後のレコードの後に位置付けられている場合は&0; 以外を返します。 現在のレコードがありません。|  
|[CRecordset::IsFieldDirty](#isfielddirty)|現在のレコードで指定したフィールドが変更された場合は&0; 以外を返します。|  
|[CRecordset::IsFieldNull](#isfieldnull)|現在のレコードで指定されたフィールドが null の場合は&0; 以外を返します (値を持ちません)。|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|現在のレコードで指定したフィールドを null (値がない) に設定できる場合は&0; 以外を返します。|  
|[CRecordset::IsOpen](#isopen)|0 以外の場合を返します。`Open`既に呼び出されています。|  
|[CRecordset::Move](#move)|どちらの方向に現在のレコードから、指定した数のレコードをレコード セットを配置します。|  
|[CRecordset::MoveFirst](#movefirst)|レコード セット内の最初のレコードには、現在のレコードを配置します。 テスト`IsBOF`最初です。|  
|[CRecordset::MoveLast](#movelast)|最後のレコードまたは最後の行セットは、現在のレコードを配置します。 テスト`IsEOF`最初です。|  
|[CRecordset::MoveNext](#movenext)|次のレコードまたは次の行セットは、現在のレコードを配置します。 テスト`IsEOF`最初です。|  
|[CRecordset::MovePrev](#moveprev)|前のレコードまたは前の行セットは、現在のレコードを配置します。 テスト`IsBOF`最初です。|  
|[CRecordset::OnSetOptions](#onsetoptions)|指定された ODBC ステートメントには、(選択に使用する) オプションを設定すると呼ばれます。|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|指定された ODBC ステートメントのオプション (更新時に使用される) を設定すると呼ばれます。|  
|[:Open](#open)|テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。|  
|[CRecordset::RefreshRowset](#refreshrowset)|データと指定した行の状態を更新します。|  
|[:Requery](#requery)|選択したレコードを更新するには、もう一度、レコード セットのクエリを実行します。|  
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|指定されたレコード番号に対応するレコードは、レコード セットに配置します。|  
|[CRecordset::SetBookmark](#setbookmark)|ブックマークが指定されたレコード、レコード セットに配置します。|  
|[CRecordset::SetFieldDirty](#setfielddirty)|変更されたため、現在のレコードで指定したフィールドをマークします。|  
|[CRecordset::SetFieldNull](#setfieldnull)|Null (値を持たない) を現在のレコードで指定したフィールドの値を設定します。|  
|[CRecordset::SetLockingMode](#setlockingmode)|ロック (既定)「オプティミスティック」または「排他的」ロックのロック モードを設定します。 更新プログラムのレコードをロックする方法を決定します。|  
|[CRecordset::SetParamNull](#setparamnull)|指定されたパラメーターを null (値がない) に設定します。|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|行セット内の指定した行にカーソルを位置付けます。|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|フェッチ中に取得するレコードの数を指定します。|  
|[CRecordset::Update](#update)|完了すると、`AddNew`または`Edit`データ ソースに新しいまたは更新されたデータを保存することによって操作します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CRecordset::m_hstmt](#m_hstmt)|レコード セットの ODBC ステートメント ハンドルが含まれています。 「`HSTMT`」と入力します。|  
|[CRecordset::m_nFields](#m_nfields)|レコード セット内のフィールド データ メンバーの数が含まれています。 「`UINT`」と入力します。|  
|[CRecordset::m_nParams](#m_nparams)|レコード セット内のパラメーター データ メンバーの数が含まれています。 「`UINT`」と入力します。|  
|[CRecordset::m_pDatabase](#m_pdatabase)|ポインターを含む、`CDatabase`データ ソースに使用されるレコード セットが接続されているオブジェクト。|  
|[CRecordset::m_strFilter](#m_strfilter)|含む、 `CString` Structured Query Language (SQL) を指定する`WHERE`句。 フィルターとして使用すると、特定の条件を満たすレコードだけを選択します。|  
|[CRecordset::m_strSort](#m_strsort)|含む、 `CString` SQL を指定する`ORDER BY`句。 レコードの並べ替え方法を制御するために使用します。|  
  
## <a name="remarks"></a>コメント  
 「レコード セット」と呼ばれる`CRecordset`オブジェクトが&2; つの形式で通常使用される: ダイナセットを使う場合やスナップショットです。 ダイナセットは、同期を他のユーザーによるデータの更新と共にとどまります。 スナップショットは、データの静的ビューです。 各フォームは、レコード セットを開いた時に固定されたレコードのセットを表しますが、他のユーザーまたはアプリケーションで他のレコード セットのいずれかのレコードに加えられた変更が反映されますダイナセット内のレコードをスクロールするとします。  
  
> [!NOTE]
>  オープン データベース コネクティビティ (ODBC) クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)代わりにします。 詳細については、記事を参照してください。[の概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)します。  
  
 レコード セットのいずれかの種類を使用する通常、アプリケーション固有のレコード セットからクラスを派生`CRecordset`します。 レコード セットは、データ ソースからレコードを選択しをこともできます。  
  
-   レコード間をスクロールします。  
  
-   レコードを更新し、ロックのモードを指定します。  
  
-   データ ソースの選択から使用可能なレコードを制限するために、レコード セットをフィルター処理します。  
  
-   レコード セットを並べ替えます。  
  
-   実行時までわからない情報で、選択範囲をカスタマイズするレコード セットをパラメーター化します。  
  
 クラスを使用するデータベースを開くしへのポインターをコンス トラクターに渡して、レコード セット オブジェクトを構築、`CDatabase`オブジェクトです。 まず、レコード セットの**開く**メンバー関数、オブジェクトは、ダイナセットまたはスナップショットかどうかを指定できます。 呼び出す**開く**データ ソースからデータを選択します。 レコード セット オブジェクトが開かれた後に、レコード間をスクロールし、それらを操作するメンバー関数とデータ メンバーを使用します。 更新可能または読み取り専用であるかどうか、利用できる操作がオブジェクトは、ダイナセットまたはスナップショットかどうかに依存して (このオープン データベース コネクティビティ (ODBC) のデータ ソースの機能) に依存し、バルク行フェッチを実装しているかどうか。 されている変更されたか、後に追加するレコードを更新する、**開く**呼び出し、オブジェクトの**Requery**メンバー関数。 オブジェクトの**閉じる**メンバー関数し、それが完了したら、オブジェクトを破棄します。  
  
 派生で`CRecordset`クラス、レコード フィールド エクス (チェンジ RFX) または読み取りとレコードのフィールドの更新をサポートするためにバルク レコード フィールド エクス チェンジ (Bulk RFX) を使用します。  
  
 レコード セットとレコード フィールド エクス チェンジの詳細については、記事を参照してください。[の概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)、[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)、[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)、および[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。 ダイナセットを使う場合のスナップショットに重点を置いて、記事を参照してください。[ダイナセット](../../data/odbc/dynaset.md)と[スナップショット](../../data/odbc/snapshot.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb.h  
  
##  <a name="addnew"></a>CRecordset::AddNew  
 テーブルに新しいレコードを追加するために準備します。  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります、 [Requery](#requery)メンバー関数を新しく追加したレコードを参照してください。 レコードのフィールドは、最初に Null です。 (データベース用語では「値を持たない」手段を Null に設定し、同じではありません**NULL** c++)。完了するには、操作を呼び出す必要があります、[更新](#update)メンバー関数。 **更新プログラム**のデータ ソースへの変更を保存します。  
  
> [!NOTE]
>  呼び出すことができない場合は、バルク行フェッチを実装している、`AddNew`です。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 `AddNew`レコード セットのフィールド データ メンバーを使用して、新しい空のレコードを準備します。 呼び出した後`AddNew`、レコード セットのフィールド データ メンバーに必要な値を設定します。 (を呼び出す必要はありません、[編集](#edit)この目的のためのメンバー関数を使用してください**編集**の既存のレコードのみです)。関数を呼び出すと**更新**、変更されたフィールド データ メンバーの値は、データ ソースに保存されます。  
  
> [!CAUTION]
>  呼び出す前に、新しいレコードをスクロールする**更新**、新しいレコードは失われ、警告が指定されていません。  
  
 データ ソースは、トランザクションをサポートする場合は、`AddNew`呼び出し、トランザクションの一部です。 トランザクションの詳細については、クラスを参照してください。 [CDatabase](../../mfc/reference/cdatabase-class.md)します。 呼び出す必要があります[CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)呼び出す前に`AddNew`します。  
  
> [!NOTE]
>  ダイナセットを使う場合の新しいレコードは、最後のレコードとしてレコード セットに追加されます。 スナップショットに追加したレコードは追加されません。呼び出す必要があります**Requery**をレコード セットを更新します。  
  
 呼び出すことはできません`AddNew`レコード セットを持つ**開く**メンバー関数が呼び出されていません。 A`CDBException`を呼び出す場合にスローされる`AddNew`レコード セットに追加することはできません。 呼び出して、レコード セットは更新可能かどうかを判断できます[CanAppend](#canappend)します。  
  
 詳細については、次の記事を参照してください:[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)、[レコード セット: 追加、更新、およびレコードの削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)、および[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
### <a name="example"></a>例  
 記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
##  <a name="canappend"></a>CRecordset::CanAppend  
 以前に開いたレコード セットが、新しいレコードを追加することができるかどうかを決定します。  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>戻り値  
 新しいレコードを追加、レコード セットを許可する場合は 0 以外。それ以外の場合 0 を返します。 `CanAppend`読み取り専用レコード セットが開かれている場合 0 を返します。  
  
##  <a name="canbookmark"></a>値  
 レコード セットが、ブックマークを使用してレコードをマークすることができるかどうかを決定します。  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットは、ブックマークをサポートしている場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は独立して、 **crecordset::usebookmarks**オプション、`dwOptions`のパラメーター、[開く](#open)メンバー関数。 `CanBookmark`特定の ODBC ドライバーとカーソルがサポートのブックマークを入力するかどうかを示します。 **Crecordset::usebookmarks**はサポートされていれば、ブックマークが使用できるかどうかを示します。  
  
> [!NOTE]
>  ブックマークは、順方向専用レコード セットではサポートされていません。  
  
 ブックマークとレコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。  
  
##  <a name="cancel"></a>CRecordset::Cancel  
 実行中の非同期操作または&2; つ目のスレッドからのプロセスのいずれかのデータ ソースのキャンセルを要求します。  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>コメント  
 MFC ODBC クラスが、非同期処理の使用を不要になったことに注意してください。非同期操作を実行する ODBC API 関数を直接に呼び出す必要があります**SQLSetConnectOption**します。 詳細については、「関数の非同期実行」のトピックを参照してください、 *ODBC SDK Programmer's Guide*します。  
  
##  <a name="cancelupdate"></a>CRecordset::CancelUpdate  
 保留中の更新の原因で、すべてをキャンセル、[編集](#edit)または[AddNew](#addnew)操作、前に[更新](#update)が呼び出されます。  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  このメンバー関数は、バルク行フェッチ、このようなレコード セットを呼び出すことはできませんのでを使用しているレコード セットに適用することはありません**編集**、 `AddNew`、または**更新**します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 自動ダーティ フィールド チェックが有効になっている場合は、`CancelUpdate`メンバー変数を前に、の値に復元されます**編集**または`AddNew`と呼ばれる以外の場合、その変更は保持されます。 既定では、フィールドの自動チェックが有効、レコード セットが開かれたときです。 無効にして、指定する必要があります、 **crecordset::nodirtyfieldcheck**で、`dwOptions`のパラメーター、[開く](#open)メンバー関数。  
  
 データ更新の詳細については、記事を参照してください。[レコード セット: 追加、更新、およびレコードの削除 (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)します。  
  
##  <a name="canrestart"></a>CRecordset::CanRestart  
 レコード セットを呼び出して、クエリを (レコードを更新する) を再起動できるかどうかを判断、 **Requery**メンバー関数。  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>戻り値  
 再クエリが使用できる場合は 0 以外。それ以外の場合 0 を返します。  
  
##  <a name="canscroll"></a>CRecordset::CanScroll  
 レコード セットでは、スクロールできるかどうかを決定します。  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットがスクロールできる場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、スクロール、記事を参照して[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。  
  
##  <a name="cantransact"></a>CRecordset::CanTransact  
 レコード セットにトランザクションができるかどうかを決定します。  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットは、トランザクションを許可する場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
##  <a name="canupdate"></a>CRecordset::CanUpdate  
 レコード セットを更新できるかどうかを決定します。  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、レコード セットを更新することができます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 レコード セットは、その基になるデータ ソースが読み取り専用である場合、または指定した場合は読み取り専用する可能性があります**crecordset::readonly**で、`dwOptions`パラメーターは、レコード セットを開いたときにします。  
  
##  <a name="checkrowseterror"></a>CRecordset::CheckRowsetError  
 レコードをフェッチ中に生成されたエラーの処理と呼ばれます。  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRetCode`  
 ODBC API 関数には、コードが返されます。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 この仮想メンバー関数は、レコードをフェッチしたときに発生するエラーを処理し、バルク行フェッチ役に立ちます。 オーバーライドすることを検討することも`CheckRowsetError`エラー処理を実装します。  
  
 `CheckRowsetError`自動的に呼び出されますカーソルのナビゲーション操作でなど**開いている**、 **Requery**、またはその**移動**操作します。 ODBC API 関数の戻り値が渡される**SQLExtendedFetch**します。 次の表に、可能な値、`nRetCode`パラメーター。  
  
|終了|説明|  
|--------------|-----------------|  
|**SQL_SUCCESS**|関数は正常に完了しましたその他の情報はありません。|  
|**SQL_SUCCESS_WITH_INFO**|関数は致命的でないエラーのため、場合によって正常に完了します。 追加情報を呼び出すことによって取得できる**SQLError**します。|  
|**SQL_NO_DATA_FOUND**|結果セットからすべての行がフェッチされました。|  
|**SQL_ERROR**|関数が失敗しました。 追加情報を呼び出すことによって取得できる**SQLError**します。|  
|**SQL_INVALID_HANDLE**|関数は、無効な環境ハンドル、接続ハンドル、またはステートメント ハンドルのため失敗しました。 これは、プログラミング エラーを示します。 追加情報が利用できない**SQLError**します。|  
|`SQL_STILL_EXECUTING`|非同期的に開始された関数が実行中です。 既定では、MFC が決してに合格するには、この値に注意してください`CheckRowsetError`です。MFC の呼び出しは引き続き**SQLExtendedFetch**返されなくなるまで`SQL_STILL_EXECUTING`します。|  
  
 詳細については**SQLError**を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="close"></a>ような場合  
 レコード セットを閉じます。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 ODBC **HSTMT**とすべてのメモリが、レコード セットに割り当てられているフレームワークは割り当てを解除します。 呼び出した後に通常**閉じる**で割り当てられた場合は、C++ のレコード セット オブジェクトを削除する**新しい**します。  
  
 呼び出すことができます**開く**呼び出した後でもう一度**閉じる**します。 これにより、レコード セット オブジェクトを再利用できます。 呼び出す場合は**Requery**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase&17;](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="crecordset"></a>CRecordset::CRecordset  
 `CRecordset` オブジェクトを構築します。  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDatabase`  
 ポインターを含む、`CDatabase`オブジェクトまたは値**NULL**します。 かどうか**NULL**と`CDatabase`オブジェクトの**開く**データ ソースに接続するメンバー関数が呼び出されていない場合、レコード セットがそれ自体の中に開きたいを試みます**開く**を呼び出します。 渡した場合**NULL**、`CDatabase`オブジェクトが構築され、ClassWizard でユーザーがレコード セット クラスを派生する場合に指定したデータ ソース情報を使用して接続します。  
  
### <a name="remarks"></a>コメント  
 使用するか`CRecordset`直接からアプリケーションに固有のクラスを派生させたり`CRecordset`します。 ClassWizard を使用して、レコード セット クラスを派生させることができます。  
  
> [!NOTE]
>  派生クラス*必要があります*独自のコンス トラクターを指定します。 派生クラスのコンス トラクターで、コンス トラクターを呼び出します`CRecordset::CRecordset`に沿った適切なパラメーターを渡します。  
  
 渡す**NULL**してレコード セット コンス トラクターに、`CDatabase`オブジェクトが構築され、自動的に結合します。 これは、方法を使うの構築し、接続を必要としない、`CDatabase`レコード セットを構築する前にオブジェクトです。  
  
### <a name="example"></a>例  
 詳細については、記事を参照してください。[レコード セット: テーブル (ODBC) を利用したクラス宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)します。  
  
##  <a name="delete"></a>CRecordset::Delete  
 現在のレコードを削除します。  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>コメント  
 削除が成功した後、レコード セットのフィールド データ メンバーは、Null 値に設定されのいずれかを明示的に呼び出す必要があります、**移動**削除されたレコードを移動するために機能します。 削除されたレコードに移動するに戻ることはできません。 データ ソースは、トランザクションをサポートする場合は、**削除**呼び出し、トランザクションの一部です。 詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
> [!NOTE]
>  呼び出すことができない場合は、バルク行フェッチを実装している、**削除**します。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
> [!CAUTION]
>  レコード セットは更新可能である必要があり、ある有効なレコードの現在のレコード セットを呼び出すと**削除**。 そうしないと、エラーが発生します。 たとえば、レコードを削除してを呼び出す前に別のレコードにはスクロールされません**削除**ここでも、**削除**がスローされます、 [CDBException](../../mfc/reference/cdbexception-class.md)します。  
  
 異なり[AddNew](#addnew)と[編集](#edit)への呼び出し**削除**への呼び出しが発生しなかった[更新](#update)します。 場合、**削除**呼び出しが失敗した場合は、変更されていないフィールドのデータ メンバーが残されます。  
  
### <a name="example"></a>例  
 この例では、関数のフレームで作成されたレコード セットを使用します。 例では、想定して`m_dbCust`、型のメンバー変数`CDatabase`既にデータ ソースに接続します。  
  
 [!code-cpp[NVC_MFCDatabase&#18;](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="dobulkfieldexchange"></a>CRecordset::DoBulkFieldExchange  
 バルク行をデータ ソースからレコード セットへのデータを交換するには、呼び出されます。 レコード フィールド エクス チェンジ (Bulk RFX) の一括を実装します。  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 ポインター、 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトです。 フレームワークは既にセットアップこのオブジェクト フィールドの exchange 操作のためのコンテキストを指定します。  
  
### <a name="remarks"></a>コメント  
 バルク行フェッチが実装された場合、フレームワークは、レコード セット オブジェクトにデータ ソースからデータを自動的に転送するには、このメンバー関数を呼び出します。 `DoBulkFieldExchange`また、レコード セットの選択範囲の SQL ステートメントの文字列のパラメーターのプレース ホルダーに存在する場合、パラメーターのデータ メンバーをバインドします。  
  
 バルク行フェッチが実装されていない場合、フレームワーク[DoFieldExchange](#dofieldexchange)します。 バルク行フェッチを実装するのに指定する必要があります、`CRecordset::useMultiRowFetch`のオプション、`dwOptions`内のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
> `DoBulkFieldExchange`派生するクラスを使用している場合にのみ使用できますが`CRecordset`です。 直接レコード セット オブジェクトを作成した場合`CRecordset`、呼び出す必要があります、 [GetFieldValue](#getfieldvalue)のデータを取得します。  
  
 バルク レコード フィールド エクス チェンジ (Bulk RFX) は、レコード フィールド エクス (チェンジ RFX) に似ています。 データは、レコード セット オブジェクトへのデータ ソースから自動的に転送されます。 ただし、呼び出すことができない`AddNew`、**編集**、**削除**、または**更新**の変更をデータ ソースに転送します。 クラス`CRecordset`現在はデータの一括行を更新するためのメカニズムを提供しません ODBC API 関数を使用して、独自の関数を記述する、 **SQLSetPos**します。  
  
 ClassWizard では、バルク レコード フィールド エクス チェンジ; はサポートされていないことに注意してください。したがって、オーバーライドする必要があります`DoBulkFieldExchange`手動で Bulk RFX 関数の呼び出しを記述します。 これらの関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)します。  
  
 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。 関連情報については、記事を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)します。  
  
##  <a name="dofieldexchange"></a>CRecordset::DoFieldExchange  
 データ ソースに対応するレコードとレコード セットのフィールド データ メンバーの間で双方向) の「データを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ RFX) をを実装します。  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 ポインター、 [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)オブジェクトです。 フレームワークは既にセットアップこのオブジェクト フィールドの exchange 操作のためのコンテキストを指定します。  
  
### <a name="remarks"></a>コメント  
 バルク行フェッチが実装されていない場合、フレームワークは、自動的にデータ ソースの現在のレコードの対応する列とレコード セット オブジェクトのフィールド データ メンバーの間でデータを交換するには、このメンバー関数を呼び出します。 `DoFieldExchange`また、レコード セットの選択範囲の SQL ステートメントの文字列のパラメーターのプレース ホルダーに存在する場合、パラメーターのデータ メンバーをバインドします。  
  
 バルク行フェッチが実装されている場合、フレームワーク[DoBulkFieldExchange](#dobulkfieldexchange)します。 バルク行フェッチを実装するのに指定する必要があります、`CRecordset::useMultiRowFetch`のオプション、`dwOptions`内のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
> `DoFieldExchange`派生するクラスを使用している場合にのみ使用できますが`CRecordset`です。 直接レコード セット オブジェクトを作成した場合`CRecordset`、呼び出す必要があります、 [GetFieldValue](#getfieldvalue)のデータを取得します。  
  
 レコード フィールド エクス チェンジ (RFX) と呼ばれるフィールドのデータの交換が双方向で機能します。 データ ソースのレコードのフィールドにレコード セット オブジェクトのフィールド データ メンバーと、レコード セット オブジェクトをデータ ソースのレコードからです。  
  
 唯一実行操作を実装するために通常必要`DoFieldExchange`派生レコード セット クラスは ClassWizard でクラスを作成し、フィールド データ メンバーの名前とデータ型を指定します。 ClassWizard をパラメーター データ メンバーを指定するかを動的に連結するすべての列と処理するために記述するコードを追加することも可能性があります。 詳細については、記事を参照してください。[レコード セット: データ列を動的にバインド (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)します。  
  
 ClassWizard 使用して、派生したレコード セット クラスを宣言するときのオーバーライドが書き込まれます`DoFieldExchange`次の例のようにします。  
  
 [!code-cpp[NVC_MFCDatabase&#19;](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 RFX 関数の詳細については、トピックを参照してください。[レコード フィールド エクス チェンジ関数](../../mfc/reference/record-field-exchange-functions.md)します。  
  
 さらに例と詳細については`DoFieldExchange`、記事を参照して[レコード フィールド エクス チェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)します。 RFX の詳細については、記事を参照してください。[レコード フィールド エクス チェンジ](../../data/odbc/record-field-exchange-rfx.md)します。  
  
##  <a name="edit"></a>CRecordset::Edit  
 現在のレコードを変更をできます。  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後**編集**、直接その値をリセットして、フィールド データ メンバーを変更することができます。 操作が完了するときに、[更新](#update)データ ソースで変更を保存するメンバー関数。  
  
> [!NOTE]
>  呼び出すことができない場合は、バルク行フェッチを実装している、**編集**します。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 **編集**レコード セットのデータ メンバーの値を保存します。 呼び出す場合**編集**を変更し、呼び出す**編集**元に&1; つ目の前に、レコードの値を復元する、もう一度**編集**を呼び出します。  
  
 場合によっては、(データを含まない) を Null にすることで、列を更新することがあります。 これを行うには、呼び出す[な](#setfieldnull)のパラメーターを持つ**TRUE** Null フィールドをマークするこれもにより、更新される列です。 場合は、フィールドの値が変更されていない場合でも、データ ソースに書き込まれ、呼び出しを[き](#setfielddirty)のパラメーターを持つ**TRUE**します。 これは、フィールド値の Null であった場合でも機能します。  
  
 データ ソースは、トランザクションをサポートする場合は、**編集**呼び出し、トランザクションの一部です。 呼び出す必要があります[CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans)呼び出す前に**編集**とレコード セットが開かれた後。 その通話にも注意して[CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans)呼び出しに代わるものではありません**更新**を完了する、**編集**操作します。 トランザクションの詳細については、クラスを参照してください。 [CDatabase](../../mfc/reference/cdatabase-class.md)します。  
  
 現在のロック モードによって更新されるレコードがロックされている**編集**が呼び出されるまで**更新**または別のレコードをスクロール中だけロックする可能性がありますか、**編集**を呼び出します。 ロック モードを変更する[SetLockingMode](#setlockingmode)します。  
  
 呼び出す前に新しいレコードをスクロールする場合、現在のレコードの前の値が復元された**更新**します。 A`CDBException`を呼び出す場合にスローされる**編集**更新できないレコードまたは現在のレコードがないかどうか。  
  
 詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)と[レコード セット: ロック (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase&#20;](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="flushresultset"></a>CRecordset::FlushResultSet  
 複数の結果セットがある場合は、定義済みクエリ (ストアド プロシージャ) の次の結果セットを取得します。  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>戻り値  
 取得する複数の結果セットがある場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります`FlushResultSet`のみ完全に終了したら現在の結果セットのカーソルを使用します。 次の結果を呼び出すことによって設定を取得するときに注意してください`FlushResultSet`、カーソルを置き、その結果セットでは有効ではなく呼び出す必要があります、 [MoveNext](#movenext)メンバー関数の呼び出し後`FlushResultSet`します。  
  
 定義済みのクエリでは、出力パラメーターまたは入出力パラメーターを使用する場合を呼び出す必要があります`FlushResultSet`返されるまで`FALSE`(値 0)、これらのパラメーター値を取得するためにします。  
  
 `FlushResultSet`ODBC API 関数を呼び出す`SQLMoreResults`します。 場合`SQLMoreResults`返します`SQL_ERROR`または`SQL_INVALID_HANDLE`、し`FlushResultSet`は例外をスローします。 詳細については`SQLMoreResults`を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 ストアド プロシージャを呼び出そうとする場合、フィールドにバインドする必要がある`FlushResultSet`です。  
  
### <a name="example"></a>例  
 次のコードがあると見なさ`COutParamRecordset`は、`CRecordset`の入力パラメーターと出力パラメーターでは、定義済みのクエリに基づいており、複数の結果セットを持つ派生オブジェクト。 構造に注意してください、 [DoFieldExchange](#dofieldexchange)をオーバーライドします。  
  
 [!code-cpp[NVC_MFCDatabase #&21;](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase #&22;](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="getbookmark"></a>CRecordset::GetBookmark  
 現在のレコードのブックマークの値を取得します。  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 `varBookmark`  
 参照、 [CDBVariant](../../mfc/reference/cdbvariant-class.md)を現在のレコードのブックマークを表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 調べるには、レコード セットでブックマークがサポートされているかどうか、呼び出す[調べる](#canbookmark)します。 ブックマークを使用できるようにサポートされている場合に設定する必要があります、 **crecordset::usebookmarks**オプション、`dwOptions`のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  ブックマークがサポートされていないか使用できない場合、呼び出す`GetBookmark`スローされた例外が発生します。 ブックマークは、順方向専用レコード セットではサポートされていません。  
  
 `GetBookmark`現在のレコードのブックマークの値を代入、`CDBVariant`オブジェクトです。 いつでも別のレコードに移動した後、そのレコードに戻り、呼び出す[SetBookmark](#setbookmark)で対応する`CDBVariant`オブジェクトです。  
  
> [!NOTE]
>  レコード セットの特定の操作の後ブックマークが無効になります。 呼び出す場合など`GetBookmark`続けて**Requery**のレコードに戻ることはできない`SetBookmark`します。 呼び出す[CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を安全に呼び出すことができるかどうかを確認する`SetBookmark`です。  
  
 ブックマークとレコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。  
  
##  <a name="getdefaultconnect"></a>:Getdefaultconnect  
 既定の接続文字列を取得するには、呼び出されます。  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`既定の接続文字列を格納しています。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、レコード セットの基になるデータ ソースの既定の接続文字列を取得するには、このメンバー関数を呼び出します。 ClassWizard では、テーブルと列に関する情報を取得する ClassWizard で使用する、同じデータ ソースを特定することによってのこの関数を実装します。 おそらくご、アプリケーションを開発中に、この既定の接続に依存すると便利です。 既定の接続をアプリケーションのユーザーに対して適切ではありません。 場合は、ClassWizard のバージョンを破棄すること、この関数を修正する必要があります。 接続文字列の詳細については、記事を参照してください。[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)します。  
  
##  <a name="getdefaultsql"></a>CRecordset::GetDefaultSQL  
 実行する既定の SQL 文字列を取得するには、呼び出されます。  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`を既定の SQL ステートメントが含まれています。  
  
### <a name="remarks"></a>コメント  
 フレームワークでは、レコード セットの基になる既定の SQL ステートメントを取得するには、このメンバー関数を呼び出します。 これは、テーブル名または SQL**選択**ステートメントです。  
  
 直接定義するしない既定の SQL ステートメントで ClassWizard、レコード セット クラスを宣言することで ClassWizard では、このタスクを実行する.  
  
 独自の SQL ステートメントの文字列が必要な場合`GetSQL`を開いたときに、レコード セットのレコードを選択するための SQL ステートメントが返されます。 クラスのオーバーライドで、既定の SQL 文字列を編集する`GetDefaultSQL`です。 使用して、定義済みクエリへの呼び出しを指定するなど、**呼び出す**ステートメントです。 (注、編集する場合、 `GetDefaultSQL`、変更する必要も`m_nFields`データ ソース内の列の数に一致する)。  
  
 詳細については、記事を参照してください。[レコード セット: テーブル (ODBC) を利用したクラス宣言](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)します。  
  
> [!CAUTION]
>  テーブル名は、フレームワークが複数のテーブル名が指定された場合、またはテーブル名、識別できない場合は空になります、**呼び出す**ステートメントを解釈できませんでした。 使用する場合、**を呼び出す**ステートメント、中かっこの間に空白を挿入する必要がありますと**を呼び出す**キーワード、中かっこの前に、または前に空白を挿入すると、**選択**でキーワード、**を選択**ステートメントです。  
  
##  <a name="getfieldvalue"></a>CRecordset::GetFieldValue  
 現在のレコードのフィールドのデータを取得します。  
  
```  
void GetFieldValue(
    LPCTSTR lpszName,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CStringA& strValue);

 
void GetFieldValue(
    short nIndex,  
    CStringW& strValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 フィールドの名前。  
  
 *varValu*e  
 参照、 [CDBVariant](../../mfc/reference/cdbvariant-class.md)フィールドの値を格納するオブジェクト。  
  
 `nFieldType`  
 フィールドの ODBC C データ型。 既定値を使用して**DEFAULT_FIELD_TYPE**、強制的に`GetFieldValue`次の表に基づいて SQL データ型から C データ型を決定します。 それ以外の場合は、データを直接入力または互換性のあるデータの種類を選択を指定できます。たとえばに任意のデータ型を格納することができます**SQL_C_CHAR**します。  
  
|C データ型|SQL データ型|  
|-----------------|-------------------|  
|**SQL_C_BIT**|**SQL_BIT**|  
|**SQL_C_UTINYINT**|**SQL_TINYINT**|  
|**SQL_C_SSHORT**|**SQL_SMALLINT**|  
|**SQL_C_SLONG**|**SQL_INTEGER**|  
|**SQL_C_FLOAT**|**SQL_REAL**|  
|**SQL_C_DOUBLE**|**SQL_FLOATSQL_DOUBLE**|  
|**SQL_C_TIMESTAMP**|**SQL_DATESQL_TIMESQL_TIMESTAMP**|  
|**SQL_C_CHAR**|**SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR**|  
|**SQL_C_BINARY**|**SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY**|  
  
 ODBC データ型の詳細については、「SQL データ型」および「C のデータ型」の付録 D のトピックを参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `nIndex`  
 フィールドの&0; から始まるインデックス。  
  
 `strValue`  
 参照、 [CString](../../atl-mfc-shared/reference/cstringt-class.md)フィールドの値を格納するオブジェクトをフィールドのデータ型に関係なく、テキストに変換します。  
  
### <a name="remarks"></a>コメント  
 名前またはインデックスは、フィールドを参照することができます。 いずれかのフィールドの値を格納する、`CDBVariant`オブジェクトまたは`CString`オブジェクトです。  
  
 バルク行フェッチを実装している場合、現在のレコードは常に行セットの最初のレコードに位置付けられます。 使用する`GetFieldValue`で指定された行セット内のレコード、最初に呼び出す必要があります、 [SetRowsetCursorPosition](#setrowsetcursorposition)その行セット内で目的の行にカーソルを移動するメンバー関数。 物書き`GetFieldValue`その行に対応します。 バルク行フェッチを実装するのに指定する必要があります、`CRecordset::useMultiRowFetch`のオプション、`dwOptions`内のパラメーター、[開く](#open)メンバー関数。  
  
 使用する`GetFieldValue`デザイン時に静的にバインドするのではなく、実行時にフィールドを動的に取得します。 たとえば、宣言した後は、レコード セット オブジェクトから直接`CRecordset`、使用する必要があります`GetFieldValue`を取得するフィールドのデータはレコード フィールド エクス チェンジ (RFX) またはバルク レコード フィールド エクス チェンジ (Bulk RFX) が実装されていません。  
  
> [!NOTE]
>  派生することがなく、レコード セット オブジェクトを宣言する場合`CRecordset`、ODBC カーソル ライブラリが読み込まれる必要はありません。 カーソル ライブラリでは、レコード セットは、バインドされた列を少なくとも&1; つである必要があります。ただし、使用`CRecordset`列がないが、直接バインドされています。 メンバー関数は、 [cdatabase::openex](../../mfc/reference/cdatabase-class.md#openex)と[cdatabase::open](../../mfc/reference/cdatabase-class.md#open)カーソル ライブラリが読み込まれるかどうかを制御します。  
  
 `GetFieldValue`ODBC API 関数を呼び出す**SQLGetData**します。 ドライバーは、値を出力する場合**SQL_NO_TOTAL**フィールドの値の実際の長さの`GetFieldValue`例外をスローします。 詳細については**SQLGetData**を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のサンプル コードでは`GetFieldValue`から直接、レコード セット オブジェクトが宣言されているため`CRecordset`です。  
  
 [!code-cpp[NVC_MFCDatabase 第&23;](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  DAO クラスとは異なり`CDaoRecordset`、`CRecordset`が、`SetFieldValue`メンバー関数。 直接オブジェクトを作成する場合は、 `CRecordset`、効果的に読み取り専用であります。  
  
 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="getodbcfieldcount"></a>CRecordset::GetODBCFieldCount  
 レコード セット オブジェクト内のフィールドの合計数を取得します。  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット内のフィールドの数。  
  
### <a name="remarks"></a>コメント  
 レコード セットの作成に関する詳細については、記事を参照してください。[レコード セット: の生成と破棄 (ODBC) のレコード セット](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)します。  
  
##  <a name="getodbcfieldinfo"></a>に  
 レコード セット内のフィールドに関する情報を取得します。  
  
```  
void GetODBCFieldInfo(
    LPCTSTR lpszName,  
    CODBCFieldInfo& fieldinfo);

 
void GetODBCFieldInfo(
    short nIndex,  
    CODBCFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 フィールドの名前。  
  
 `fieldinfo`  
 参照、`CODBCFieldInfo`構造体。  
  
 `nIndex`  
 フィールドの&0; から始まるインデックス。  
  
### <a name="remarks"></a>コメント  
 関数の&1; つのバージョンでは、フィールドを名前で検索することができます。 その他のバージョンでは、インデックスでフィールドを検索することができます。  
  
 返される情報の説明を参照してください、 [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md)構造体。  
  
 レコード セットの作成に関する詳細については、記事を参照してください。[レコード セット: の生成と破棄 (ODBC) のレコード セット](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)します。  
  
##  <a name="getrecordcount"></a>CRecordset::GetRecordCount  
 レコード セットのサイズを決定します。  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット内のレコードの数レコード セットにレコードが含まれていない場合は 0またはレコードの数を特定できない場合は – 1 を選択します。  
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  レコード カウントは、"high watermark"番号が最大レコードとして保持がまだユーザーがレコードを移動すると表示されます。 レコードの合計数は、ユーザーが最後のレコードに進んだ後だけ呼ばれます。 パフォーマンス上の理由から、呼び出すときに、数は更新されません`MoveLast`します。 レコードを自分でカウントするを呼び出す`MoveNext`まで繰り返し`IsEOF`0 以外を返します。 使用してレコードを追加する**CRecordset:AddNew**と**更新**数を増やします。 を使用してレコードを削除する`CRecordset::Delete`数が減少します。  
  
##  <a name="getrowsetsize"></a>CRecordset::GetRowsetSize  
 回のフェッチ時に取得する行の数の現在の設定を取得します。  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 回のフェッチ時に取得する行の数。  
  
### <a name="remarks"></a>コメント  
 バルク行フェッチを使用している、レコード セットを開いたときの既定の行セット サイズは 25 です。それ以外の場合は 1 です。  
  
 バルク行フェッチを実装するのに指定する必要があります、`CRecordset::useMultiRowFetch`オプション、`dwOptions`のパラメーター、[開く](#open)メンバー関数。 行セットのサイズの設定を変更するには、呼び出す[SetRowsetSize](#setrowsetsize)します。  
  
 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="getrowsfetched"></a>CRecordset::GetRowsFetched  
 フェッチ後に実際に取得されたレコード数を決定します。  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>戻り値  
 行の数は、特定のフェッチ後に、データ ソースから取得します。  
  
### <a name="remarks"></a>コメント  
 これは、機能は、バルク行フェッチを実装するときに便利です。 行セットのサイズが通常フェッチから取得する行の数を示しますただし、レコード セットの行の合計数にも影響行セットの行の数が取得されます。 たとえば、レコード セットに行セット サイズ設定が 4 の 10 個のレコードがある場合は、ループ レコード セットを呼び出すことによって`MoveNext`2 レコードだけを持つ最後の行セットになります。  
  
 バルク行フェッチを実装するのに指定する必要があります、`CRecordset::useMultiRowFetch`オプション、`dwOptions`のパラメーター、[開く](#open)メンバー関数。 行セットのサイズを指定するには、呼び出す[SetRowsetSize](#setrowsetsize)します。  
  
 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase #&24;](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="getrowstatus"></a>CRecordset::GetRowStatus  
 現在の行セット内の行の状態を取得します。  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `wRow`  
 1 から始まる位置の行の現在の行セット。 この値の範囲は 1、行セットのサイズにします。  
  
### <a name="return-value"></a>戻り値  
 行のステータス値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 `GetRowStatus`またはデータ ソースから取得したが最後の行へのステータスの変更を示す値を返すに対応する行`wRow`がフェッチされました。 次の表は、可能性のある戻り値の一覧です。  
  
|状態値|説明|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|行は変更されません。|  
|`SQL_ROW_UPDATED`|行が更新されました。|  
|`SQL_ROW_DELETED`|行が削除されました。|  
|`SQL_ROW_ADDED`|行が追加されました。|  
|`SQL_ROW_ERROR`|行は、エラーのため取得することができます。|  
|`SQL_ROW_NOROW`|対応する行がない`wRow`します。|  
  
 詳細については、ODBC API 関数を参照してください。 **SQLExtendedFetch**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getstatus"></a>CRecordset::GetStatus  
 レコード セットと最後のレコードが認識されているかどうかの現在のレコードのインデックスを決定します。  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `rStatus`  
 参照、 **CRecordsetStatus**オブジェクトです。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 `CRecordset`指標を追跡する試行は状況によってはこれが不可能です。 参照してください[GetRecordCount](#getrecordcount)説明します。  
  
 **CRecordsetStatus**構造体には、次の形式。  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 2 つのメンバー **CRecordsetStatus**は次の意味があります。  
  
- **m_lCurrentRecord**がわかっている場合、レコード セット内の現在のレコードの&0; から始まるインデックスが含まれています。 このメンバーを含む、インデックスを特定できない場合**AFX_CURRENT_RECORD_UNDEFINED** (–&2;)。 場合`IsBOF`は**TRUE** (レコード セットを空または先頭レコードの前にスクロールしようとしています)、 **m_lCurrentRecord**に設定されている**AFX_CURRENT_RECORD_BOF** (–&1;)。 最初のレコードにし、設定されている場合に 0、2 つ目、1 と記録にします。  
  
- **m_bRecordCountFinal**&0; 以外の場合は、レコード セット内のレコードの合計数を確認します。 レコード セットの先頭から始まりますを呼び出すことにより、その一般にこの記述しなければならない`MoveNext`まで`IsEOF`0 以外を返します。 このメンバーは、0 は場合、によって返されるレコードのカウント`GetRecordCount`いないが-1 でのみ、"high watermark"レコードの場合は、です。  
  
##  <a name="getsql"></a>CRecordset::GetSQL  
 開いたときに、レコード セットのレコードを選択するために使用された SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **const**への参照、 `CString` SQL ステートメントを格納しています。  
  
### <a name="remarks"></a>コメント  
 これは一般に、SQL になります**選択**ステートメントです。 によって返される文字列`GetSQL`は読み取り専用です。  
  
 によって返される文字列`GetSQL`通常とは異なる任意の文字列でレコード セットに渡した場合、`lpszSQL`パラメーターを**開く**メンバー関数。 これは、レコード セットに渡したに基づく完全な SQL ステートメントを作成するため**開く**、したが指定したもので、ClassWizard で指定した、**か**と`m_strSort`データ メンバー、およびすべてのパラメーターを指定する可能性があります。 レコード セットがこの SQL ステートメントを作成する方法の詳細については、記事を参照してください。[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)します。  
  
> [!NOTE]
>  このメンバー関数を呼び出した後にだけ呼び出して[開く](#open)します。  
  
##  <a name="gettablename"></a>CRecordset::GetTableName  
 レコード セットのクエリの基になる SQL テーブルの名前を取得します。  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A **const**への参照、`CString`テーブルを含むレコード セットがテーブルに基づいた、それ以外の場合、空の文字列の名前します。  
  
### <a name="remarks"></a>コメント  
 `GetTableName`有効なは、レコード セットは、複数のテーブルまたは定義済みクエリ (ストアド プロシージャ) の結合ではないテーブルに基づいている場合のみです。 名前とは、読み取り専用です。  
  
> [!NOTE]
>  このメンバー関数を呼び出した後にだけ呼び出して[開く](#open)します。  
  
##  <a name="isbof"></a>CRecordset::IsBOF  
 レコード セットは、最初のレコードの前に位置付けられている場合は&0; 以外を返します。 現在のレコードがありません。  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最初のレコードより前にスクロールした場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 レコードからレコード セットの最初のレコードの前に終了したかどうかを学習するレコードにスクロールする前に、このメンバー関数を呼び出します。 使用することも`IsBOF`と共に`IsEOF`レコード セットをいくつかのレコードが含まれていますが空かを判断します。 呼び出した後すぐに**開く**、レコード セットにレコードが含まれていない場合、 `IsBOF` 0 以外を返します。最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときに、 `IsBOF` 0 を返します。  
  
 呼び出すし、最初のレコードが現在のレコード`MovePrev`、`IsBOF`後以外を返します。 場合`IsBOF`呼び出すと、0 以外を返します`MovePrev`エラーが発生します。 場合`IsBOF`戻り値は&0; 以外の値、現在のレコードが定義されていないと、エラーは、現在のレコードを必要とする任意のアクションが発生します。  
  
### <a name="example"></a>例  
 この例では`IsBOF`と`IsEOF`レコード セットを双方向にスクロールすると、レコード セットの制限を検出します。  
  
 [!code-cpp[NVC_MFCDatabase&#25;](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="isdeleted"></a>CRecordset::IsDeleted  
 現在のレコードが削除されているかどうかを決定します。  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットが削除されたレコードに配置されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 レコードをスクロールする場合と`IsDeleted`返します**TRUE** (ゼロ以外)、スクロールして別のレコードに他のレコード セットの操作を実行する前にします。  
  
 結果`IsDeleted`レコード セットを指定するかどうかが、更新可能かどうか、レコード セットの種類など、さまざまな要因に依存する、 **crecordset::skipdeletedrecords**ドライバー パックは、レコードを削除するかどうか、レコード セットが開かれたときに、複数のユーザーがあるかどうかのオプションです。  
  
 詳細については**crecordset::skipdeletedrecords**し、梱包、ドライバーを参照してください、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  バルク行フェッチを実装している場合は、呼び出す必要はありません`IsDeleted`します。 代わりに、 [GetRowStatus](#getrowstatus)メンバー関数。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="iseof"></a>CRecordset::IsEOF  
 レコード セットは、最後のレコードの後に位置付けられている場合は&0; 以外を返します。 現在のレコードがありません。  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最後のレコードより後にスクロールする場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 レコードからレコード セットの最後のレコードを越えているかどうかについては、レコードをスクロールするときに、このメンバー関数を呼び出します。 使用することも`IsEOF`レコード セットをいくつかのレコードが含まれていますが空かを判断します。 呼び出した後すぐに**開く**、レコード セットにレコードが含まれていない場合、 `IsEOF`&0; 以外を返します。 最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときに、 `IsEOF` 0 を返します。  
  
 最後のレコードが、呼び出されると、現在のレコードかどうか`MoveNext`、`IsEOF`後以外を返します。 場合`IsEOF`呼び出すと、0 以外を返します`MoveNext`エラーが発生します。 場合`IsEOF`戻り値は&0; 以外の値、現在のレコードが定義されていないと、エラーは、現在のレコードを必要とする任意のアクションが発生します。  
  
### <a name="example"></a>例  
 例を参照してください[IsBOF](#isbof)します。  
  
##  <a name="isfielddirty"></a>CRecordset::IsFieldDirty  
 以降、指定されたフィールド データ メンバーが変更されたかどうかを判断[編集](#edit)または[AddNew](#addnew)呼び出されました。  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**がダーティ フィールドのいずれかが判断されます。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーが呼び出し元から変更された場合は 0 以外`AddNew`または**編集**。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 すべてのダーティ フィールド データ メンバー内のデータは上に転送するレコードをデータ ソースへの呼び出しによって現在のレコードが更新されたときに、[更新](#update)のメンバー関数`CRecordset`(の呼び出しに続く**編集**または`AddNew`)。  
  
> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装した場合、バルク行フェッチし、`IsFieldDirty`は常に返す**FALSE**とアサーションは失敗になります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 呼び出す`IsFieldDirty`への呼び出しの前の効果をリセット[き](#setfielddirty)フィールドのダーティ状態が再評価されるためです。 `AddNew`の場合も、現在のフィールド値が擬似の null 値と異なる場合フィールド ステータス ダーティが設定されます。 **編集**場合は、フィールドの値は、フィールドの状態がダーティに設定し、キャッシュされた値とは異なります。 します。  
  
 `IsFieldDirty`によって実装され[DoFieldExchange](#dofieldexchange)します。  
  
 ダーティ フラグの詳細については、記事を参照してください。[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)します。  
  
##  <a name="isfieldnull"></a>CRecordset::IsFieldNull  
 現在のレコードで指定したフィールドが Null の場合は&0; 以外を返します (値を持ちません)。  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL** Null が、フィールドのいずれかが判断されます。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーが Null としてフラグが設定された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を呼び出してレコード セットの指定されたフィールド データ メンバーを Null としてマークされているかどうかを決定します。 (データベース用語では「値を持たない」手段を Null に設定し、同じではありません**NULL** c++)。フィールド データ メンバーが Null としてフラグが設定した場合は、列の値がない現在のレコードのとして解釈されます。  
  
> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装した場合、バルク行フェッチし、`IsFieldNull`は常に返す**FALSE**とアサーションは失敗になります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 `IsFieldNull`によって実装され[DoFieldExchange](#dofieldexchange)します。  
  
##  <a name="isfieldnullable"></a>CRecordset::IsFieldNullable  
 現在のレコードで指定したフィールドに設定できます Null (値がない) 場合は&0; 以外を返します。  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**を Null 値に設定するかどうかは、フィールドのいずれかを判断します。  
  
### <a name="remarks"></a>コメント  
 指定されたフィールド データ メンバーが「null を許容」かどうかを判断する (するには、Null 値に設定しますC++ **NULL** Null の場合、データベース用語では、これと同じではありません「値を持たない」) です。  
  
> [!NOTE]
>  呼び出すことができない場合は、バルク行フェッチを実装している、`IsFieldNullable`です。 代わりに、 [GetODBCFieldInfo](#getodbcfieldinfo)フィールドを Null 値に設定できるかどうかを判断します。 常に呼び出すことのできる注`GetODBCFieldInfo`バルク行フェッチを実装しているかどうかに関係なく、します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 Null 値は、フィールド値が必要です。 このようなフィールドを追加するか、レコードを更新する場合は Null に設定しようとすると、データ ソースは追加や更新を拒否し、[更新](#update)は例外をスローします。 呼び出すときに、例外が発生した**更新**を呼び出すときではなく、[な](#setfieldnull)です。  
  
 使用して**NULL**関数の最初の引数が関数をのみに適用の**outputColumn**フィールドいない**param**フィールドです。 たとえばの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase #&26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドが影響を受けません。  
  
 作業する**param**フィールド、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase #&27;](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**の場合と、 **outputColumn**フィールドです。  
  
 `IsFieldNullable`によって実装され[DoFieldExchange](#dofieldexchange)します。  
  
##  <a name="isopen"></a>CRecordset::IsOpen  
 レコード セットが開かれてかどうかを判断します。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、レコード セット オブジェクトの[開く](#open)または[Requery](#requery)メンバー関数が呼び出されていたとレコード セットが終了していない。 それ以外の場合 0 です。  
  
##  <a name="m_hstmt"></a>CRecordset::m_hstmt  
 型の ODBC ステートメントのデータ構造体へのハンドルを含む**HSTMT**レコード セットに関連付けられている。  
  
### <a name="remarks"></a>コメント  
 ODBC データ ソースには、各クエリに関連付けられて、 **HSTMT**します。  
  
> [!CAUTION]
>  使用しないでください**m_hstmt**する前に[開く](#open)が呼び出されています。  
  
 通常にアクセスする必要はありません、 **HSTMT**を直接 SQL ステートメントの直接の実行にならない場合があります。 `ExecuteSQL`クラスのメンバー関数`CDatabase`を使用する例を提供**m_hstmt**します。  
  
##  <a name="m_nfields"></a>CRecordset::m_nFields  
 レコード セット クラスのフィールド データ メンバーの数が含まれていますつまり、データ ソースからレコード セットが選択した列の数。  
  
### <a name="remarks"></a>コメント  
 レコード セット クラスのコンス トラクターを初期化する必要があります`m_nFields`を正しい値にします。 バルク行フェッチを実装していない場合、ClassWizard は、レコード セット クラスを宣言に使用するときにこの初期化を書き込みます。 手動で記述することもできます。  
  
 フレームワークでは、この番号を使用して、フィールド データ メンバーと、データ ソースの現在のレコードの対応する列の間の相互作用を管理します。  
  
> [!CAUTION]
>  この番号は、[出力列] に登録されているの番号に対応する必要があります`DoFieldExchange`または`DoBulkFieldExchange`への呼び出し後[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)パラメーターと共に**CFieldExchange::outputColumn**します。  
  
 アーティクルの説明に従って、動的に列をバインドすることができます"レコード セット: 動的にバインディングのデータ列です"。 これを行う場合の数の増加する必要があります`m_nFields`呼び出しの rfx 関数または Bulk RFX 関数の数を反映するように、`DoFieldExchange`または`DoBulkFieldExchange`動的にバインドされた列のメンバー関数。  
  
 詳細については、記事を参照してください。[レコード セット: データ列を動的にバインド (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)と[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
### <a name="example"></a>例  
 記事を参照して[レコード フィールド エクス チェンジ: RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)します。  
  
##  <a name="m_nparams"></a>CRecordset::m_nParams  
 レコード セット クラスでパラメーター データ メンバーの数が含まれていますつまり、パラメーターの数は、レコード セットのクエリを使用して渡されます。  
  
### <a name="remarks"></a>コメント  
 レコード セット クラスにパラメーター データ メンバーがある場合、クラスのコンス トラクターを初期化する必要があります`m_nParams`を正しい値にします。 値`m_nParams`既定値は 0 です。 手動でパラメーターの数を反映するようにクラスのコンス トラクターで初期化を追加する必要があります (これは、手動で行う必要があります) のパラメーター データ メンバーを追加する場合 (の数とサイズ以上である必要がありますが ' 内のプレース ホルダー、**か**または`m_strSort`文字列)。  
  
 フレームワークは、レコード セットのクエリをパラメーター化するときに、この番号を使用します。  
  
> [!CAUTION]
>  この番号は、"params"に登録されているの番号に対応する必要があります`DoFieldExchange`または`DoBulkFieldExchange`への呼び出し後[SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype)のパラメーター値を持つ**CFieldExchange::inputParam**、 **CFieldExchange::param**、 **CFieldExchange::outputParam**、または**CFieldExchange::inoutParam**します。  
  
### <a name="example"></a>例  
  記事を参照してください[レコード セット: レコード セット (ODBC) のパラメーターを利用した](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)と[レコード フィールド エクス チェンジ: RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)します。  
  
##  <a name="m_pdatabase"></a>CRecordset::m_pDatabase  
 ポインターを含む、`CDatabase`データ ソースに使用されるレコード セットが接続されているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この変数は、2 つの方法で設定されます。 通常、既に接続されているにポインターを渡す`CDatabase`レコード セット オブジェクトを構築するときのオブジェクトします。 渡した場合**NULL**代わりに、`CRecordset`を作成、`CDatabase`のオブジェクトを接続します。 いずれの場合、`CRecordset`この変数にマウス ポインターを格納します。  
  
 通常は直接不要に格納されているポインターを使用する**m_pDatabase**します。 独自の拡張機能を記述する場合`CRecordset`、ただし、ポインターを使用する必要があります。 たとえば、する必要があります、ポインターをスローする場合、独自`CDBException`秒です。 使用して同じ作業を行う必要がある場合に必要なまたは`CDatabase`実行されるトランザクションのタイムアウト設定、または呼び出しなどのオブジェクト、`ExecuteSQL`クラスのメンバー関数`CDatabase`直接 SQL ステートメントを実行します。  
  
##  <a name="m_strfilter"></a>CRecordset::m_strFilter  
 呼び出す前に、レコード セット オブジェクトを作成した後、**開く**メンバーを格納する、このデータ メンバーを使用して、関数、 `CString` SQL が含まれている**、**句。  
  
### <a name="remarks"></a>コメント  
 レコード セットでは、この文字列を使用して、中に、選択されたレコードを制限 (またはフィルター処理)、**開く**または**Requery**を呼び出します。 これは、「すべての販売員カリフォルニア州在住」など、レコードのサブセットを選択するのに便利です ("の状態 = CA") です。 ODBC SQL 構文、 **、**句は、  
  
 `WHERE search-condition`  
  
 含めないようにすること、 **、**文字列のキーワードです。 フレームワークを提供します。  
  
 配置することで、フィルター文字列をパラメーター化することもできます ' 内のプレース ホルダー、各プレース ホルダーのクラスにパラメーター データ メンバーを宣言して、パラメーターを渡すことでレコード セットには、時間を実行します。 これにより、実行時にフィルターを作成することができます。 詳細については、記事を参照してください。[レコード セット: レコード セット (ODBC) のパラメーターを利用した](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)します。  
  
 SQL の詳細については**、**句、記事を参照して[SQL](../../data/odbc/sql.md)します。 選択して、レコードのフィルター処理する方法の詳細については、記事を参照してください。[レコード セット: レコードのフィルター処理 (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase #&30;](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="m_strsort"></a>CRecordset::m_strSort  
 呼び出す前に、レコード セット オブジェクトを作成した後、**開く**メンバーを格納する、このデータ メンバーを使用して、関数、 `CString` SQL が含まれている**ORDER BY**句。  
  
### <a name="remarks"></a>コメント  
 レコード セットは、この文字列を使用して、並べ替え中に、選択されたレコード、**開く**または**Requery**を呼び出します。 1 つまたは複数の列のレコード セットを並べ替えるには、この機能を使用することができます。 ODBC SQL 構文、 **ORDER BY**句は、  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 ここで並べ替え仕様は、整数値または列名です。 昇順または降順の順序 (既定では、順序は昇順) は、並べ替え文字列内の列リストに"ASC"または"DESC"を追加しても指定できます。 選択されたレコードは、1 秒で、次の最初の列を表示するには、最初に並べ替えられます。 たとえばの順姓、名、"Customers"レコード セットを注文する可能性があります。 一覧表示する列の数は、データ ソースによって異なります。 詳細については、次を参照してください。、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]*します。*  
  
 含めないようにすること、 **ORDER BY**文字列のキーワードです。 フレームワークを提供します。  
  
 SQL 句の詳細については、記事を参照してください。 [SQL](../../data/odbc/sql.md)します。 レコードの並べ替えの詳細については、記事を参照してください。[レコード セット: レコードの並べ替え (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase #&31;](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]  
  
##  <a name="move"></a>CRecordset::Move  
 前方または後方レコード セット内で現在のレコード ポインターを移動します。  
  
```  
virtual void Move(
    long nRows,  
    WORD wFetchType = SQL_FETCH_RELATIVE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRows`  
 前方または後方に移動する行の数。 正の値は、レコード セットの終了に向けて前方移動します。 負の値は、先頭に向かって後方移動します。  
  
 `wFetchType`  
 行セットを決定する**移動**がフェッチされます。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 値 0 を渡す場合`nRows`、**移動**現在のレコードを更新**移動**、現在は終了`AddNew`または**編集**モードでは、前に、現在のレコードの値を復元および`AddNew`または**編集**が呼び出されました。  
  
> [!NOTE]
>  レコード セット間を移動するときに、削除されたレコードをスキップできません。 参照してください[CRecordset::IsDeleted](#isdeleted)の詳細。 開くと、`CRecordset`で、 **skipDeletedRecords**オプションを設定、**移動**場合アサート、`nRows`パラメーターが 0 です。 この動作は、同じデータを使用して他のクライアント アプリケーションが削除される行の更新を防止します。 参照してください、`dwOption`パラメーター[開く](#open)の詳細については**skipDeletedRecords**します。  
  
 **移動**行セットによって、レコード セットの位置を変更します。 値に基づいて`nRows`と`wFetchType`、**移動**適切な行セットをフェッチし、最初のレコードを行セットの現在のレコードです。 バルク行フェッチを実装しない場合、行セットのサイズは常に 1 です。 行セットをフェッチするときに**移動**直接呼び出します、 [CheckRowsetError](#checkrowseterror)フェッチによるエラーを処理するメンバー関数。  
  
 渡した場合、値に応じて**移動**は他のと同じ`CRecordset`メンバー関数。 具体的には、値で`wFetchType`がより直感的にメンバー関数と多くの場合、現在のレコードを移動するための推奨される方法を示すことがあります。  
  
 次の表に、可能な値`wFetchType`、行セットを**移動**がフェッチに基づいて`wFetchType`と`nRows`、およびすべての同等のメンバー関数に対応する`wFetchType`です。  
  
|wFetchType|フェッチされた行セット|同等のメンバー関数|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE`(既定値)|行セットの開始`nRows`行が現在の行セットの最初の行からです。||  
|`SQL_FETCH_NEXT`|次の行セット`nRows`は無視されます。|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|前の行セット`nRows`は無視されます。|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|レコード セットの最初の行セット`nRows`は無視されます。|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|レコード セットの最後の完全な行セット`nRows`は無視されます。|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|場合`nRows`> 0 で始まる行セット`nRows`レコード セットの先頭からの行。 場合`nRows` < 0,="" the="" rowset="" starting=""> `nRows` 、レコード セットの末尾から行です。 場合`nRows`= 0、最初のファイル (BOF) 状態が返されます。|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|ブックマーク値を持つに対応する行で始まる行セット`nRows`します。|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  順方向専用レコード セットの**移動**はの値でのみ有効`SQL_FETCH_NEXT`の`wFetchType`です。  
  
> [!CAUTION]
>  呼び出す**移動**レコード セットにレコードが存在しない場合は例外をスローします。 いくつかのレコードをレコード セットが存在するかどうかを確認するのには、呼び出す[IsBOF](#isbof)と[IsEOF](#iseof)します。  
  
> [!NOTE]
>  先頭またはレコード セットの末尾を越えてスクロールした場合 (`IsBOF`または`IsEOF`0 以外を返します) を呼び出す、**移動**関数がスローする可能性があります、`CDBException`です。 たとえば場合、 `IsEOF`&0; 以外を返しますと`IsBOF`していない`MoveNext`、例外がスローされますが、`MovePrev`されません。  
  
> [!NOTE]
>  呼び出した場合**移動**現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 レコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。 関連情報については、ODBC API 関数を参照してください。 **SQLExtendedFetch**で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase #&28;](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="movefirst"></a>CRecordset::MoveFirst  
 最初のレコードの最初の行セットに使用すると、現在のレコードです。  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>コメント  
 かどうかバルク行フェッチが実装されてに関係なくこれは常に、レコード セット内の最初のレコードです。  
  
 呼び出す必要はありません**MoveFirst**レコード セットを開いた直後にします。 その時点では、最初のレコードが (もしあれば) と、現在のレコードでは自動的にです。  
  
> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。  
  
> [!NOTE]
>  レコード セット間を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 いくつかのレコードをレコード セットが存在するかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 レコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
### <a name="example"></a>例  
  例を参照してください[IsBOF](#isbof)します。  
  
##  <a name="movelast"></a>CRecordset::MoveLast  
 現在のレコードを最後の完全な行セットの最初のレコードに位置付けます。  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>コメント  
 バルク行フェッチを実装しない場合、レコード セットがあり、行セットのサイズは 1、その`MoveLast`レコード セットにレコード移動最後です。  
  
> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。  
  
> [!NOTE]
>  レコード セット間を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 いくつかのレコードをレコード セットが存在するかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 レコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
### <a name="example"></a>例  
  例を参照してください[IsBOF](#isbof)します。  
  
##  <a name="movenext"></a>CRecordset::MoveNext  
 現在のレコードを次の行セットの最初のレコードに位置付けます。  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>コメント  
 バルク行フェッチを実装しない場合、レコード セットがあり、行セットのサイズは 1、その`MoveNext`単純に次のレコードに移動します。  
  
> [!NOTE]
>  レコード セット間を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 いくつかのレコードをレコード セットが存在するかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  呼び出すことは推奨も`IsEOF`呼び出す前に`MoveNext`します。 たとえば、レコード セットの末尾までスクロールした`IsEOF`は&0; 以外を返します後続の呼び出しに`MoveNext`例外がスローされます。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 レコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
### <a name="example"></a>例  
  例を参照してください[IsBOF](#isbof)します。  
  
##  <a name="moveprev"></a>CRecordset::MovePrev  
 現在のレコードを前の行セットの最初のレコードに位置付けます。  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>コメント  
 バルク行フェッチを実装しない場合、レコード セットがあり、行セットのサイズは 1、その`MovePrev`前のレコードに移動します。  
  
> [!NOTE]
>  前方スクロール専用レコードのこのメンバー関数が正しくありません。  
  
> [!NOTE]
>  レコード セット間を移動するときに、削除されたレコードをスキップできません。 参照してください、 [IsDeleted](#isdeleted)詳細については、メンバー関数。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 いくつかのレコードをレコード セットが存在するかどうかを確認するのには、呼び出す`IsBOF`と`IsEOF`です。  
  
> [!NOTE]
>  呼び出すことは推奨も`IsBOF`呼び出す前に`MovePrev`します。 たとえば、レコード セットの先頭にスクロールして`IsBOF`は&0; 以外を返します後続の呼び出しに`MovePrev`例外がスローされます。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 レコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
### <a name="example"></a>例  
  例を参照してください[IsBOF](#isbof)します。  
  
##  <a name="onsetoptions"></a>CRecordset::OnSetOptions  
 指定された ODBC ステートメントには、(選択に使用する) オプションを設定すると呼ばれます。  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 `hstmt`  
 **HSTMT**の ODBC ステートメント オプションでは、設定します。  
  
### <a name="remarks"></a>コメント  
 呼び出す`OnSetOptions`を指定した ODBC ステートメントのオプション (選択に使用される) を設定します。 フレームワークでは、レコード セットの最初のオプションを設定するには、このメンバー関数を呼び出します。 `OnSetOptions`スクロール可能なカーソルとカーソルの同時実行のデータ ソースのサポートを決定し、レコード セットのオプションを設定します。 (一方`OnSetOptions`選択操作のために使用`OnSetUpdateOptions`更新操作のために使用します)。  
  
 オーバーライド`OnSetOptions`ドライバーまたはデータ ソースに固有のオプションを設定します。 たとえば、オーバーライド場合は、データ ソースの排他アクセスで開くことをサポート、`OnSetOptions`その機能を利用するためにします。  
  
 カーソルの詳細については、記事を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)します。  
  
##  <a name="onsetupdateoptions"></a>CRecordset::OnSetUpdateOptions  
 指定された ODBC ステートメントのオプション (更新時に使用される) を設定すると呼ばれます。  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>パラメーター  
 `hstmt`  
 **HSTMT**の ODBC ステートメント オプションでは、設定します。  
  
### <a name="remarks"></a>コメント  
 呼び出す`OnSetUpdateOptions`を指定した ODBC ステートメントのオプション (更新時に使用される) を設定します。 フレームワークは、レコード セットからレコードを更新する HSTMT が作成された後に、このメンバー関数を呼び出します。 (一方`OnSetOptions`選択操作のために使用`OnSetUpdateOptions`更新操作のために使用します)。`OnSetUpdateOptions`スクロール可能なカーソルとカーソルの同時実行のデータ ソースのサポートを決定し、レコード セットのオプションを設定します。  
  
 オーバーライド`OnSetUpdateOptions`をそのステートメントを使用して、データベースにアクセスする前に、ODBC ステートメントのオプションを設定します。  
  
 カーソルの詳細については、記事を参照してください。 [ODBC](../../data/odbc/odbc-basics.md)します。  
  
##  <a name="open"></a>:Open  
 テーブルを取得するか、レコードセットが表すクエリを実行して、レコードセットを開きます。  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOpenType`  
 既定値をそのまま**AFX_DB_USE_DEFAULT_TYPE**、または、次のいずれかの値を使用、 **enum OpenType**:  
  
- **:Dynaset**双方向にスクロールできるレコード セット。 レコードのメンバーシップおよび順序は、レコードセットを開いたときに決定されますが、他のユーザーによるデータ値の変更は、フェッチ操作後に表示されます。 ダイナセットは、キーセット ドリブン レコードセットとも呼ばれます。  
  
- **Crecordset::snapshot**双方向にスクロールできる静的レコード セット。 レコードのメンバーシップと順序は、レコードセットを開いたときに決定されます。データ値は、レコードをフェッチしたときに決定されます。 他のユーザーが行った変更は、レコードセットを閉じてから再度開くまで表示されません。  
  
- **:Dynamic**双方向にスクロールできるレコード セット。 他のユーザーが行ったメンバーシップ、順序、およびデータ値の変更は、フェッチ操作後に表示されます。 多くの ODBC ドライバーでは、この型のレコードセットはサポートされていません。  
  
- **Crecordset::forwardonly**前方スクロールのみが読み取り専用レコード セット。  
  
     `CRecordset`、既定値は**crecordset::snapshot**します。 既定値の機構により、Visual C++ ウィザードで既定値の異なる ODBC `CRecordset` と DAO `CDaoRecordset` 両方を操作できます。  
  
 これらのレコード セットの型の詳細については、記事を参照してください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)します。 関連情報については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] の「Using Block and Scrollable Cursors (ブロックとスクロール可能なカーソルの使用)」を参照してください。  
  
> [!CAUTION]
>  要求した型がサポートされていない場合、例外がスローされます。  
  
 `lpszSQL`  
 次のいずれかを含む文字列ポインター:  
  
-   A **NULL**ポインター。  
  
-   テーブルの名前。  
  
-   SQL**選択**ステートメント (必要に応じて、SQL で**場所**または**ORDER BY**句)。  
  
-   A**呼び出す**定義済みクエリ (ストアド プロシージャ) の名前を指定します。 中かっこの間にスペースを入れないように注意してください、**呼び出す**キーワードです。  
  
 この文字列の詳細については、「解説」の表と ClassWizard のロールの説明を参照してください。  
  
> [!NOTE]
>  結果セット内の列の順序は、RFX の順序に一致する必要がありますまたは Bulk RFX 関数の呼び出し、 [DoFieldExchange](#dofieldexchange)または[DoBulkFieldExchange](#dobulkfieldexchange)関数オーバーライドします。  
  
 `dwOptions`  
 以下に示す値の組み合わせを指定できるビットマスク。 これらの値の一部は同時に指定できません。 既定値は**none**します。  
  
- **Crecordset::none**オプションが設定されていません。 このパラメーター値は、他のすべての値と同時に指定できません。 既定では、レコード セットを更新すると[編集](#edit)または[削除](#delete)し、使用して新しいレコードを追加できます[AddNew](#addnew)します。 更新できるかどうかは、データ ソースと指定する `nOpenType` オプションによって異なります。 バルク追加の最適化は使用できません。 バルク行フェッチは実装されません。 削除されたレコードはレコードセットの移動中にスキップされません。 ブックマークは使用できません。 自動ダーティ フィールド チェックが実装されます。  
  
- **Crecordset::appendonly**を許可しない**編集**または**削除**レコード セットでします。 `AddNew` のみ実行できます。 このオプションは相互に排他的な**crecordset::readonly**します。  
  
- **Crecordset::readonly**レコード セットを読み取り専用として開きます。 このオプションは相互に排他的な**crecordset::appendonly**します。  
  
- **Crecordset::optimizebulkadd**同時に多数のレコードを追加する方法を最適化するために準備された SQL ステートメントを使用します。 ODBC API 関数を使用していない場合にのみ適用されます**SQLSetPos**をレコード セットを更新します。 最新の更新で、ダーティとマークされるフィールドが決まります。 このオプションは `CRecordset::useMultiRowFetch` と同時に指定できません。  
  
- `CRecordset::useMultiRowFetch`複数の行を&1; 回のフェッチ操作で取得するようにするバルク行フェッチを実装します。 これは、パフォーマンスを向上するために設計された拡張機能です。ただし、バルク レコード フィールド エクスチェンジは ClassWizard ではサポートされていません。 このオプションは相互に排他的な**crecordset::optimizebulkadd**します。 指定した場合`CRecordset::useMultiRowFetch`、オプションでは、 **crecordset::nodirtyfieldcheck**自動的に有効 (ダブル バッファリングは使用できません)。 前方スクロール専用レコード セットをオプションで**crecordset::useextendedfetch**自動的に有効です。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
- **Crecordset::skipdeletedrecords**レコード セット内を移動するときに削除されたすべてのレコードをスキップします。 これにより、特定の相対フェッチでパフォーマンスが低下します。 このオプションは前方スクロール専用レコードセットでは無効です。 呼び出した場合[移動](#move)で、`nRows`パラメーターを 0 に設定と**crecordset::skipdeletedrecords**オプションを設定、**移動**はアサートします。 注意**crecordset::skipdeletedrecords**のような*ドライバーによるパック*行を削除することを示しますが、レコード セットから削除されます。 ただし、ドライバーによってレコードがパックされる場合、ユーザー自身が削除するレコードだけがスキップされます。レコードセットを開いている間に他のユーザーによって削除されたレコードはスキップされません。 **Crecordset::skipdeletedrecords**は他のユーザーによって削除された行をスキップします。  
  
- **Crecordset::usebookmarks**サポートされている場合、レコード セットでブックマークの使用可能性があります。 ブックマークを使用すると、データの取得速度は低下しますが、データ移動のパフォーマンスが向上します。 前方スクロール専用レコードセットでは無効です。 詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。  
  
- **Crecordset::nodirtyfieldcheck**自動ダーティ フィールド チェック (ダブル バッファリング) をオフにします。 これにより、パフォーマンスは向上しますが、`SetFieldDirty` メンバー関数と `SetFieldNull` メンバー関数を呼び出して手動でフィールドをダーティとしてマークする必要があります。`CRecordset` クラスのダブル バッファリングは、`CDaoRecordset` クラスのダブル バッファリングに似ています。 ただし、`CRecordset` では、個別のフィールドに対してダブル バッファリングを有効にできません。すべてのフィールドに対して有効にするか、またはすべてのフィールドに対して無効にします。 オプションを指定する場合は、 `CRecordset::useMultiRowFetch`、し**crecordset::nodirtyfieldcheck**はオンになります。 ただし、、自動的に`SetFieldDirty`と`SetFieldNull`バルク行フェッチを実装しているレコード セットでは使用できません。  
  
- **:Executedirect**準備された SQL ステートメントを使用しません。 パフォーマンスを向上させる場合にこのオプションを指定、 **Requery**メンバー関数は呼び出されません。  
  
- **Crecordset::useextendedfetch**実装**SQLExtendedFetch**の代わりに**SQLFetch**します。 これは、前方スクロール専用レコードセットに対してバルク行フェッチを実装するために設計されています。 オプションを指定する場合は、`CRecordset::useMultiRowFetch`順方向専用レコード セットに対して、し**crecordset::useextendedfetch**自動的に有効です。  
  
- **Crecordset::userallocmultirowbuffers**ユーザーは、データの格納バッファーを割り当てます。 独自の格納バッファーを割り当てる場合は、このオプションと一緒に `CRecordset::useMultiRowFetch` を使用します。使用しない場合、必要な格納バッファーが自動的に割り当てられます。 詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。 指定することに注意してください**crecordset::userallocmultirowbuffers**を指定せず`CRecordset::useMultiRowFetch`アサーションは失敗になります。  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CRecordset`オブジェクトが正常に開かれている以外の場合は 0 [cdatabase::open](../../mfc/reference/cdatabase-class.md#open) (と呼ばれる) 場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 レコードセットによって定義されたクエリを実行するには、このメンバー関数を呼び出す必要があります。 呼び出しの前に**開く**、レコード セット オブジェクトを構築する必要があります。  
  
 このレコード セットの接続は、データ ソースが呼び出す前に、レコード セットを作成する方法に依存**開く**します。 渡した場合、 [CDatabase](../../mfc/reference/cdatabase-class.md)このメンバー関数を使用してオブジェクトがデータ ソースに接続されていないレコード セットのコンス トラクターを[GetDefaultConnect](#getdefaultconnect)データベース オブジェクトを開こうとします。 渡した場合**NULL**コンス トラクターを作成、レコード セットのコンス トラクターに、 `CDatabase` 、オブジェクトと**開く**データベース オブジェクトの接続を試みます。 レコード セットとさまざまな状況で接続を閉じる方法の詳細については、次を参照してください。[閉じる](#close)します。  
  
> [!NOTE]
>  `CRecordset` オブジェクトを使用したデータ ソースへのアクセスは常に共有されます。 `CDaoRecordset` クラスとは異なり、`CRecordset` オブジェクトを使用して排他アクセスでデータ ソースを開くことはできません。  
  
 呼び出すと**開く**、クエリ、通常、SQL**選択**ステートメントの次の表に示す条件に基づいてレコードを選択します。  
  
|lpszSQL パラメーターの値|レコードの選択基準|例|  
|------------------------------------|----------------------------------------|-------------|  
|**NULL**|`GetDefaultSQL` の返す文字列。||  
|SQL テーブル名|`DoFieldExchange` または `DoBulkFieldExchange` のテーブル リストのすべての列。|`"Customer"`|  
|定義済みクエリ (ストアド プロシージャ) の名前|返すためにクエリが定義された列。|`"{call OverDueAccts}"`|  
|**選択**列リスト**FROM**テーブル リスト|指定したテーブルの指定した列。|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  SQL 文字列に余分な空白を挿入しないでください。 中かっこの間にスペースを挿入する場合など、**を呼び出す**キーワード、MFC は SQL 文字列をテーブル名を誤って解釈およびに組み込むため、**選択**スローされる例外の原因となるステートメント。 同様に、定義済みクエリでは、出力パラメーターを使用する場合は、空白を挿入しないで、中かっこの間で、' シンボルです。 中かっこの前に空白を挿入する最後に、必要があります、**を呼び出す**ステートメントまたは前に、**選択**でキーワード、**選択**ステートメントです。  
  
 通常のプロシージャでは**NULL**に**開く**この例では**開く**呼び出し[GetDefaultSQL](#getdefaultsql)します。 派生を使用している場合は、`CRecordset`クラス、 **GetDefaultSQL** ClassWizard で指定したテーブル名を提供します。 代わりに、その他の情報を `lpszSQL` パラメーターに指定できます。  
  
 何を渡した**開く**クエリの最終的な SQL 文字列を構築 (SQL も**、**と**ORDER BY**句が追加された、`lpszSQL`文字列が渡されました) し、そのクエリを実行します。 呼び出して、作成された文字列を調べることができます[GetSQL](#getsql)呼び出した後**開く**します。 詳細については、レコード セットの SQL ステートメントの作成方法と、レコードの選択は、記事を参照してください。[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)します。  
  
 レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 フィルターや並べ替えなど、レコード セットのオプションを設定する場合は、指定これらを呼び出す前に、レコード セット オブジェクトを作成した後**開く**します。 レコード セットが開いて、レコード セット内のレコードを更新する場合は、呼び出す[Requery](#requery)します。  
  
 などの他の例の詳細については、記事を参照してください。[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)、[レコード セット: レコード選択のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)、および[レコード セット: の生成と破棄 (ODBC) のレコード セット](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)します。  
  
### <a name="example"></a>例  
 次のコード例の別のフォームを表示する、**開く**呼び出します。  
  
 [!code-cpp[NVC_MFCDatabase&#16;](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]  
  
##  <a name="refreshrowset"></a>CRecordset::RefreshRowset  
 データと現在の行セット内の行の状態を更新します。  
  
```  
void RefreshRowset(
    WORD wRow,  
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>パラメーター  
 `wRow`  
 1 から始まる位置の行の現在の行セット。 この値の範囲は&0;、行セットのサイズにします。  
  
 `wLockType`  
 更新された後に、行をロックする方法を示す値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 ゼロの値を渡す場合`wRow`、行セット内のすべての行が更新されます。  
  
 使用する`RefreshRowset`を指定してバルク行フェッチを実装している必要があります、 **CRecordset::useMulitRowFetch**オプション、[開く](#open)メンバー関数。  
  
 `RefreshRowset`ODBC API 関数を呼び出す**SQLSetPos**します。 `wLockType`パラメーターを指定した後の行のロック状態**SQLSetPos**が実行されます。 次の表に、可能な値`wLockTyp`e。  
  
|wLockType|説明|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(既定値)|ドライバーまたはデータ ソースにより、行は前に、と同じロックまたはロック解除の状態が`RefreshRowset`呼び出されました。|  
|`SQL_LOCK_EXCLUSIVE`|ドライバーまたはデータ ソースは、専用の行をロックします。 すべてのデータ ソースは、この種類のロックをサポートします。|  
|`SQL_LOCK_UNLOCK`|ドライバーまたはデータ ソースには、行がロック解除します。 すべてのデータ ソースは、この種類のロックをサポートします。|  
  
 詳細については**SQLSetPos**を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="requery"></a>:Requery  
 (更新) を再構築、レコード セット。  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットが正常に再構築された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 追加と削除やその他のユーザーがデータ ソースに対して実行するを反映するように、レコード セットを呼び出してレコード セットをリビルドする必要があります**Requery**します。 レコード セットがダイナセットの場合は、自動的に、その既存のレコード (ただし追加は除きます) に対してや他のユーザーが行った更新を反映します。 レコード セットがスナップショットである場合は、呼び出す必要があります**Requery**編集内容を他のユーザーだけでなく追加および削除を反映するようにします。  
  
 ダイナセットまたはスナップショットのどちらかを呼び出して**Requery**いつでも新しいフィルターや並べ替え、または新しいパラメーター値を使用してレコード セットを再構築が必要です。 新しい値を割り当てることによって新しいフィルターまたは並べ替えのプロパティを設定**か**と`m_strSort`呼び出す前に**Requery**します。 新しい値を呼び出す前にパラメーター データ メンバーに割り当てることで新しいパラメーターを設定**Requery**します。 フィルターと並べ替え文字列が変更されていない場合は、パフォーマンスが向上すると、クエリを再利用できます。  
  
 レコード セットを再構築に失敗した場合、レコード セットは閉じられます。 呼び出す前に**Requery**を呼び出して、レコード セットを表示できるかどうかを指定できます、`CanRestart`メンバー関数。 `CanRestart`限りませんが**Requery**は成功します。  
  
> [!CAUTION]
>  呼び出す**Requery**を呼び出した後にのみ[開く](#open)します。  
  
### <a name="example"></a>例  
 この例では、さまざまな並べ替え順序を適用するレコード セットが再構築します。  
  
 [!code-cpp[NVC_MFCDatabase #&29;](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="setabsoluteposition"></a>CRecordset::SetAbsolutePosition  
 指定されたレコード番号に対応するレコードは、レコード セットに配置します。  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>パラメーター  
 `nRows`  
 1 から始まる序数位置、現在のレコードのレコード セット。  
  
### <a name="remarks"></a>コメント  
 `SetAbsolutePosition`この序数位置に基づいて、現在のレコード ポインターを移動します。  
  
> [!NOTE]
>  このメンバー関数は前方スクロール専用レコードでは無効です。  
  
 ODBC レコード セットの絶対位置は 1 に設定は、レコード セットの最初のレコードを指します0 の設定は、ファイルの先頭 (BOF) の位置を参照します。  
  
 負の値を渡すこともできます`SetAbsolutePosition`します。 この場合、レコード セットの位置は、レコード セットの末尾から評価されます。 たとえば、`SetAbsolutePosition( -1 )`レコード セットの最後のレコードを現在のレコードのポインターを移動します。  
  
> [!NOTE]
>  絶対位置は、レコード番号の代わりとして使用するものではありません。 ブックマークは、まだ保持し、レコードの位置の変更前のレコードが削除されたときから、指定された位置に戻ることをお勧めです。 さらを保証できません特定のレコードがある絶対位置を同じ場合は、レコード セットを再作成を使用して SQL ステートメントを使用して作成された場合を除き、レコード セット内の各レコードの順序は保証されないため、 **ORDER BY**句。  
  
 レコード セットの移動とブックマークの詳細については、記事を参照してください。[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)と[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)します。  
  
##  <a name="setbookmark"></a>CRecordset::SetBookmark  
 指定されたブックマークを含むレコードをレコード セットに配置します。  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 `varBookmark`  
 参照、 [CDBVariant](../../mfc/reference/cdbvariant-class.md)特定のレコードのブックマークの値を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 調べるには、レコード セットでブックマークがサポートされているかどうか、呼び出す[調べる](#canbookmark)します。 ブックマークを使用できるようにサポートされている場合に設定する必要があります、 **crecordset::usebookmarks**オプション、`dwOptions`のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  ブックマークがサポートされていないか使用できない場合、呼び出す`SetBookmark`スローされた例外が発生します。 ブックマークは、順方向専用レコード セットではサポートされていません。  
  
 最初に現在のレコードのブックマークを取得する[GetBookmark](#getbookmark)、ブックマークの値を保存、`CDBVariant`オブジェクトです。 呼び出してそのレコードを返すことができます、後で`SetBookmark`保存したブックマークの値を使用します。  
  
> [!NOTE]
>  レコード セットの特定の操作後に、呼び出す前にブックマークの永続性をチェックする必要があります`SetBookmark`します。 持つブックマークを取得する場合など`GetBookmark`し、呼び出す**Requery**ブックマークは有効でなくなる可能性があります。 呼び出す[CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence)を安全に呼び出すことができるかどうかを確認する`SetBookmark`です。  
  
 ブックマークとレコード セットの移動に関する詳細については、記事を参照してください。[レコード セット: ブックマークと絶対位置 (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)と[レコード セット: スクロール (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)します。  
  
##  <a name="setfielddirty"></a>CRecordset::SetFieldDirty  
 未変更または変更されたレコード セットのフィールド データ メンバーのフラグを設定します。  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 レコード セット内のフィールド データ メンバーのアドレスを格納または**NULL**します。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では「値を持たない」という意味)。  
  
 `bDirty`  
 **TRUE**かどうか、フィールド データ メンバーは「ダーティ」(変更されている) としてフラグが付けられます。 それ以外の場合**FALSE**かどうか、フィールド データ メンバーは「クリーン」(変更されていない) としてフラグが付けられます。  
  
### <a name="remarks"></a>コメント  
 未変更としてフィールドをマークすることにより、フィールドが更新されない結果、SQL トラフィックも少なくて済みます。  
  
> [!NOTE]
>  このメンバー関数では、バルク行フェッチを使用しているレコード セットに適用されません。 実装した場合、バルク行フェッチし、`SetFieldDirty`アサーションは失敗になります。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 フレームワークでは、確実にレコード フィールド エクス (チェンジ RFX) メカニズムによって、データ ソースのレコードに書き込まれる、フィールド データ メンバーを変更します。 フィールドの値を変更すると、通常フィールドを設定、ダーティ、自動的を呼び出す必要があります頻度の低い`SetFieldDirty`が自分で場合もありますようにすることも、列が明示的に更新または挿入するフィールド データ メンバーがどのような値に関係なく。  
  
> [!CAUTION]
>  呼び出した後にのみ、このメンバー関数を呼び出して[編集](#edit)または[AddNew](#addnew)します。  
  
 使用して**NULL**関数の最初の引数が関数をのみに適用の**outputColumn**フィールドいない**param**フィールドです。 たとえばの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase #&26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドが影響を受けません。  
  
 作業する**param**フィールド、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase #&27;](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**の場合と、 **outputColumn**フィールドです。  
  
##  <a name="setfieldnull"></a>CRecordset::SetFieldNull  
 Null (値を持たない)、または Null として、レコード セットのフィールド データ メンバーのフラグを設定します。  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 レコード セット内のフィールド データ メンバーのアドレスを格納または**NULL**します。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では「値を持たない」という意味)。  
  
 `bNull`  
 以外の場合は、フィールド データ メンバーは、値 (Null) がないものとしてフラグが付けられます。 フィールド データ メンバーは、Null としてフラグを設定する場合は、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 新しいレコードをレコード セットに追加するときにすべてのフィールド データ メンバーは最初に Null 値に設定され「ダーティ」(変更されている) フラグが付けられます。 データ ソースからレコードを取得するときにその列既に値があるかは Null です。  
  
> [!NOTE]
>  バルク行フェッチを使用しているレコード セットでこのメンバー関数を呼び出す必要はありません。 バルク行フェッチを実装している場合は、呼び出す`SetFieldNull`アサーションの失敗が発生します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 具体的に呼び出して、値を持っていない現在のレコードのフィールドを指定したい場合`SetFieldNull`と`bNull`に設定**TRUE**に Null としてフラグを設定します。 Null フィールドが対象としてマーク済みしようとしています、値を指定する場合は、単にその新しい値を設定します。 Null フラグを削除する必要はありません`SetFieldNull`します。 フィールドの null が許可されたかどうかを確認するのには、呼び出す`IsFieldNullable`します。  
  
> [!CAUTION]
>  呼び出した後にのみ、このメンバー関数を呼び出して[編集](#edit)または[AddNew](#addnew)します。  
  
 使用して**NULL**関数の最初の引数が関数をのみに適用の**outputColumn**フィールドいない**param**フィールドです。 たとえばの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase #&26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドが影響を受けません。  
  
 作業する**param**フィールド、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase #&27;](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**の場合と、 **outputColumn**フィールドです。  
  
> [!NOTE]
>  Null の場合への呼び出しにパラメーターを設定するときに`SetFieldNull`レコード アサーションで開かれている結果セットが前にします。 この場合、 [SetParamNull](#setparamnull)します。  
  
 `SetFieldNull`によって実装され[DoFieldExchange](#dofieldexchange)します。  
  
##  <a name="setlockingmode"></a>CRecordset::SetLockingMode  
 ロック (既定)「オプティミスティック」または「排他的」ロックのロック モードを設定します。 更新プログラムのレコードをロックする方法を決定します。  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>パラメーター  
 `nMode`  
 次の値の&1; つ含まれる、 **enum LockMode**:  
  
- **オプティミスティック**への呼び出し中にのみ更新されるレコードをロックするオプティミスティック ロック**更新**します。  
  
- **ペシミスティック**、レコードをロックして排他的ロックとすぐに**編集**と呼びます。 維持までの間、**更新**呼び出しが完了するか、新しいレコードに移動します。  
  
### <a name="remarks"></a>コメント  
 レコード セットが更新プログラムを使用して&2; つのレコードのロックの戦略を指定する必要がある場合は、このメンバー関数を呼び出します。 レコード セットのロック モードは、既定では、**オプティミスティック**します。 変更するにはより慎重に**ペシミスティック**戦略をロックします。 呼び出す`SetLockingMode`を構築して、レコード セット オブジェクトを開いた後を呼び出す前に**編集**します。  
  
##  <a name="setparamnull"></a>CRecordset::SetParamNull  
 Null (値を持たない)、または Null としてパラメーターのフラグを設定します。  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 パラメーターの&0; から始まるインデックス。  
  
 `bNull`  
 場合**TRUE** (既定値) の場合は、パラメーターが Null としてフラグが付けられます。 それ以外の場合、パラメーターは Null と見なされます。  
  
### <a name="remarks"></a>コメント  
 異なり[な](#setfieldnull)、呼び出すことができます`SetParamNull`レコード セットを開く前にします。  
  
 `SetParamNull`定義済みクエリ (ストアド プロシージャ) で通常使用されます。  
  
##  <a name="setrowsetcursorposition"></a>CRecordset::SetRowsetCursorPosition  
 現在の行セット内の行にカーソルを移動します。  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>パラメーター  
 `wRow`  
 1 から始まる位置の行の現在の行セット。 この値の範囲は 1、行セットのサイズにします。  
  
 `wLockType`  
 更新された後に、行をロックする方法を示す値。 詳細については、「解説」を参照してください。  
  
### <a name="remarks"></a>コメント  
 バルク行フェッチを実装する場合は、レコードが現在のレコードをフェッチした行セットの最初のレコードがここでは、行セットによって取得されます。 行セット内の別のレコードを現在のレコードのために呼び出す`SetRowsetCursorPosition`します。 たとえば、結合`SetRowsetCursorPosition`で、 [GetFieldValue](#getfieldvalue)レコード セットの任意のレコードからデータを動的に取得するメンバー関数。  
  
 使用する`SetRowsetCursorPosition`を指定してバルク行フェッチを実装している必要があります、`CRecordset::useMultiRowFetch`のオプション、`dwOptions`内のパラメーター、[開く](#open)メンバー関数。  
  
 `SetRowsetCursorPosition`ODBC API 関数を呼び出す**SQLSetPos**します。 `wLockType`パラメーターを指定した後の行のロック状態**SQLSetPos**が実行されます。 次の表に、可能な値`wLockTyp`e。  
  
|wLockType|説明|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(既定値)|ドライバーまたはデータ ソースにより、行は前に、と同じロックまたはロック解除の状態が`SetRowsetCursorPosition`呼び出されました。|  
|`SQL_LOCK_EXCLUSIVE`|ドライバーまたはデータ ソースは、専用の行をロックします。 すべてのデータ ソースは、この種類のロックをサポートします。|  
|`SQL_LOCK_UNLOCK`|ドライバーまたはデータ ソースには、行がロック解除します。 すべてのデータ ソースは、この種類のロックをサポートします。|  
  
 詳細については**SQLSetPos**を参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="setrowsetsize"></a>CRecordset::SetRowsetSize  
 フェッチ中に取得するレコードの数を指定します。  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwNewRowsetSize*  
 回のフェッチ時に取得する行の数。  
  
### <a name="remarks"></a>コメント  
 この仮想メンバー関数では、バルク行フェッチを使用する場合は、1 回のフェッチ時に取得する行の数を指定します。 バルク行フェッチを実装するのに設定する必要があります、`CRecordset::useMultiRowFetch`オプション、`dwOptions`のパラメーター、[開く](#open)メンバー関数。  
  
> [!NOTE]
>  呼び出す`SetRowsetSize`一括を実装することがなく、失敗したアサーションの行フェッチが発生します。  
  
 呼び出す`SetRowsetSize`呼び出す前に**開く**を最初に、レコード セットの行セットのサイズを設定します。 バルク行フェッチを実装する際の既定の行セット サイズは 25 です。  
  
> [!NOTE]
>  呼び出すときに警告を使用して`SetRowsetSize`します。 データの記憶域を手動で割り当てている場合 (で指定されたとおり、 **crecordset::userallocmultirowbuffers** dwOptions パラメーターのオプション**開く**) を呼び出した後は、配列の格納バッファーを再割り当てする必要があるかどうかを確認する必要があります`SetRowsetSize`、カーソル ナビゲーション操作を実行する前にします。  
  
 行セットのサイズの現在の設定を取得するを呼び出す[GetRowsetSize](#getrowsetsize)します。  
  
 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
##  <a name="update"></a>CRecordset::Update  
 完了すると、`AddNew`または**編集**データ ソースに新しいまたは更新されたデータを保存することによって操作します。  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は 1 つのレコードが正常に更新されました。列が変更されていない場合は、それ以外の場合 0 を返します。 レコードが更新されない、または&1; つのレコードが更新された数より多い場合、例外がスローされます。 例外は、データ ソースでその他の障害にもスローされます。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を呼び出した後、 [AddNew](#addnew)または[編集](#edit)メンバー関数。 この呼び出しが完了するために必要な`AddNew`または**編集**操作します。  
  
> [!NOTE]
>  呼び出すことができない場合は、バルク行フェッチを実装している、**更新**します。 これにより、失敗したアサーションが発生します。 クラス`CRecordset`メカニズムが用意されていないデータの一括行を更新するには、ODBC API 関数を使用して、独自の関数を記述することができます**SQLSetPos**します。 バルク行フェッチの詳細については、記事を参照してください。[レコード セット: レコードのフェッチ (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)します。  
  
 両方とも`AddNew`と**編集**データ ソースに保存するための追加または編集したデータが置かれている編集バッファーを準備します。 **更新プログラム**データを保存します。 マークまたは変更されたものとして検出されたフィールドのみが更新されます。  
  
 データ ソースは、トランザクションをサポートする場合は、**更新**を呼び出す (およびその対応する`AddNew`または**編集**呼び出し)、トランザクションの一部です。 トランザクションの詳細については、記事を参照してください。[トランザクション (ODBC)](../../data/odbc/transaction-odbc.md)します。  
  
> [!CAUTION]
>  呼び出した場合**更新**最初にいずれかの操作を呼び出すこと`AddNew`または**編集**、**更新**スロー、`CDBException`です。 呼び出した場合`AddNew`または**編集**、呼び出す必要があります**更新**を呼び出す前に、**移動**操作、またはレコード セットまたはデータ ソース接続を閉じる前にします。 それ以外の場合、変更は、警告を表示せず失われます。  
  
 処理の詳細**更新**エラーの場合は、記事を参照して[レコード セット: レコード更新のしくみ (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)します。  
  
### <a name="example"></a>例  
 記事を参照して[トランザクション: レコード セット (ODBC) でのトランザクションを実行する](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDatabase クラス](../../mfc/reference/cdatabase-class.md)   
 [CRecordView クラス](../../mfc/reference/crecordview-class.md)

