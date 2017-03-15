---
title: "CDaoRecordset クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoRecordset
dev_langs:
- C++
helpviewer_keywords:
- recordsets, types
- CDaoRecordset class
- records, CDaoRecordSet
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
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
ms.openlocfilehash: 3d3d830a7d423a2653819e9cbf160538e486cfb0
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorecordset-class"></a>CDaoRecordset クラス
データ ソースから選択された&1; 組のレコードセットを表現します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoRecordset : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|`CDaoRecordset` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordset::AddNew](#addnew)|新しいレコードを追加する準備をします。 呼び出す[更新](#update)追加を完了します。|  
|[CDaoRecordset::CanAppend](#canappend)|使用してレコード セットに新しいレコードを追加できる場合は&0; 以外を返す、 [AddNew](#addnew)メンバー関数。|  
|[CDaoRecordset::CanBookmark](#canbookmark)|レコード セットは、ブックマークをサポートする場合は&0; 以外を返します。|  
|[CDaoRecordset::CancelUpdate](#cancelupdate)|期限に保留中の更新プログラムを選択解除、[編集](#edit)または[AddNew](#addnew)操作します。|  
|[CDaoRecordset::CanRestart](#canrestart)|0 以外の場合を返します。 [Requery](#requery)レコード セットのクエリを再実行を呼び出すことができます。|  
|[CDaoRecordset::CanScroll](#canscroll)|レコードをスクロールする場合は&0; 以外を返します。|  
|[CDaoRecordset::CanTransact](#cantransact)|データ ソースには、トランザクションがサポートしている場合は&0; 以外を返します。|  
|[CDaoRecordset::CanUpdate](#canupdate)|レコード セットを更新する場合は&0; 以外を返します (することができますを追加、更新、またはレコードを削除) します。|  
|[CDaoRecordset::Close](#close)|レコード セットを閉じます。|  
|[CDaoRecordset::Delete](#delete)|レコード セットから現在のレコードを削除します。 削除された後は、別のレコードに明示的にスクロールする必要があります。|  
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|データ ソースに対応するレコードとレコード セットのフィールド データ メンバーの間で双方向) の「データを交換するには、呼び出されます。 レコード フィールド エクス (チェンジ DFX) をを実装 DAO します。|  
|[CDaoRecordset::Edit](#edit)|現在のレコードへの変更を準備します。 呼び出す**更新**編集を完了します。|  
|[CDaoRecordset::FillCache](#fillcache)|すべてのデータを格納する、または ODBC データ ソースからデータを含むレコード セット オブジェクトのローカル キャッシュの一部です。|  
|[CDaoRecordset::Find](#find)|1 つは、次では、検索、特定の文字列を指定された条件と、そのレコードを現在のレコードを満たすダイナセット タイプのレコード セット内の前、または最後の位置。|  
|[CDaoRecordset::FindFirst](#findfirst)|ダイナセット型またはレコードを指定された条件と、そのレコードを現在のレコードを満たす最初のレコードを検索します。|  
|[CDaoRecordset::FindLast](#findlast)|ダイナセット型またはレコードを指定された条件と、そのレコードを現在のレコードを満たすには、最後のレコードを検索します。|  
|[CDaoRecordset::FindNext](#findnext)|ダイナセット型またはレコードを指定された条件と、そのレコードを現在のレコードを満たすには、次のレコードを検索します。|  
|[CDaoRecordset::FindPrev](#findprev)|ダイナセット型またはレコードを指定された条件と、そのレコードを現在のレコードを満たすには、前のレコードを検索します。|  
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|レコード セット オブジェクトの現在のレコードのレコード数を返します。|  
|[CDaoRecordset::GetBookmark](#getbookmark)|レコードのブックマークを表す値を返します。|  
|[CDaoRecordset::GetCacheSize](#getcachesize)|ODBC データ ソースからローカルにキャッシュされたデータを含むダイナセット タイプのレコード セット内のレコードの数を示す値を返します。|  
|[CDaoRecordset::GetCacheStart](#getcachestart)|キャッシュすることをレコード セットの最初のレコードのブックマークを示す値を返します。|  
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|返します。、`CString`最近にインデックスの名前を含む、インデックス付きのテーブル型で使用される`CDaoRecordset`します。|  
|[CDaoRecordset::GetDateCreated](#getdatecreated)|基になるベース テーブルの日付と時刻を返す、`CDaoRecordset`オブジェクトが作成されました|  
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|基になるベース テーブルのデザインに加えられた最新の変更日時を返します、`CDaoRecordset`オブジェクトです。|  
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|既定のデータ ソースの名前を返します。|  
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|実行する既定の SQL 文字列を取得するには、呼び出されます。|  
|[CDaoRecordset::GetEditMode](#geteditmode)|現在のレコードの編集状態を示す値を返します。|  
|[CDaoRecordset::GetFieldCount](#getfieldcount)|レコード セット内のフィールドの数を表す値を返します。|  
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|レコード セットの特定の種類のフィールドについての情報を返します。|  
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|レコード セット内のフィールドの値を返します。|  
|[CDaoRecordset::GetIndexCount](#getindexcount)|レコード セットを基になるテーブルのインデックスの数を取得します。|  
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|さまざまな種類のインデックスに関する情報を返します。|  
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|最後に追加またはレコードの更新を決定するために使用します。|  
|[CDaoRecordset::GetLockingMode](#getlockingmode)|編集中に有効になっているロックの種類を示す値を返します。|  
|[CDaoRecordset::GetName](#getname)|返します。、 `CString` 、レコード セットの名前を格納します。|  
|[CDaoRecordset::GetParamValue](#getparamvalue)|基になる DAOParameter オブジェクトに格納されている指定されたパラメーターの現在の値を取得します。|  
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|レコードの総数の割合としての現在のレコードの位置を返します。|  
|[CDaoRecordset::GetRecordCount](#getrecordcount)|レコード セット オブジェクトにアクセスするレコードの数を返します。|  
|[CDaoRecordset::GetSQL](#getsql)|レコード セットのレコードを選択するために使用する SQL 文字列を取得します。|  
|[CDaoRecordset::GetType](#gettype)|レコード セットの種類を特定するために呼び出されます。 テーブル型、ダイナセット タイプ、またはスナップショットの種類。|  
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|返します。、`CString`フィールドに入力されたデータを検証する値を格納します。|  
|[CDaoRecordset::GetValidationText](#getvalidationtext)|検証規則が満たされていない場合に表示されるテキストを取得します。|  
|[CDaoRecordset::IsBOF](#isbof)|レコード セットは、最初のレコードの前に位置付けられている場合は&0; 以外を返します。 現在のレコードがありません。|  
|[CDaoRecordset::IsDeleted](#isdeleted)|レコード セットが削除されたレコードに配置されている場合は&0; 以外を返します。|  
|[CDaoRecordset::IsEOF](#iseof)|レコード セットは、最後のレコードの後に位置付けられている場合は&0; 以外を返します。 現在のレコードがありません。|  
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|現在のレコードで指定したフィールドが変更された場合は&0; 以外を返します。|  
|[CDaoRecordset::IsFieldNull](#isfieldnull)|現在のレコードで指定したフィールドが Null (値を持たない) の場合は&0; 以外を返します。|  
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|現在のレコードで指定したフィールドに設定できます Null (値がない) 場合は&0; 以外を返します。|  
|[CDaoRecordset::IsOpen](#isopen)|0 以外の場合を返します。[開いている](#open)既に呼び出されています。|  
|[CDaoRecordset::Move](#move)|どちらの方向に現在のレコードから、指定した数のレコードをレコード セットを配置します。|  
|[CDaoRecordset::MoveFirst](#movefirst)|レコード セット内の最初のレコードには、現在のレコードを配置します。|  
|[CDaoRecordset::MoveLast](#movelast)|現在のレコードをレコード セットの最後のレコードに位置付けます。|  
|[CDaoRecordset::MoveNext](#movenext)|現在のレコードをレコード セットの次のレコードに位置付けます。|  
|[CDaoRecordset::MovePrev](#moveprev)|レコード セットの前のレコードの現在のレコードを配置します。|  
|[Cdaorecordset::open](#open)|テーブル、ダイナセット、またはスナップショットからは、新しいレコード セットを作成します。|  
|[CDaoRecordset::Requery](#requery)|選択したレコードを更新するには、もう一度、レコード セットのクエリを実行します。|  
|[CDaoRecordset::Seek](#seek)|現在のインデックスと、そのレコードを現在のレコードの指定した条件を満たすインデックス付きのテーブル型のレコード セット オブジェクト内のレコードを見つけます。|  
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|レコード セット オブジェクトの現在のレコードのレコード数を設定します。|  
|[CDaoRecordset::SetBookmark](#setbookmark)|指定されたブックマークを含むレコードをレコード セットに配置します。|  
|[CDaoRecordset::SetCacheSize](#setcachesize)|ODBC データ ソースからローカルにキャッシュされたデータを含むダイナセット タイプのレコード セットのレコードの数を示す値を設定します。|  
|[CDaoRecordset::SetCacheStart](#setcachestart)|キャッシュされるレコード セットの最初のレコードのブックマークを示す値を設定します。|  
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|テーブル型のレコード セットのインデックスを設定すると呼ばれます。|  
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|変更されたため、現在のレコードで指定したフィールドをマークします。|  
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Null (値を持たない) は、現在のレコードで指定したフィールドの値を設定します。|  
|[たび](#setfieldvalue)|レコード セット内のフィールドの値を設定します。|  
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Null にレコード セット内のフィールドの値を設定します。 (値を持たない)。|  
|[CDaoRecordset::SetLockingMode](#setlockingmode)|編集中に有効にするロックの種類を示す値を設定します。|  
|[CDaoRecordset::SetParamValue](#setparamvalue)|基になる DAOParameter のオブジェクトに格納されている指定されたパラメーターの現在の値を設定します。|  
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|指定されたパラメーターの現在の値を Null (値がない) に設定します。|  
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|レコード セット内のレコードの合計数の割合に対応する位置には、現在のレコードの位置を設定します。|  
|[CDaoRecordset::Update](#update)|完了すると、`AddNew`または**編集**データ ソースに新しいまたは更新されたデータを保存することによって操作します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|フィールドの変更は自動的にマークするかどうかを示すフラグが含まれています。|  
|[CDaoRecordset::m_nFields](#m_nfields)|レコード セット クラスのフィールド データ メンバーの数と、データ ソースからレコード セットが選択した列の数が含まれています。|  
|[CDaoRecordset::m_nParams](#m_nparams)|レコード セット クラスでパラメーター データ メンバーの数が含まれています: レコード セットのクエリで渡されるパラメーターの数|  
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|レコード セット オブジェクトを基になる DAO インターフェイスへのポインター。|  
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|この結果セットのソース データベースです。 ポインターを含む、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトです。|  
|[CDaoRecordset::m_strFilter](#m_strfilter)|SQL の構築に使用される文字列を含む**、**ステートメントです。|  
|[CDaoRecordset::m_strSort](#m_strsort)|SQL の構築に使用される文字列を含む**ORDER BY**ステートメントです。|  
  
## <a name="remarks"></a>コメント  
 「レコード セット」と呼ばれる`CDaoRecordset`オブジェクトは、次の&3; つのフォームで使用できます。  
  
-   テーブル型のレコード セットは、確認、追加、変更、または単一のデータベース テーブルからレコードを削除に使用できる基本テーブルを表します。  
  
-   ダイナセット タイプは、更新可能なレコードを持つクエリの結果です。 これらのレコード セットは、確認、追加、変更、または、基になるデータベース テーブルまたはテーブルからレコードを削除に使用できるレコードのセットです。 ダイナセット タイプには、データベース内の&1; つまたは複数のテーブルのフィールドを含めることができます。  
  
-   スナップショットの種類のレコード セットは、一連のデータの検索やレポートの生成に使用できるレコードの静的なコピーです。 これらのレコード セットは、データベース内の&1; つまたは複数のテーブルのフィールドを含めることができますが、更新することはできません。  
  
 レコード セットの各形式では、レコード セットが開かれる時に固定されたレコードのセットを表します。 テーブル型のレコード セットまたはダイナセット タイプのレコード セット内のレコードをスクロールすると、他のユーザーまたはアプリケーションで他のレコード セットのいずれか、レコード セットが開かれた後に、レコードに変更が反映されます。 (スナップショットの種類のレコード セットを更新できません。)使用する`CDaoRecordset`直接から、アプリケーション固有のレコード セット クラスを派生させたり`CDaoRecordset`します。 することもできます。  
  
-   レコード間をスクロールします。  
  
-   インデックスを設定し、すばやくを使用してレコードを探します[Seek](#seek) (テーブル型のレコード セットのみ)。  
  
-   文字列比較に基づいてレコードを検索します。"<",></",>\<="、"="、"> ="、または">"(ダイナセット タイプおよびスナップショット タイプのレコード セット)。  
  
-   レコードを更新し、(スナップショットの種類のレコード セット) を除くロック モードを指定します。  
  
-   データ ソースの選択から使用可能なレコードを制限するために、レコード セットをフィルター処理します。  
  
-   レコード セットを並べ替えます。  
  
-   実行時までわからない情報で、選択範囲をカスタマイズするレコード セットをパラメーター化します。  
  
 クラス`CDaoRecordset`のクラスに似たインターフェイスを提供`CRecordset`します。 主な違いは、そのクラス`CDaoRecordset`OLE に基づくデータ アクセス オブジェクト (DAO) を介してデータにアクセスします。 クラス`CRecordset`オープン データベース コネクティビティ (ODBC) と ODBC ドライバーを通じてその DBMS のデータベースにアクセスします。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC Open Database Connectivity () を基 MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"というプレフィックスが付いています。 DAO クラスで ODBC データ ソースにアクセスできます。Microsoft Jet データベース エンジンに固有であるために、DAO クラスは一般に優れた機能を提供します。  
  
 使用するか`CDaoRecordset`直接からクラスを派生させたり`CDaoRecordset`します。 いずれの場合、レコード セット クラスを使用するデータベースを開くし、コンス トラクターへのポインターに渡して、レコード セット オブジェクトを構築、`CDaoDatabase`オブジェクトです。 構築することも、`CDaoRecordset`オブジェクト、作成、一時的な MFC`CDaoDatabase`オブジェクトです。 まず、レコード セットの[開く](#open)かを指定するかどうか、オブジェクト タイプのレコード、ダイナセット タイプのレコード セットでは、スナップショットの種類のレコード セットのメンバー関数。 呼び出す**開く**データベースからデータを選択し、最初のレコードを取得します。  
  
 レコード間をスクロールし、それらを操作するには、オブジェクトのメンバー関数とデータ メンバーを使用します。 利用できる操作は、オブジェクトは、テーブル型のレコード セット、ダイナセット タイプの recordset またはスナップショットの種類のレコード セットかどうかと、更新可能または読み取り専用であるかどうかによって異なります。-これは、データベース、またはオープン データベース コネクティビティ (ODBC) データ ソースの機能に依存します。 されている変更されたか、後に追加するレコードを更新する、**開く**呼び出し、オブジェクトの[Requery](#requery)メンバー関数。 オブジェクトの**閉じる**メンバー関数し、それが完了したら、オブジェクトを破棄します。  
  
 `CDaoRecordset`DAO レコード フィールド エクス (チェンジ DFX) を使用してのタイプ セーフな C++ のメンバーの読み取りとレコードのフィールドの更新をサポート、`CDaoRecordset`または`CDaoRecordset`-クラスを派生します。 DFX メカニズムを使用して、使用せず、データベース内の列の動的バインドを実装することも[GetFieldValue](#getfieldvalue)と[いる](#setfieldvalue)します。  
  
 関連情報については、「レコード セット オブジェクト」DAO ヘルプのトピックを参照してください。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="a-nameaddnewa--cdaorecordsetaddnew"></a><a name="addnew"></a>CDaoRecordset::AddNew  
 テーブル型またはダイナセット タイプのレコード セットに新しいレコードを追加するには、このメンバー関数を呼び出します。  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>コメント  
 レコードのフィールドは、最初に Null です。 (データベース用語では「値を持たない」手段を Null に設定し、同じではありません**NULL** c++)。完了するには、操作を呼び出す必要があります、[更新](#update)メンバー関数。 **更新プログラム**のデータ ソースへの変更を保存します。  
  
> [!CAUTION]
>  レコードを編集し、別のレコードを呼び出さずにスクロールしかどうか**更新**変更が失われ、警告します。  
  
 呼び出して、ダイナセット タイプのレコード セットにレコードを追加するかどうかは[AddNew](#addnew)、レコードがレコード セットに表示されになったいずれかに表示されている新しい基になるテーブルに含まれる`CDaoRecordset`オブジェクトです。  
  
 新しいレコードの位置は、レコード セットの種類によって異なります。  
  
-   ダイナセット タイプでは、新しいレコードが挿入されるレコード セットは保証されません。 この動作では、パフォーマンス、同時実行の上の理由から、Microsoft Jet 3.0 に変更されました。 目標は、新しく追加されたレコードを現在のレコードには、最後に変更されたレコードのブックマークを取得し、そのブックマークに移動します。  
  
 [!code-cpp[NVC_MFCDatabase&#1;](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]  
  
-   インデックスが指定されているテーブル型レコード セットの並べ替え順序での適切な場所でレコードが返されます。 インデックスが指定されていない場合は、レコード セットの末尾に新しいレコードが返されます。  
  
 レコードは、使用する前に現在`AddNew`を最新の状態します。 新しいレコードを現在に設定するし、レコード セットは、ブックマークの呼び出しをサポートする[SetBookmark](#setbookmark)基になる DAO レコード セット オブジェクトの LastModified プロパティの設定で示されるブックマークをします。 これは、追加したレコード内のカウンター (自動インクリメント) フィールドの値を決定するために役立ちます。 詳細については、次を参照してください。 [GetLastModifiedBookmark](#getlastmodifiedbookmark)します。  
  
 データベースは、トランザクションをサポートする場合は、`AddNew`呼び出し、トランザクションの一部です。 トランザクションの詳細については、クラスを参照してください。 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)します。 呼び出す必要があります[CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans)呼び出す前に`AddNew`します。  
  
 呼び出すことはできません`AddNew`レコード セットを持つ[開く](#open)メンバー関数が呼び出されていません。 A`CDaoException`を呼び出す場合にスローされる`AddNew`のレコード セットに追加することはできません。 呼び出して、レコード セットが更新可能かどうかを判断できます[CanAppend](#canappend)します。  
  
 フレームワークでは、確実に DAO レコード フィールド エクス (チェンジ DFX) メカニズムによって、データ ソースのレコードに書き込まれる、フィールド データ メンバーを変更します。 フィールドの値を変更すると、通常フィールドを設定、ダーティ、自動的を呼び出す必要があります頻度の低い[き](#setfielddirty)が自分で場合もありますようにすることも、列が明示的に更新または挿入するフィールド データ メンバーがどのような値に関係なく。 DFX 機構は、の使用も採用されています。**擬似 NULL**します。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)します。  
  
 ダブル バッファリング機構が使用されていない場合、フィールドの値を変更しては自動的に設定されません、フィールドをダーティと。 この場合は、ダーティ フィールドを明示的に設定する必要があります。 含まれているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
> [!NOTE]
>  レコードがダブル バッファリングされた場合 (つまり、フィールドの自動チェックが有効)、呼び出す`CancelUpdate`メンバー変数を前に、の値に復元されます`AddNew`または**編集**呼び出されました。  
  
 関連情報については、「AddNew メソッド」、"ただし Method"、「LastModified プロパティ」および"EditMode Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namecanappenda--cdaorecordsetcanappend"></a><a name="canappend"></a>CDaoRecordset::CanAppend  
 以前に開いたレコード セットが呼び出すことによって新しいレコードを追加することができるかどうかを判断するには、このメンバー関数を呼び出す、 [AddNew](#addnew)メンバー関数。  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>戻り値  
 新しいレコードを追加、レコード セットを許可する場合は 0 以外。それ以外の場合 0 を返します。 `CanAppend`読み取り専用レコード セットが開かれている場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプの「メソッドの追加」を参照してください。  
  
##  <a name="a-namecanbookmarka--cdaorecordsetcanbookmark"></a><a name="canbookmark"></a>CDaoRecordset::CanBookmark  
 以前に開いたレコード セットが個別にブックマークを使用してレコードを指定することができるかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL CanBookmark();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、レコード セットは、それ以外の場合 0 のブックマークをサポートしています。  
  
### <a name="remarks"></a>コメント  
 Microsoft Jet データベース エンジンのテーブルに完全に基づくレコード セットを使用している場合は、順方向専用のスクロール レコード セットとしてフラグが設定されたスナップショットの種類のレコード セットで以外のブックマークが使用できます。 その他のデータベース製品 (外部 ODBC データ ソース) はブックマークをサポートしていません。  
  
 関連情報については、DAO のヘルプでは、「ブックマークを設定のプロパティ」を参照してください。  
  
##  <a name="a-namecancelupdatea--cdaorecordsetcancelupdate"></a><a name="cancelupdate"></a>CDaoRecordset::CancelUpdate  
 `CancelUpdate`メンバー関数は、期限に保留中の更新プログラムをキャンセル、[編集](#edit)または[AddNew](#addnew)操作します。  
  
```  
virtual void CancelUpdate();
```  
  
### <a name="remarks"></a>コメント  
 アプリケーションを呼び出す場合など、**編集**または`AddNew`メンバー関数が呼び出されると[更新](#update)、`CancelUpdate`後に加えられた変更をキャンセル**編集**または`AddNew`呼び出されました。  
  
> [!NOTE]
>  レコードがダブル バッファリングされた場合 (つまり、フィールドの自動チェックが有効)、呼び出す`CancelUpdate`メンバー変数を前に、の値に復元されます`AddNew`または**編集**呼び出されました。  
  
 ある場合ない**編集**または`AddNew`操作が保留中、 `CancelUpdate` MFC 例外をスローすると、します。 呼び出す、 [GetEditMode](#geteditmode)キャンセルできる保留中の操作があるかどうかを判断するメンバー関数。  
  
 関連情報については、DAO ヘルプの「ただしメソッド」を参照してください。  
  
##  <a name="a-namecanrestarta--cdaorecordsetcanrestart"></a><a name="canrestart"></a>CDaoRecordset::CanRestart  
 レコード セットを呼び出して、クエリを (レコードを更新する) を再起動できるかどうかを判断するには、このメンバー関数を呼び出す、 **Requery**メンバー関数。  
  
```  
BOOL CanRestart();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値**Requery**クエリを実行するレコード セットのここでも、それ以外の場合 0 と呼ばれることができます。  
  
### <a name="remarks"></a>コメント  
 テーブル型のレコード セットをサポートしていない**Requery**します。  
  
 場合**Requery**は呼び出しがサポートされていない[閉じる](#close)し[開いている](#open)データを更新します。 呼び出すことができます**Requery**オブジェクトを更新するレコード セットの基になるパラメーター クエリ パラメーターの値が変更された後です。  
  
 関連情報については、DAO ヘルプの「再開可能なプロパティ」を参照してください。  
  
##  <a name="a-namecanscrolla--cdaorecordsetcanscroll"></a><a name="canscroll"></a>CDaoRecordset::CanScroll  
 このメンバー関数を呼び出して、レコード セットでは、スクロールできるかどうかを決定します。  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、それ以外の場合 0 のレコードをスクロールすることができます。  
  
### <a name="remarks"></a>コメント  
 呼び出した場合[開く](#open)と**dbForwardOnly**、レコード セットは前方スクロールのみことができます。  
  
 関連情報については、"配置の現在のレコード ポインターと DAO"DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namecantransacta--cdaorecordsetcantransact"></a><a name="cantransact"></a>CDaoRecordset::CanTransact  
 このメンバー関数を呼び出して、レコード セットにトランザクションができるかどうかを決定します。  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>戻り値  
 基になるデータ ソースは、トランザクション、それ以外の場合 0 をサポートしている場合 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプの「トランザクション プロパティ」を参照してください。  
  
##  <a name="a-namecanupdatea--cdaorecordsetcanupdate"></a><a name="canupdate"></a>CDaoRecordset::CanUpdate  
 このメンバー関数を呼び出して、レコード セットを更新できるかどうかを判断します。  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットを更新する場合は 0 以外 (追加、更新、およびレコードの削除)、それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 レコード セットは、その基になるデータ ソースが読み取り専用である場合、または指定した場合は読み取り専用する可能性があります**dbReadOnly**の`nOptions`呼び出されたとき[開く](#open)レコード セットにします。  
  
 関連情報については、「AddNew メソッド」、「メソッドの編集」、「メソッドの削除」、"Update Method"、および DAO ヘルプの「更新可能なプロパティ」のトピックを参照してください。  
  
##  <a name="a-namecdaorecordseta--cdaorecordsetcdaorecordset"></a><a name="cdaorecordset"></a>CDaoRecordset::CDaoRecordset  
 `CDaoRecordset` オブジェクトを構築します。  
  
```  
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDatabase`  
 ポインターを含む、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトまたは値**NULL**します。 かどうか**NULL**と`CDaoDatabase`オブジェクトの**開く**データ ソースに接続するメンバー関数が呼び出されていない場合、レコード セットがそれ自体の中に開きたいを試みます[開く](#open)を呼び出します。 渡した場合**NULL**、`CDaoDatabase`オブジェクトが構築され、結合からレコード セット クラスを派生するかどうかに指定したデータ ソース情報を使用して`CDaoRecordset`します。  
  
### <a name="remarks"></a>コメント  
 使用するか`CDaoRecordset`直接からアプリケーションに固有のクラスを派生させたり`CDaoRecordset`します。 ClassWizard を使用して、レコード セット クラスを派生させることができます。  
  
> [!NOTE]
>  派生させた場合、`CDaoRecordset`クラスを派生クラスは、独自のコンス トラクターを指定する必要があります。 派生クラスのコンス トラクターで、コンス トラクターを呼び出します`CDaoRecordset::CDaoRecordset`に沿った適切なパラメーターを渡します。  
  
 渡す**NULL**してレコード セット コンス トラクターに、`CDaoDatabase`オブジェクトが構築され、自動的に結合します。 これは、構築し、接続を必要としないための便利なショートカット、`CDaoDatabase`レコード セットを構築する前にオブジェクトです。 場合、`CDaoDatabase`オブジェクトが開いていない、 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)オブジェクトは、既定のワークスペースを使用するのも作成されます。 詳細については、次を参照してください。 [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase)します。  
  
##  <a name="a-nameclosea--cdaorecordsetclose"></a><a name="close"></a>CDaoRecordset::Close  
 閉じる、`CDaoRecordset`オブジェクトが関連付けられているデータベースで開いているレコード セットのコレクションから削除します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 **閉じる**は破棄しませんので、`CDaoRecordset`オブジェクトを呼び出すことによって、オブジェクトを再利用できる**開く**の同じデータ ソースまたは別のデータ ソースにします。  
  
 保留中のすべて[AddNew](#addnew)または[編集](#edit)ステートメントはキャンセルされ、すべての保留中のトランザクションはロールバックされます。 保留中の追加や変更を保持する場合は、呼び出す[更新](#update)を呼び出す前に**閉じる**の各レコードです。  
  
 呼び出すことができます**開く**呼び出した後でもう一度**閉じる**します。 これにより、レコード セット オブジェクトを再利用できます。 呼び出す方が[Requery](#requery)可能であれば、します。  
  
 関連情報については、DAO ヘルプの「閉じるメソッド」を参照してください。  
  
##  <a name="a-namedeletea--cdaorecordsetdelete"></a><a name="delete"></a>CDaoRecordset::Delete  
 開いているダイナセット型またはテーブル型のレコード セット オブジェクトの現在のレコードを削除するには、このメンバー関数を呼び出します。  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>コメント  
 削除が成功した後、レコード セットのフィールド データ メンバーは、Null 値に設定され、レコード セットのナビゲーションのメンバー関数のいずれかを明示的に呼び出す必要があります ([移動](#move)、 [Seek](#seek)、 [SetBookmark](#setbookmark)など)、削除したレコードを移動するためにします。 レコード セットからレコードを削除する場合がある現在のレコード、レコード セットを呼び出す前に**削除**。 そうしないと、MFC は、例外をスローします。  
  
 **削除**現在のレコードを削除し、アクセスできなくなります。 編集または削除されたレコードを使用できないが、現在残っています。 別のレコードに移動するとすることはできません、削除したレコード現在再度します。  
  
> [!CAUTION]
>  レコード セットは更新可能である必要があり、ある有効なレコードの現在のレコード セットを呼び出すと**削除**します。 たとえば、レコードを削除してを呼び出す前に別のレコードにはスクロールされません**削除**ここでも、**削除**がスローされます、 [CDaoException](../../mfc/reference/cdaoexception-class.md)します。  
  
 トランザクションを使用してを呼び出す場合は、レコードを復元できます、 [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback)メンバー関数。 ベース テーブルが主テーブルの場合は、連鎖的にリレーションシップを削除、現在のレコードを削除すると、外部テーブル内の&1; つまたは複数のレコードも削除可能性があります。 詳細については、DAO のヘルプで、定義「連鎖削除」を参照してください。  
  
 異なり`AddNew`と**編集**への呼び出し**削除**への呼び出しが発生しなかった**更新**します。  
  
 関連情報については、「AddNew メソッド」、「メソッドの編集」、「メソッドの削除」、"Update Method"、および DAO ヘルプの「更新可能なプロパティ」のトピックを参照してください。  
  
##  <a name="a-namedofieldexchangea--cdaorecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CDaoRecordset::DoFieldExchange  
 フレームワークでは、自動的にデータ ソースの現在のレコードの対応する列とレコード セット オブジェクトのフィールド データ メンバーの間でデータを交換するには、このメンバー関数を呼び出します。  
  
```  
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```  
  
### <a name="parameters"></a>パラメーター  
 `pFX`  
 ポインターを含む、`CDaoFieldExchange`オブジェクトです。 フレームワークは既にセットアップこのオブジェクト フィールドの exchange 操作のためのコンテキストを指定します。  
  
### <a name="remarks"></a>コメント  
 また、レコード セットの選択範囲の SQL ステートメントの文字列のパラメーターのプレース ホルダーに存在する場合、パラメーターのデータ メンバーをバインドします。 DAO レコード フィールド エクス チェンジ (DFX) と呼ばれるフィールドのデータの交換が双方向で機能します。 レコード セット オブジェクトのフィールド データ メンバーのデータ ソースのレコードのフィールドとレコード セット オブジェクトにデータ ソースのレコードからです。 列を動的にバインドする場合は、実装する必要はありません`DoFieldExchange`します。  
  
 唯一実行操作を実装するために通常必要`DoFieldExchange`派生レコード セット クラスは ClassWizard でクラスを作成し、フィールド データ メンバーの名前とデータ型を指定します。 パラメーター データ メンバーを指定する ClassWizard の書き込み先と、コードを追加することも可能性があります。 すべてのフィールドは、動的に連結するのには、この関数はアクティブになりましていないパラメーター データ メンバーを指定しない限りです。  
  
 ClassWizard 使用して、派生したレコード セット クラスを宣言するときのオーバーライドが書き込まれます`DoFieldExchange`次の例のようにします。  
  
 [!code-cpp[NVC_MFCDatabase&#2;](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]  
  
##  <a name="a-nameedita--cdaorecordsetedit"></a><a name="edit"></a>CDaoRecordset::Edit  
 現在のレコードを変更できるようにするには、このメンバー関数を呼び出します。  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>コメント  
 呼び出すと、**編集**メンバー関数の場合、現在のレコードのフィールドに加えられた変更は、コピー バッファーにコピーされます。 レコードに必要な変更を加えた後で呼び出す**更新**して変更を保存します。 **編集**レコード セットのデータ メンバーの値を保存します。 呼び出す場合**編集**を変更し、呼び出す**編集**元に&1; つ目の前に、レコードの値を復元する、もう一度**編集**を呼び出します。  
  
> [!CAUTION]
>  レコードを編集して、最初に呼び出さずに別のレコードに移動する操作を実行して場合**更新**変更が失われ、警告します。 さらに、レコード セットまたは親データベースを閉じる場合は、警告なし、編集されたレコードが破棄されます。  
  
 場合によっては、(データを含まない) を Null にすることで、列を更新することがあります。 これを行うには、呼び出す`SetFieldNull`のパラメーターを持つ**TRUE** Null フィールドをマークするこれもにより、更新される列です。 場合は、フィールドの値が変更されていない場合でも、データ ソースに書き込まれ、呼び出しを`SetFieldDirty`のパラメーターを持つ**TRUE**します。 これは、フィールド値の Null であった場合でも機能します。  
  
 フレームワークでは、確実に DAO レコード フィールド エクス (チェンジ DFX) メカニズムによって、データ ソースのレコードに書き込まれる、フィールド データ メンバーを変更します。 フィールドの値を変更すると、通常フィールドを設定、ダーティ、自動的を呼び出す必要があります頻度の低い[き](#setfielddirty)が自分で場合もありますようにすることも、列が明示的に更新または挿入するフィールド データ メンバーがどのような値に関係なく。 DFX 機構は、の使用も採用されています。**擬似 NULL**します。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)します。  
  
 ダブル バッファリング機構が使用されていない場合、フィールドの値を変更しては自動的に設定されません、フィールドをダーティと。 この場合は、ダーティ フィールドを明示的に設定する必要があります。 含まれているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
 時刻からロックは、レコードがレコード セット オブジェクトがマルチ ユーザー環境で排他ロックされると、**編集**更新が完了するまでに使用します。 レコード セットがやロックされている場合は、レコードがロックされ、データベースで更新される直前に、編集前のレコードと比較します。 呼び出されるため、レコードが変更された場合**編集**、**更新**操作が失敗して、MFC は例外をスローします。 ロック モードを変更する`SetLockingMode`です。  
  
> [!NOTE]
>  オプティミスティック ロックは常に、インストール可能な ISAM、ODBC などの外部データベース形式で使用します。  
  
 呼び出した後は、現在のレコードが**編集**します。 呼び出す**編集**、現在のレコードが必要があります。 現在のレコードが存在しない場合、またはレコード セットがオープン テーブル型またはダイナセット タイプの recordset オブジェクトを参照していない場合は、例外が発生します。 呼び出す**編集**により、`CDaoException`が次の状況でスローされます。  
  
-   現在のレコードがありません。  
  
-   データベースまたはレコード セットは読み取り専用です。  
  
-   レコードのフィールドは、更新可能ではありません。  
  
-   データベースまたはレコード セットは、別のユーザーによって排他的に使用開いていた。  
  
-   別のユーザーは、レコードを含むページをロックされています。  
  
 データ ソースは、トランザクションをサポートする場合は、**編集**呼び出し、トランザクションの一部です。 呼び出す必要があります`CDaoWorkspace::BeginTrans`呼び出す前に**編集**とレコード セットが開かれた後。 その通話にも注意して`CDaoWorkspace::CommitTrans`呼び出しに代わるものではありません**更新**を完了する、**編集**操作します。 トランザクションの詳細については、クラスを参照してください。`CDaoWorkspace`します。  
  
 関連情報については、「AddNew メソッド」、「メソッドの編集」、「メソッドの削除」、"Update Method"、および DAO ヘルプの「更新可能なプロパティ」のトピックを参照してください。  
  
##  <a name="a-namefillcachea--cdaorecordsetfillcache"></a><a name="fillcache"></a>CDaoRecordset::FillCache  
 指定された数のレコード セットからレコードをキャッシュするには、このメンバー関数を呼び出します。  
  
```  
void FillCache(
    long* pSize = NULL,  
    COleVariant* pBookmark = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `pSize`  
 キャッシュに設定する行の数を指定します。 このパラメーターを省略した場合、値は、基になる DAO オブジェクトの CacheSize プロパティの設定で決まります。  
  
 `pBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md)ブックマークを指定します。 キャッシュはこのブックマークで示されたレコードから開始されます。 このパラメーターを省略した場合、キャッシュは、基になる DAO オブジェクトの CacheStart プロパティで示されたレコードから開始されます。  
  
### <a name="remarks"></a>コメント  
 キャッシュすると、取得、またはリモート サーバーからデータをフェッチします。 アプリケーションのパフォーマンスが向上します。 キャッシュは、領域を前提としている、データはおそらく再要求されて、アプリケーションの実行中に、サーバーから直前にフェッチされたデータを保持するローカル メモリがいます。 データが要求されると、Microsoft Jet データベース エンジン、データのキャッシュまずチェック時間がかかると、サーバーから取得することではなく。 非 ODBC データ ソースにデータ キャッシュを使用しても何も起こりませんように、データがキャッシュに保存されません。  
  
 フェッチされるレコードを格納するキャッシュを待機しているのではなく明示的に入力できますキャッシュいつでも呼び出すことによって、`FillCache`メンバー関数。 これは、方法は、高速なため、キャッシュがいっぱいに`FillCache`はなく、一度に&1; つずつのいくつかのレコードをフェッチします。 たとえば、画面にレコードが表示されているときに、アプリケーションの呼び出しを持つことができます`FillCache`を次の画面いっぱいのレコードをフェッチします。  
  
 レコード セット オブジェクトを使用してアクセスされる ODBC データベースには、ローカル キャッシュを持つことができます。 キャッシュを作成するには、リモート データ ソースからレコード セット オブジェクトを開くし、しを呼び出す、`SetCacheSize`と`SetCacheStart`レコード セットのメンバー関数。 場合`lSize`と*lBookmark*で指定された範囲外部分的または完全である範囲を作成`SetCacheSize`と`SetCacheStart`、この範囲外のレコード セットの部分は無視され、キャッシュに読み込まれない。 場合`FillCache`要求よりも多くのレコードがリモート データ ソースでは、残りのレコードのみがフェッチ、例外はスローされません。  
  
 キャッシュからフェッチされたレコードでは、他のユーザーがデータ ソースに同時に行われた変更は反映されません。  
  
 `FillCache`キャッシュされていないレコードだけを取得します。 キャッシュされたすべてのデータの更新を強制的に、`SetCacheSize`メンバー関数を`lSize`パラメーターを 0、呼び出し`SetCacheSize`を使用して、`lSize`パラメーターは、最初に要求して、呼び出し、キャッシュのサイズに等しい`FillCache`します。  
  
 関連情報については、DAO ヘルプの「FillCache メソッド」を参照してください。  
  
##  <a name="a-namefinda--cdaorecordsetfind"></a><a name="find"></a>CDaoRecordset::Find  
 比較演算子を使用してダイナセット型またはスナップショットのレコード セット内で特定の文字列を検索するには、このメンバー関数を呼び出します。  
  
```  
virtual BOOL Find(
    long lFindType,  
    LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 *lFindType*  
 必要な検索操作の種類を示す値。 次の値を指定できます。  
  
- **AFX_DAO_NEXT**一致する文字列の次の場所を検索します。  
  
- **AFX_DAO_PREV**一致する文字列の前の場所を検索します。  
  
- **AFX_DAO_FIRST**一致する文字列の最初の位置を検索します。  
  
- **AFX_DAO_LAST**一致する文字列の最後の位置を検索します。  
  
 `lpszFilter`  
 文字列式 (のように、 **、**付けられ、SQL ステートメントの句**、**) レコードを検索するために使用します。 例:  
  
 [!code-cpp[NVC_MFCDatabase&#3;](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 1 つは、次を検索する文字列の前、または最後のインスタンス。 **検索**は仮想関数なので、このメソッドをオーバーライドして、独自の実装を追加します。 `FindFirst`、 `FindLast`、 `FindNext`、および`FindPrev`のメンバー関数の呼び出し、**検索**メンバー関数を使用できるように**検索**すべての検索操作の動作を制御します。  
  
 テーブル型のレコード セット内のレコードを検索を呼び出す、 [Seek](#seek)メンバー関数。  
  
> [!TIP]
>  レコードがある場合より効果的な一連の値が小さいほど**検索**になります。 一般に、および、特に、ODBC データは、必要なレコードだけを取得する新しいクエリを作成することをお勧めします。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプでできます。  
  
##  <a name="a-namefindfirsta--cdaorecordsetfindfirst"></a><a name="findfirst"></a>CDaoRecordset::FindFirst  
 このメンバー関数を呼び出して、指定した条件に一致する最初のレコードを検索します。  
  
```  
BOOL FindFirst(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFilter`  
 文字列式 (のように、 **、**付けられ、SQL ステートメントの句**、**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 `FindFirst`メンバー関数は、レコード セットの先頭から検索し、レコード セットの末尾に検索を開始します。  
  
 レコード間を移動する移動操作のいずれかのレコードを検索 (だけでなく、特定の条件を満たしているもの) を使用してすべてを含める場合。 テーブル型のレコード セット内のレコードを検索を呼び出す、`Seek`メンバー関数。  
  
 現在のレコードのポインターは、決められた条件に一致するレコードが置かれていない場合、`FindFirst`は&0; を返します。 レコード セットには、条件を満たす複数のレコードが含まれている場合`FindFirst`、最初に見つかった位置では、検索`FindNext`と次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合を呼び出すことによって、変更を保存してください、**更新**別のレコードに移動する前に、メンバー関数。 更新することがなく別のレコードに移動すると、変更内容は警告なしに失われます。  
  
 **検索**メンバー関数は、次の表に、双方向での場所から検索します。  
  
|検索操作|開始|検索の方向|  
|---------------------|-----------|----------------------|  
|`FindFirst`|レコード セットの先頭|レコード セットの末尾|  
|`FindLast`|レコード セットの末尾|レコード セットの先頭|  
|`FindNext`|現在のレコード|レコード セットの末尾|  
|**FindPrevious**|現在のレコード|レコード セットの先頭|  
  
> [!NOTE]
>  呼び出すと`FindLast`、Microsoft Jet データベース エンジンがこれが既に実行されていない場合、検索を開始する前に、レコード セットが完全に設定します。 最初の検索は、以後の検索よりも長くかかる場合があります。  
  
 検索操作のいずれかの方法は呼び出すことと同じ**MoveFirst**または`MoveNext`、ただし、これだけでは、最初または次のレコード現在条件を指定せずします。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合**検索**、現在のレコードが定義されていない&0; 以外を返します。 この場合は、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショット タイプ レコード セットを使用できません。  
  
-   米国の日付形式 (1 か月-日-年) を使用する必要があります、米国版の Microsoft Jet データベース エンジンを使用していない場合でも、日付を持つフィールドを検索する場合それ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを使用する場合、特に大規模なレコード セットを操作する場合、検索操作を使用して、低速があるが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますカスタム**ORDERBY**または**、**句、パラメーター クエリ、または**CDaoQuerydef**インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプでできます。  
  
##  <a name="a-namefindlasta--cdaorecordsetfindlast"></a><a name="findlast"></a>CDaoRecordset::FindLast  
 このメンバー関数を呼び出して、指定した条件に一致する最後のレコードを検索します。  
  
```  
BOOL FindLast(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFilter`  
 文字列式 (のように、 **、**付けられ、SQL ステートメントの句**、**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 `FindLast`メンバー関数は、レコード セットの最後に、検索と、レコード セットの先頭に向かって逆方向検索を開始します。  
  
 レコード間を移動する移動操作のいずれかのレコードを検索 (だけでなく、特定の条件を満たしているもの) を使用してすべてを含める場合。 テーブル型のレコード セット内のレコードを検索を呼び出す、`Seek`メンバー関数。  
  
 現在のレコードのポインターは、決められた条件に一致するレコードが置かれていない場合、`FindLast`は&0; を返します。 レコード セットには、条件を満たす複数のレコードが含まれている場合`FindFirst`、最初に見つかった位置では、検索`FindNext`と、最初に見つかった位置の後に次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合を呼び出して変更を保存することを確認して、**更新**別のレコードに移動する前に、メンバー関数。 更新することがなく別のレコードに移動すると、変更内容は警告なしに失われます。  
  
 検索操作のいずれかの方法は呼び出すことと同じ**MoveFirst**または`MoveNext`、ただし、これだけでは、最初または次のレコード現在条件を指定せずします。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合**検索**、現在のレコードが定義されていない&0; 以外を返します。 この場合は、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショット タイプ レコード セットを使用できません。  
  
-   米国の日付形式 (1 か月-日-年) を使用する必要があります、米国版の Microsoft Jet データベース エンジンを使用していない場合でも、日付を持つフィールドを検索する場合それ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを使用する場合、特に大規模なレコード セットを操作する場合、検索操作を使用して、低速があるが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますカスタム**ORDERBY**または**、**句、パラメーター クエリ、または**CDaoQuerydef**インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプでできます。  
  
##  <a name="a-namefindnexta--cdaorecordsetfindnext"></a><a name="findnext"></a>CDaoRecordset::FindNext  
 このメンバー関数を呼び出して、指定した条件に一致する次のレコードを検索します。  
  
```  
BOOL FindNext(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFilter`  
 文字列式 (のように、 **、**付けられ、SQL ステートメントの句**、**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 `FindNext`メンバー関数は、現在のレコードから検索を開始し、レコード セットの末尾に検索します。  
  
 レコード間を移動する移動操作のいずれかのレコードを検索 (だけでなく、特定の条件を満たしているもの) を使用してすべてを含める場合。 テーブル型のレコード セット内のレコードを検索を呼び出す、`Seek`メンバー関数。  
  
 現在のレコードのポインターは、決められた条件に一致するレコードが置かれていない場合、`FindNext`は&0; を返します。 レコード セットには、条件を満たす複数のレコードが含まれている場合`FindFirst`、最初に見つかった位置では、検索`FindNext`と次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合を呼び出して変更を保存することを確認して、**更新**別のレコードに移動する前に、メンバー関数。 更新することがなく別のレコードに移動すると、変更内容は警告なしに失われます。  
  
 検索操作のいずれかの方法は呼び出すことと同じ**MoveFirst**または`MoveNext`、ただし、これだけでは、最初または次のレコード現在条件を指定せずします。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合**検索**、現在のレコードが定義されていない&0; 以外を返します。 この場合は、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショット タイプ レコード セットを使用できません。  
  
-   米国の日付形式 (1 か月-日-年) を使用する必要があります、米国版の Microsoft Jet データベース エンジンを使用していない場合でも、日付を持つフィールドを検索する場合それ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを使用する場合、特に大規模なレコード セットを操作する場合、検索操作を使用して、低速があるが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますカスタム**ORDERBY**または**、**句、パラメーター クエリ、または**CDaoQuerydef**インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプでできます。  
  
##  <a name="a-namefindpreva--cdaorecordsetfindprev"></a><a name="findprev"></a>CDaoRecordset::FindPrev  
 このメンバー関数を呼び出して、指定した条件に一致する以前のレコードを検索します。  
  
```  
BOOL FindPrev(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFilter`  
 文字列式 (のように、 **、**付けられ、SQL ステートメントの句**、**) レコードを検索するために使用します。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 `FindPrev`メンバー関数は、現在のレコードから検索を開始し、レコード セットの先頭に向かって逆方向に検索します。  
  
 レコード間を移動する移動操作のいずれかのレコードを検索 (だけでなく、特定の条件を満たしているもの) を使用してすべてを含める場合。 テーブル型のレコード セット内のレコードを検索を呼び出す、`Seek`メンバー関数。  
  
 現在のレコードのポインターは、決められた条件に一致するレコードが置かれていない場合、`FindPrev`は&0; を返します。 レコード セットには、条件を満たす複数のレコードが含まれている場合`FindFirst`、最初に見つかった位置では、検索`FindNext`と次の出現箇所を検索します。  
  
> [!CAUTION]
>  現在のレコードを編集する場合を呼び出して変更を保存することを確認して、**更新**別のレコードに移動する前に、メンバー関数。 更新することがなく別のレコードに移動すると、変更内容は警告なしに失われます。  
  
 検索操作のいずれかの方法は呼び出すことと同じ**MoveFirst**または`MoveNext`、ただし、これだけでは、最初または次のレコード現在条件を指定せずします。 移動操作で、検索操作を行うことができます。  
  
 検索操作を使用する場合は、次に注意してください。  
  
-   場合**検索**、現在のレコードが定義されていない&0; 以外を返します。 この場合は、有効なレコードには、現在のレコード ポインターを配置する必要があります。  
  
-   検索操作は、前方スクロール スナップショット タイプ レコード セットを使用できません。  
  
-   米国の日付形式 (1 か月-日-年) を使用する必要があります、米国版の Microsoft Jet データベース エンジンを使用していない場合でも、日付を持つフィールドを検索する場合それ以外の場合、一致するレコードが見つからない可能性があります。  
  
-   ODBC データベースで大きなダイナセットを使用する場合、特に大規模なレコード セットを操作する場合、検索操作を使用して、低速があるが見つかることもあります。 SQL クエリを使用してパフォーマンスを向上させることができますカスタム**ORDERBY**または**、**句、パラメーター クエリ、または**CDaoQuerydef**インデックス付きの特定のレコードを取得するオブジェクト。  
  
 関連情報については、トピックを参照して、"FindFirst、FindLast、FindNext、FindPrevious メソッド"DAO のヘルプでできます。  
  
##  <a name="a-namegetabsolutepositiona--cdaorecordsetgetabsoluteposition"></a><a name="getabsoluteposition"></a>CDaoRecordset::GetAbsolutePosition  
 レコード セット オブジェクトの現在のレコードのレコード数を返します。  
  
```  
long GetAbsolutePosition();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットのレコードの数を 0 から整数。 レコード セット内の現在のレコードの序数位置に対応します。  
  
### <a name="remarks"></a>コメント  
 基になる DAO オブジェクトの AbsolutePosition プロパティの値は 0 から始まります。0 の設定は、レコード セット内の最初のレコードを表します。 呼び出して、レコード セット内のデータが設定されたレコードの数を指定できます[GetRecordCount](#getrecordcount)します。 呼び出す`GetRecordCount`数を確認して、すべてのレコードにアクセスする必要がありますので時間がかかる場合があります。  
  
 場合は、現在のレコードとして、レコード セット内のレコードがない場合に-1 を返します。 現在のレコードが削除された場合は、AbsolutePosition プロパティの値が定義されていませんし、MFC は、参照されている場合に例外をスローします。 ダイナセット タイプのレコード セットに対して新しいレコードは、シーケンスの末尾に追加されます。  
  
> [!NOTE]
>  このプロパティは、レコード番号の代わりとして使用するものではありません。 ブックマークは、保持して、指定した位置に戻るための推奨される方法であり、すべての種類のレコード セット オブジェクトで現在のレコードを配置する唯一の方法です。 具体的には、前のレコードが削除されたときに、指定されたレコードの位置が変わります。 また、特定のレコードがある絶対位置を同じ場合は、レコード セットを再作成を使用して SQL ステートメントを使用して作成された場合を除き、レコード セット内の各レコードの順序は保証されないため保証はありません、 **ORDERBY**句。  
  
> [!NOTE]
>  このメンバー関数では、ダイナセット タイプとスナップショット タイプのレコード セットに対してのみ有効です。  
  
 関連情報については、DAO ヘルプの「AbsolutePosition プロパティ」を参照してください。  
  
##  <a name="a-namegetbookmarka--cdaorecordsetgetbookmark"></a><a name="getbookmark"></a>CDaoRecordset::GetBookmark  
 このメンバー関数を呼び出して、特定のレコードのブックマークの値を取得します。  
  
```  
COleVariant GetBookmark();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードにブックマークを表す値を返します。  
  
### <a name="remarks"></a>コメント  
 レコード セット オブジェクトを作成または開くときに各レコードは既に一意のブックマーク サポートしている場合。 呼び出す`CanBookmark`をレコード セットでブックマークをサポートするかどうかを判断します。  
  
 現在のレコードのブックマークを保存するにはするブックマークの値を割り当てることによって、`COleVariant`オブジェクトです。 別のレコードに移動した後でそのレコードにすばやく戻るを呼び出す`SetBookmark`の値に対応するパラメーターを持つ`COleVariant`オブジェクトです。  
  
> [!NOTE]
>  呼び出す[Requery](#requery) DAO ブックマークを変更します。  
  
 関連情報については、DAO ヘルプの「ブックマーク プロパティ」を参照してください。  
  
##  <a name="a-namegetcachesizea--cdaorecordsetgetcachesize"></a><a name="getcachesize"></a>CDaoRecordset::GetCacheSize  
 キャッシュされたレコードの数を取得するには、このメンバー関数を呼び出します。  
  
```  
long GetCacheSize();
```  
  
### <a name="return-value"></a>戻り値  
 ODBC データ ソースからローカルにキャッシュされたデータを含むダイナセット タイプ レコード セットからレコードの数を指定する値。  
  
### <a name="remarks"></a>コメント  
 データ キャッシュでは、ダイナセット タイプの recordset オブジェクトを経由してリモート サーバーからデータを取得するアプリケーションのパフォーマンスが向上します。 キャッシュは、アプリケーションの実行中に、データをもう一度要求は、最近、サーバーから取得するデータを保持するローカル メモリ内のスペースです。 データが要求されると、Microsoft Jet データベース エンジン、要求されたデータのキャッシュまずチェック時間がかかると、サーバーから取得するには。 ODBC データ ソースから発生しないデータがキャッシュに保存されません。  
  
 アタッチのテーブルなどの ODBC データ ソースには、ローカル キャッシュを持つことができます。  
  
 関連情報については、DAO のヘルプ トピック「CacheSize、CacheStart プロパティ」を参照してください。  
  
##  <a name="a-namegetcachestarta--cdaorecordsetgetcachestart"></a><a name="getcachestart"></a>CDaoRecordset::GetCacheStart  
 キャッシュされるレコード セットの最初のレコードのブックマークの値を取得するには、このメンバー関数を呼び出します。  
  
```  
COleVariant GetCacheStart();
```  
  
### <a name="return-value"></a>戻り値  
 A`COleVariant`キャッシュされるレコード セット内の最初のレコードのブックマークを指定します。  
  
### <a name="remarks"></a>コメント  
 Microsoft Jet データベース エンジンが、キャッシュからキャッシュの範囲内のレコードを要求し、サーバーからのキャッシュの範囲外のレコードを要求します。  
  
> [!NOTE]
>  キャッシュから取得されたレコードでは、他のユーザーがデータ ソースに同時に行われた変更は反映されません。  
  
 関連情報については、DAO のヘルプ トピック「CacheSize、CacheStart プロパティ」を参照してください。  
  
##  <a name="a-namegetcurrentindexa--cdaorecordsetgetcurrentindex"></a><a name="getcurrentindex"></a>CDaoRecordset::GetCurrentIndex  
 インデックス付きのテーブル型で使用されているインデックスを確認するには、このメンバー関数を呼び出す`CDaoRecordset`オブジェクトです。  
  
```  
CString GetCurrentIndex();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`テーブル型のレコード セットで使用する現在のインデックスの名前を格納します。 インデックスが設定されていない場合は、空の文字列を返します。  
  
### <a name="remarks"></a>コメント  
 このインデックスはテーブル型のレコード セット内のレコードの順序の基礎でありで使用される、 [Seek](#seek)レコードを検索するメンバー関数。  
  
 A`CDaoRecordset`オブジェクトは、1 つ以上のインデックスを持つことができますが、一度に&1; つだけのインデックスを使用することができます (ですが、[どちら](../../mfc/reference/cdaotabledef-class.md)オブジェクトはいくつかのインデックスに対して定義する必要があります)。  
  
 関連情報については、トピック「インデックス オブジェクト」と定義の DAO のヘルプでは、"現在のインデックス"を参照してください。  
  
##  <a name="a-namegetdatecreateda--cdaorecordsetgetdatecreated"></a><a name="getdatecreated"></a>CDaoRecordset::GetDateCreated  
 ベース テーブルが作成された日時を取得するには、このメンバー関数を呼び出します。  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>戻り値  
 A[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)ベース テーブルが作成された日時を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 日付と時刻の設定は、ベース テーブルが作成されたコンピューターから派生します。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="a-namegetdatelastupdateda--cdaorecordsetgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoRecordset::GetDateLastUpdated  
 このメンバー関数を呼び出して、スキーマの最終更新日時を取得します。  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>戻り値  
 A[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)ベース テーブルの構造 (スキーマ) が最後に更新された日時を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 日付と時刻の設定は、ベース テーブルの構造 (スキーマ) が最後に更新されたコンピューターから派生します。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="a-namegetdefaultdbnamea--cdaorecordsetgetdefaultdbname"></a><a name="getdefaultdbname"></a>CDaoRecordset::GetDefaultDBName  
 このレコード セットに対して、データベースの名前を確認するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetDefaultDBName();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`このレコード セットの派生元となるデータベースの名前とパスが含まれています。  
  
### <a name="remarks"></a>コメント  
 レコード セットへのポインターなしで作成された場合、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)を開くには、既定のデータベースのレコード セットによってこのパスが使用されます。 既定では、この関数は、空の文字列を返します。 ClassWizard がから新しいレコード セットを派生する場合`CDaoRecordset`、この関数が作成されます。  
  
 次の例は、二重の円記号の使用法を示しています (\\\\)、文字列としての必須では正しく解釈される文字列。  
  
 [!code-cpp[NVC_MFCDatabase&4;](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]  
  
##  <a name="a-namegetdefaultsqla--cdaorecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CDaoRecordset::GetDefaultSQL  
 フレームワークでは、レコード セットの基になる既定の SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`を既定の SQL ステートメントが含まれています。  
  
### <a name="remarks"></a>コメント  
 これは、テーブル名または SQL**選択**ステートメントです。  
  
 直接定義するしない既定の SQL ステートメントで ClassWizard、レコード セット クラスを宣言することで ClassWizard では、このタスクを実行する.  
  
 Null SQL 文字列を渡す場合[開く](#open)、この関数は、レコード セットのテーブル名または SQL の決定に呼び出されます。  
  
##  <a name="a-namegeteditmodea--cdaorecordsetgeteditmode"></a><a name="geteditmode"></a>CDaoRecordset::GetEditMode  
 このメンバー関数を呼び出して、編集の状態を確認する次の値の&1; つであります。  
  
```  
short GetEditMode();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードの編集状態を示す値を返します。  
  
### <a name="remarks"></a>コメント  
  
|値|説明|  
|-----------|-----------------|  
|**dbEditNone**|編集操作が進行中ではありません。|  
|**dbEditInProgress**|**編集**が呼び出されています。|  
|**dbEditAdd**|`AddNew`呼び出されました。|  
  
 関連情報については、DAO ヘルプの「EditMode プロパティ」を参照してください。  
  
##  <a name="a-namegetfieldcounta--cdaorecordsetgetfieldcount"></a><a name="getfieldcount"></a>CDaoRecordset::GetFieldCount  
 このメンバー関数を呼び出して、レコード セットで定義されたフィールド (列) の数を取得します。  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット内のフィールドの数。  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプの「Count プロパティ」を参照してください。  
  
##  <a name="a-namegetfieldinfoa--cdaorecordsetgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoRecordset::GetFieldInfo  
 このメンバー関数を呼び出してレコード セット内のフィールドに関する情報を取得します。  
  
```  
void GetFieldInfo(
    int nIndex,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetFieldInfo(
    LPCTSTR lpszName,  
    CDaoFieldInfo& fieldinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 インデックスで検索する場合、レコード セットのフィールド コレクションの定義済みフィールドの&0; から始まるインデックス。  
  
 `fieldinfo`  
 参照、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。  
  
 `dwInfoOptions`  
 取得するレコード セットに関する情報を指定するオプションです。 使用可能なオプションは、これらの原因として何を返す関数もここで表示されます。 最適なパフォーマンスを必要な情報のレベルだけを取得します。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名前、種類、サイズ、属性  
  
- `AFX_DAO_SECONDARY_INFO`プライマリについては、プラス: 序数の位置、必要に応じて、ゼロの長さ、照合順序では、外部名、ソース フィールドに、ソース テーブルを許可します。  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報と: 既定値、検証規則、検証のテキスト  
  
 `lpszName`  
 フィールドの名前。  
  
### <a name="remarks"></a>コメント  
 関数の&1; つのバージョンでは、インデックスでフィールドを検索することができます。 その他のバージョンでは、フィールドを名前で検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求するときは、そのレベルもの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="a-namegetfieldvaluea--cdaorecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CDaoRecordset::GetFieldValue  
 このメンバー関数を呼び出してレコード セット内のデータを取得します。  
  
```  
virtual void GetFieldValue(
    LPCTSTR lpszName,  
    COleVariant& varValue);

 
virtual void GetFieldValue(
    int nIndex,  
    COleVariant& varValue);
 
virtual COleVariant GetFieldValue(LPCTSTR lpszName); 
virtual COleVariant GetFieldValue(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 フィールドの名前を含む文字列へのポインター。  
  
 `varValue`  
 参照、`COleVariant`フィールドの値を格納するオブジェクト。  
  
 `nIndex`  
 インデックスで検索する場合、レコード セットのフィールド コレクション内のフィールドの&0; から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 2 つのバージョンの`GetFieldValue`、値の戻り値を返す、 [COleVariant](../../mfc/reference/colevariant-class.md)フィールドの値を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 名前または順序位置では、フィールドを参照することができます。  
  
> [!NOTE]
>  このメンバー関数を受け取るバージョンのいずれかの呼び出しに方が効率的です、`COleVariant`を返すバージョンの呼び出しではなく、パラメーターとしてオブジェクト参照、`COleVariant`オブジェクトです。 この関数の以前のバージョンは、旧バージョンと互換性のために保持されます。  
  
 使用`GetFieldValue`と[いる](#setfieldvalue)実行時ではなくで静的にバインド列を使用してフィールドを動的にバインドする、 [DoFieldExchange](#dofieldexchange)メカニズムです。  
  
 `GetFieldValue`および`DoFieldExchange`パフォーマンスを向上させるメカニズムを組み合わせることができます。 たとえば、使用して`GetFieldValue`、要求時にのみ必要な値を取得して、インターフェイスの「詳細な情報」ボタンには、その呼び出しを代入します。  
  
 関連情報については、"フィールド Object"、「値プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namegetindexcounta--cdaorecordsetgetindexcount"></a><a name="getindexcount"></a>CDaoRecordset::GetIndexCount  
 このメンバー関数を呼び出して、テーブル型のレコード セットで使用できるインデックスの数を決定します。  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブル型のレコード セット内のインデックスの数。  
  
### <a name="remarks"></a>コメント  
 `GetIndexCount`レコード セット内のすべてのインデックスをループ処理に役立ちます。 そのためを使用して`GetIndexCount`と共に[提供](#getindexinfo)します。 ダイナセット タイプまたはスナップショット タイプのレコード セットでこのメンバー関数を呼び出すと、MFC は、例外をスローします。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="a-namegetindexinfoa--cdaorecordsetgetindexinfo"></a><a name="getindexinfo"></a>CDaoRecordset::GetIndexInfo  
 さまざまな種類のレコード セットを基になるベース テーブルで定義されているインデックスに関する情報を取得するには、このメンバー関数を呼び出します。  
  
```  
void GetIndexInfo(
    int nIndex,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetIndexInfo(
    LPCTSTR lpszName,  
    CDaoIndexInfo& indexinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 数値の位置で検索する場合、テーブルのインデックス コレクション内の&0; から始まるインデックス。  
  
 `indexinfo`  
 参照、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。  
  
 `dwInfoOptions`  
 取得するインデックスに関する情報を指定するオプションです。 使用可能なオプションは、これらの原因として何を返す関数もここで表示されます。 最適なパフォーマンスを必要な情報のレベルだけを取得します。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)フィールドの名前、フィールドの情報  
  
- `AFX_DAO_SECONDARY_INFO`プライマリについては、プラス: プライマリ、Unique、クラスター化された、必要に応じて、IgnoreNulls 異形式  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報と: 個別のカウント  
  
 `lpszName`  
 Index オブジェクトの名前で検索する場合の名前へのポインター。  
  
### <a name="remarks"></a>コメント  
 関数の&1; つのバージョンでは、コレクション内の位置でインデックスを検索することができます。 その他のバージョンでは、名前によってインデックスを検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求するときは、そのレベルもの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="a-namegetlastmodifiedbookmarka--cdaorecordsetgetlastmodifiedbookmark"></a><a name="getlastmodifiedbookmark"></a>CDaoRecordset::GetLastModifiedBookmark  
 最も最近追加または更新されたレコードのブックマークを取得するには、このメンバー関数を呼び出します。  
  
```  
COleVariant GetLastModifiedBookmark();
```  
  
### <a name="return-value"></a>戻り値  
 A`COleVariant`を示す最近ブックマークが含まれる追加や、レコードを変更します。  
  
### <a name="remarks"></a>コメント  
 レコード セット オブジェクトを作成または開くときに各レコードは既に一意のブックマーク サポートしている場合。 呼び出す[GetBookmark](#getbookmark)をレコード セットにブックマークがサポートしているかを判断します。 レコード セットでブックマークがサポートされていない場合、`CDaoException`がスローされます。  
  
 レコードを追加すると、レコード セットの最後に表示を現在のレコードではありません。 新しいレコードを現在するためには、呼び出す`GetLastModifiedBookmark`し、呼び出す`SetBookmark`に新しく追加されたレコードを取得します。  
  
 関連情報については、DAO ヘルプの「LastModified プロパティ」を参照してください。  
  
##  <a name="a-namegetlockingmodea--cdaorecordsetgetlockingmode"></a><a name="getlockingmode"></a>CDaoRecordset::GetLockingMode  
 このメンバー関数を呼び出して、レコード セットに対して有効でロックの種類を決定します。  
  
```  
BOOL GetLockingMode();
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合、ロックの種類は、ペシミスティック ロックの場合は 0 です。  
  
### <a name="remarks"></a>コメント  
 呼び出すと、すぐにロックされているときに排他ロックが実際には、データ ページを編集しているレコードを含む、[編集](#edit)メンバー関数。 ページのロックが解除されてを呼び出したときに、[更新](#update)または[閉じる](#close)メンバー関数または移動または検索操作のいずれかです。  
  
 レコードの更新中にのみレコードを含むデータ ページがロックされている場合にオプティミスティック ロックが有効、**更新**メンバー関数。  
  
 ODBC データ ソースを使用する場合、ロックのモードは常にオプティミスティックです。  
  
 関連情報については、"LockEdits Property"と「ロック動作に複数のユーザー アプリケーション」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namegetnamea--cdaorecordsetgetname"></a><a name="getname"></a>CDaoRecordset::GetName  
 このメンバー関数を呼び出して、レコード セットの名前を取得します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`レコード セットの名前を格納します。  
  
### <a name="remarks"></a>コメント  
 レコード セットの名前は、先頭を英字にする必要があり、最大 40 文字を含めることができます。 数字を含めることができ、アンダー スコア文字しますが、区切り記号やスペースを含めることはできません。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="a-namegetparamvaluea--cdaorecordsetgetparamvalue"></a><a name="getparamvalue"></a>CDaoRecordset::GetParamValue  
 基になる DAOParameter のオブジェクトに格納されている指定されたパラメーターの現在の値を取得するには、このメンバー関数を呼び出します。  
  
```  
virtual COleVariant GetParamValue(int nIndex);  
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 基になる DAOParameter オブジェクトで、パラメーターの数値の位置。  
  
 `lpszName`  
 値を取得するパラメーターの名前。  
  
### <a name="return-value"></a>戻り値  
 クラスのオブジェクト[COleVariant](../../mfc/reference/colevariant-class.md)パラメーターの値を格納します。  
  
### <a name="remarks"></a>コメント  
 名前またはコレクション内の位置のいずれかのパラメーターを表示できます。  
  
 関連情報については、DAO ヘルプの「パラメーター オブジェクト」を参照してください。  
  
##  <a name="a-namegetpercentpositiona--cdaorecordsetgetpercentposition"></a><a name="getpercentposition"></a>CDaoRecordset::GetPercentPosition  
 呼び出すと、ダイナセット タイプまたはスナップショットの種類のレコード セットを使用しているときに`GetPercentPosition`、レコード セットを完全に設定するには、前に、移動の量が呼び出すことによって示されるアクセスできるレコードの数を基準としたが[GetRecordCount](#getrecordcount)します。  
  
```  
float GetPercentPosition();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット内のレコードの割合に基づいているレコード セット オブジェクトの現在のレコードのおおよその位置を示す 0 ~ 100 の範囲数です。  
  
### <a name="remarks"></a>コメント  
 行うことができますし、最後のレコードを呼び出して[MoveLast](#movelast)を完全なすべてのレコード セットが、これに作成のためこともかなりの時間。  
  
 呼び出すことができます`GetPercentPosition`のすべての&3; つのレコード セット オブジェクトで行うために、インデックスを持たないテーブルを含みます。 ただし、呼び出すことができない`GetPercentPosition`スクロール順方向専用のスナップショット、または外部のデータベースに対してパススルー クエリから開かれたレコード セット。 現在のレコードがないか、彼は現在のレコードが削除された場合、`CDaoException`がスローされます。  
  
 関連情報については、DAO ヘルプの「PercentPosition プロパティ」を参照してください。  
  
##  <a name="a-namegetrecordcounta--cdaorecordsetgetrecordcount"></a><a name="getrecordcount"></a>CDaoRecordset::GetRecordCount  
 レコード セットからレコードの数のアクセスを確認するには、このメンバー関数を呼び出します。  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セット オブジェクトにアクセスするレコードの数を返します。  
  
### <a name="remarks"></a>コメント  
 `GetRecordCount`すべてのレコードがアクセスされてまで、ダイナセット タイプまたはスナップショットの種類のレコード セットのレコードの数が格納されたは示しません。 このメンバー関数の呼び出し完了までに時間の大幅な時間がかかる場合があります。  
  
 最後のレコードにアクセスすると、戻り値は、レコード セットの削除されていないレコードの合計数を示します。 最後のレコードへのアクセスを強制的に、`MoveLast`または`FindLast`レコード セットのメンバー関数。 クエリが返すレコードのおおよその数を決定するのに SQL Count を使用することもできます。  
  
 アプリケーションの戻り値ダイナセット タイプ レコード セットのレコードの削除と`GetRecordCount`が減少します。 ただし、他のユーザーによって削除されたレコードは反映されません`GetRecordCount`現在のレコードが削除されたレコードに位置付けられるまでです。 レコードの数に影響するトランザクションを実行し、その後、トランザクションをロールバック`GetRecordCount`残りのレコードの実際の数には反映されません。  
  
 値`GetRecordCount`スナップショット タイプのレコード セットからは左右されない基になるテーブルに変更します。  
  
 値`GetRecordCount`テーブル型からレコード セットは、テーブルのレコードのおおよその数を反映し、テーブルのレコードの追加し、削除、すぐに影響を受けますができます。  
  
 レコードのないレコード セットには、値 0 が返されます。 アタッチされているテーブルや ODBC データベースで使用する`GetRecordCount`常に-1 を返します。 呼び出す、 **Requery**のレコード セットのメンバー関数の値にリセット`GetRecordCount`クエリが再実行される場合と同様です。  
  
 関連情報については、DAO ヘルプの「RecordCount プロパティ」を参照してください。  
  
##  <a name="a-namegetsqla--cdaorecordsetgetsql"></a><a name="getsql"></a>CDaoRecordset::GetSQL  
 開いたときに、レコード セットのレコードを選択するために使用された SQL ステートメントを取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetSQL() const;  
```  
  
### <a name="return-value"></a>戻り値  
 A `CString` SQL ステートメントを格納しています。  
  
### <a name="remarks"></a>コメント  
 これは一般に、SQL になります**選択**ステートメントです。  
  
 によって返される文字列`GetSQL`通常とは異なる任意の文字列でレコード セットに渡した場合、`lpszSQL`パラメーターを[開く](#open)メンバー関数。 これは、レコード セットに渡したに基づく完全な SQL ステートメントを作成するため**開く**、ClassWizard で指定したとするが指定したもので、[か](#m_strfilter)と[レコード](#m_strsort)データ メンバーです。  
  
> [!NOTE]
>  このメンバー関数を呼び出した後にだけ呼び出して**開く**します。  
  
 関連情報については、DAO ヘルプの「SQL プロパティ」を参照してください。  
  
##  <a name="a-namegettypea--cdaorecordsetgettype"></a><a name="gettype"></a>CDaoRecordset::GetType  
 レコード セット オブジェクトの種類を決定するレコード セットを開いた後に、このメンバー関数を呼び出します。  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットの種類を示す次の値のいずれかです。  
  
- **dbOpenTable**テーブル型のレコード セット  
  
- **dbOpenDynaset**ダイナセット タイプのレコード セット  
  
- **dbOpenSnapshot**スナップショット タイプのレコード セット  
  
### <a name="remarks"></a>コメント  
 関連情報については、DAO ヘルプの「型プロパティ」を参照してください。  
  
##  <a name="a-namegetvalidationrulea--cdaorecordsetgetvalidationrule"></a><a name="getvalidationrule"></a>CDaoRecordset::GetValidationRule  
 データの検証に使用されるルールを判断するには、このメンバー関数を呼び出します。  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`が変更またはテーブルに追加すると、レコード内のデータを検証する値を含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 このルールは、テキスト ベースし、基になるテーブルが変更されるたびに適用します。 データが有効でない場合、MFC は、例外をスローします。 返されたエラー メッセージは、指定した場合は基になるフィールド オブジェクトのプロパティのテキストまたは基になるフィールド オブジェクトのプロパティで指定された式のテキストです。 呼び出すことができます[GetValidationText](#getvalidationtext)エラー メッセージのテキストを取得します。  
  
 たとえば、月の日を必要とするレコードのフィールドがあります検証規則など"DAY BETWEEN 1 から 31 です"。  
  
 関連情報については、DAO ヘルプの「ValidationRule プロパティ」を参照してください。  
  
##  <a name="a-namegetvalidationtexta--cdaorecordsetgetvalidationtext"></a><a name="getvalidationtext"></a>CDaoRecordset::GetValidationText  
 このメンバー関数を呼び出して、基になるフィールド オブジェクトのプロパティのテキストを取得します。  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`フィールドの値が基になるフィールド オブジェクトの検証規則を満たしていない場合に表示されるメッセージのテキストを含むオブジェクト。  
  
### <a name="remarks"></a>コメント  
 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-nameisbofa--cdaorecordsetisbof"></a><a name="isbof"></a>CDaoRecordset::IsBOF  
 レコードからレコード セットの最初のレコードの前に終了したかどうかを学習するレコードにスクロールする前に、このメンバー関数を呼び出します。  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最初のレコードより前にスクロールした場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出すことも`IsBOF`と共に`IsEOF`レコード セットをいくつかのレコードが含まれていますが空かを判断します。 呼び出した後すぐに**開く**、レコード セットにレコードが含まれていない場合、 `IsBOF`&0; 以外を返します。 最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときに、 `IsBOF` 0 を返します。  
  
 呼び出すし、最初のレコードが現在のレコード`MovePrev`、`IsBOF`後以外を返します。 場合`IsBOF`呼び出すと、0 以外を返します`MovePrev`例外がスローされます。 場合`IsBOF`戻り値は&0; 以外の値、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、例外が発生します。  
  
 特定のメソッドの効果`IsBOF`と`IsEOF`設定。  
  
-   呼び出す**開く**内部的には、最初のレコード、レコード セットの現在のレコードを呼び出して**MoveFirst**します。 そのため、**開く**レコード的な原因の空のセットに`IsBOF`と`IsEOF`に&0; 以外を返します。 (失敗したときの動作については、次の表を参照してください**MoveFirst**または`MoveLast`呼び出しです)。  
  
-   レコードを正常に配置したすべての移動操作が発生する両方`IsBOF`と`IsEOF`0 を返します。  
  
-   `AddNew`呼び出しが続いて、**更新**呼び出しが正常に新しいレコードを挿入すると、`IsBOF`を返す場合に限り、0、`IsEOF`は既に 0 以外。 状態`IsEOF`は常に変更されません。 Microsoft Jet データベース エンジンによって定義されている、空のレコード セットの現在のレコード ポインターは、現在のレコードの後、新しいレコードが挿入されるため、ファイルの末尾です。  
  
-   どの**削除**呼び出し、残っている唯一のレコードをレコード セットから削除する場合でも、値を変更しないの`IsBOF`または`IsEOF`です。  
  
 この表では、移動操作は、のさまざまな組み合わせで許可される`IsBOF` / `IsEOF`します。  
  
||MoveFirst、MoveLast|MovePrev、<br /><br /> 移動< 0></ 0>|0 を移動します。|MoveNext、<br /><br /> Move > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`0 以外、=<br /><br /> `IsEOF`=0|Allowed|例外|例外|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`=&0; 以外の値|Allowed|Allowed|例外|例外|  
|両方とも&0; 以外の値|例外|例外|例外|例外|  
|どちらも 0|Allowed|Allowed|Allowed|Allowed|  
  
 移動操作を許可しても、操作、レコードを正常に配置するわけではありません。 これは、だけで、指定の移動操作を実行しようとするが許可され、例外が発生しないことを示します。 値、`IsBOF`と`IsEOF`メンバー関数を実行しようとした移動の結果として変更する場合があります。  
  
 値には、レコードを特定できない場合、移動操作の効果`IsBOF`と`IsEOF`設定が次の表に示すようにします。  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**、`MoveLast`|0 以外の値|0 以外の値|  
|**移動**0|変更なし|変更なし|  
|`MovePrev`, **Move**< 0></ 0>|0 以外の値|変更なし|  
|`MoveNext`, **Move** > 0|変更なし|0 以外の値|  
  
 関連情報については、トピックを参照して「BOF, EOF プロパティ」DAO のヘルプでできます。  
  
##  <a name="a-nameisdeleteda--cdaorecordsetisdeleted"></a><a name="isdeleted"></a>CDaoRecordset::IsDeleted  
 現在のレコードが削除されているかどうかを判断するには、このメンバー関数を呼び出します。  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットが削除されたレコードに配置されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 レコードをスクロールする場合と`IsDeleted`返します**TRUE** (ゼロ以外)、スクロールして別のレコードに他のレコード セットの操作を実行する前にします。  
  
> [!NOTE]
>  スナップショット パブリケーションまたはテーブル型のレコード セット内のレコードの削除済みの状態を確認する必要はありません。 呼び出す必要はありませんので、スナップショットからレコードを削除できない、`IsDeleted`です。 テーブル型のレコード セットは、削除されたレコードが実際には、レコード セットから削除されます。 レコードが削除されたか、または別のレコード セットで別のユーザーによって後は、そのレコードにスクロールすることはできません。 したがってを呼び出す必要はありません`IsDeleted`します。  
  
 ダイナセットからレコードを削除して、レコード セットから削除され、そのレコードにスクロールすることはできません。 ただし、内のレコードの場合、ダイナセットは削除別のユーザーによってまたは同じテーブルに基づく別のレコード セット内のいずれか`IsDeleted`戻ります**TRUE**にそのレコードを後でスクロールしたとき。  
  
 関連情報については、「メソッドの削除」、「LastModified プロパティ」および"EditMode Property"DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-nameiseofa--cdaorecordsetiseof"></a><a name="iseof"></a>CDaoRecordset::IsEOF  
 レコードからレコード セットの最後のレコードを越えているかどうかについては、レコードをスクロールするときに、このメンバー関数を呼び出します。  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>戻り値  
 レコード セットにレコードが含まれていない場合、または最後のレコードより後にスクロールする場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出すことも`IsEOF`レコード セットをいくつかのレコードが含まれていますが空かを判断します。 呼び出した後すぐに**開く**、レコード セットにレコードが含まれていない場合、 `IsEOF`&0; 以外を返します。 最初のレコードが現在のレコードには、少なくとも 1 つのレコードがレコード セットを開いたときに、 `IsEOF` 0 を返します。  
  
 最後のレコードが、呼び出されると、現在のレコードかどうか`MoveNext`、`IsEOF`後以外を返します。 場合`IsEOF`呼び出すと、0 以外を返します`MoveNext`例外がスローされます。 場合`IsEOF`戻り値は&0; 以外の値、現在のレコードが定義されていないと、現在のレコードを必要とする任意のアクション、例外が発生します。  
  
 特定のメソッドの効果`IsBOF`と`IsEOF`設定。  
  
-   呼び出す**開く**内部的には、最初のレコード、レコード セットの現在のレコードを呼び出して**MoveFirst**します。 そのため、**開く**レコード的な原因の空のセットに`IsBOF`と`IsEOF`に&0; 以外を返します。 (失敗したときの動作については、次の表を参照してください**MoveFirst**呼び出しです)。  
  
-   レコードを正常に配置したすべての移動操作が発生する両方`IsBOF`と`IsEOF`0 を返します。  
  
-   `AddNew`呼び出しが続いて、**更新**呼び出しが正常に新しいレコードを挿入すると、`IsBOF`を返す場合に限り、0、`IsEOF`は既に 0 以外。 状態`IsEOF`は常に変更されません。 Microsoft Jet データベース エンジンによって定義されている、空のレコード セットの現在のレコード ポインターは、現在のレコードの後、新しいレコードが挿入されるため、ファイルの末尾です。  
  
-   どの**削除**呼び出し、残っている唯一のレコードをレコード セットから削除する場合でも、値を変更しないの`IsBOF`または`IsEOF`です。  
  
 この表では、移動操作は、のさまざまな組み合わせで許可される`IsBOF` / `IsEOF`します。  
  
||MoveFirst、MoveLast|MovePrev、<br /><br /> 移動< 0></ 0>|0 を移動します。|MoveNext、<br /><br /> Move > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`0 以外、=<br /><br /> `IsEOF`=0|Allowed|例外|例外|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`=&0; 以外の値|Allowed|Allowed|例外|例外|  
|両方とも&0; 以外の値|例外|例外|例外|例外|  
|どちらも 0|Allowed|Allowed|Allowed|Allowed|  
  
 移動操作を許可しても、操作、レコードを正常に配置するわけではありません。 これは、だけで、指定の移動操作を実行しようとするが許可され、例外が発生しないことを示します。 値、`IsBOF`と`IsEOF`メンバー関数を実行しようとした移動の結果として変更する場合があります。  
  
 値には、レコードを特定できない場合、移動操作の効果`IsBOF`と`IsEOF`設定が次の表に示すようにします。  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**、`MoveLast`|0 以外の値|0 以外の値|  
|**移動**0|変更なし|変更なし|  
|`MovePrev`, **Move**< 0></ 0>|0 以外の値|変更なし|  
|`MoveNext`, **Move** > 0|変更なし|0 以外の値|  
  
 関連情報については、トピックを参照して「BOF, EOF プロパティ」DAO のヘルプでできます。  
  
##  <a name="a-nameisfielddirtya--cdaorecordsetisfielddirty"></a><a name="isfielddirty"></a>CDaoRecordset::IsFieldDirty  
 ダイナセットの指定されたフィールド データ メンバーを「ダーティ」としてマークされているかどうかを判断する (変更) このメンバー関数を呼び出します。  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL**がダーティ フィールドのいずれかが判断されます。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーがダーティ; としてフラグが設定された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 すべてのダーティ フィールド データ メンバー内のデータは上に転送するレコードをデータ ソースへの呼び出しによって現在のレコードが更新されたときに、**更新**のメンバー関数`CDaoRecordset`(の呼び出しに続く**編集**または`AddNew`)。 この知識があれば、さらに手順を実行できますなどに対するため、そのデータ ソースに書き込まれませんが、列をマークするフィールド データ メンバーです。  
  
 `IsFieldDirty`によって実装され`DoFieldExchange`します。  
  
##  <a name="a-nameisfieldnulla--cdaorecordsetisfieldnull"></a><a name="isfieldnull"></a>CDaoRecordset::IsFieldNull  
 このメンバー関数を呼び出してレコード セットの指定されたフィールド データ メンバーを Null としてマークされているかどうかを決定します。  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL** Null が、フィールドのいずれかが判断されます。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーが Null としてフラグが設定された場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 (データベース用語では「値を持たない」手段を Null に設定し、同じではありません**NULL** c++)。フィールド データ メンバーが Null としてフラグが設定した場合は、列の値がない現在のレコードのとして解釈されます。  
  
> [!NOTE]
>  使用して、特定の状況で`IsFieldNull`は非効率になる、次のコード例に示すようにします。  
  
 [!code-cpp[NVC_MFCDatabase&#5;](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]  
  
> [!NOTE]
>  派生することがなく動的レコードのバインドを使用しているかどうかは`CDaoRecordset`を使用してください**VT_**の例で示すようにします。  
  
##  <a name="a-nameisfieldnullablea--cdaorecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CDaoRecordset::IsFieldNullable  
 指定されたフィールド データ メンバーが「null を許容」かどうかを判断する (するには、Null 値に設定しますC++ **NULL** Null の場合、データベース用語では、これと同じではありません「値を持たない」) です。  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 状態を確認するにはフィールド データ メンバーへのポインターまたは**NULL** Null が、フィールドのいずれかが判断されます。  
  
### <a name="return-value"></a>戻り値  
 指定されたフィールド データ メンバーが Null の場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 Null 値は、フィールド値が必要です。 このようなフィールドを追加するか、レコードを更新する場合は Null に設定しようとすると、データ ソースは追加や更新を拒否し、**更新**は例外をスローします。 呼び出すときに、例外が発生した**更新**を呼び出すときではなく、`SetFieldNull`です。  
  
##  <a name="a-nameisopena--cdaorecordsetisopen"></a><a name="isopen"></a>CDaoRecordset::IsOpen  
 このメンバー関数を呼び出して、レコード セットが開いているかどうか判断します。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、レコード セット オブジェクトの**開く**または**Requery**メンバー関数が呼び出されていたとレコード セットが終了していない。 それ以外の場合 0 です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="a-namembcheckcachefordirtyfieldsa--cdaorecordsetmbcheckcachefordirtyfields"></a><a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset::m_bCheckCacheForDirtyFields  
 かどうかキャッシュされているフィールドとして自動的にマーク ダーティ (変更) を示すフラグを格納し、Null です。  
  
### <a name="remarks"></a>コメント  
 フラグが既定で**TRUE**します。 このデータ メンバーの設定は、全体のダブル バッファリングの機構を制御します。 フラグを設定すると**TRUE**DFX のメカニズムを使用してフィールドの単位でキャッシュを無効にすることができます。 フラグを設定すると**FALSE**、呼び出す必要があります`SetFieldDirty`と`SetFieldNull`自分でします。  
  
 呼び出しの前にこのデータ メンバーを設定**開く**します。 このメカニズムは、主に使いやすさです。 変更が行われると、フィールドのダブル バッファリングにより遅いことがあります。  
  
##  <a name="a-namemnfieldsa--cdaorecordsetmnfields"></a><a name="m_nfields"></a>CDaoRecordset::m_nFields  
 レコード セット クラスのフィールド データ メンバーの数と、データ ソースからレコード セットが選択した列の数が含まれています。  
  
### <a name="remarks"></a>コメント  
 レコード セット クラスのコンス トラクターを初期化する必要があります`m_nFields`静的に連結されるフィールドの適切な数です。 ClassWizard は、レコード セット クラスを宣言に使用するときに、この初期化を書き込みます。 手動で記述することもできます。  
  
 フレームワークでは、この番号を使用して、フィールド データ メンバーと、データ ソースの現在のレコードの対応する列の間の相互作用を管理します。  
  
> [!NOTE]
>  この番号に登録されている出力列の番号に対応する必要があります`DoFieldExchange`への呼び出し後`SetFieldType`パラメーターと共に**CDaoFieldExchange::outputColumn**します。  
  
 動作によって動的に列をバインドする`CDaoRecordset::GetFieldValue`と`CDaoRecordset::SetFieldValue`です。 これを行う場合は カウントをインクリメントする必要はありません`m_nFields`の呼び出しを DFX 関数の数を反映するように、`DoFieldExchange`メンバー関数。  
  
##  <a name="a-namemnparamsa--cdaorecordsetmnparams"></a><a name="m_nparams"></a>CDaoRecordset::m_nParams  
 レコード セット クラスでパラメーター データ メンバーの数が含まれています: レコード セットのクエリで渡されるパラメーターの数。  
  
### <a name="remarks"></a>コメント  
 レコード セット クラスにパラメーター データ メンバーがある場合、クラスのコンス トラクターを初期化する必要があります`m_nParams`を正しい値にします。 値`m_nParams`既定値は 0 です。 パラメーター データ メンバーを追加する場合、手動で行うことができます-パラメーターの数を反映するようにクラスのコンス トラクターで初期化処理を手動で追加する必要があります (の数とサイズ以上である必要がありますが ' 内のプレース ホルダー、**か**または`m_strSort`文字列)。  
  
 フレームワークは、レコード セットのクエリをパラメーター化するときに、この番号を使用します。  
  
> [!NOTE]
>  この番号は、"params"に登録されているの番号に対応する必要があります`DoFieldExchange`への呼び出し後`SetFieldType`パラメーターと共に**CFieldExchange::param**します。  
  
 関連情報については、DAO ヘルプの「パラメーター オブジェクト」を参照してください。  
  
##  <a name="a-namempdaorecordseta--cdaorecordsetmpdaorecordset"></a><a name="m_pdaorecordset"></a>CDaoRecordset::m_pDAORecordset  
 DAO レコード セット オブジェクトの基になるは、OLE インターフェイスへのポインターを含む、`CDaoRecordset`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。  
  
 関連情報については、「レコード セット オブジェクト」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namempdatabasea--cdaorecordsetmpdatabase"></a><a name="m_pdatabase"></a>CDaoRecordset::m_pDatabase  
 ポインターを含む、`CDaoDatabase`データ ソースに使用されるレコード セットが接続されているオブジェクト。  
  
### <a name="remarks"></a>コメント  
 この変数は、2 つの方法で設定されます。 通常、既に開かれているにポインターを渡す`CDaoDatabase`レコード セット オブジェクトを構築するときのオブジェクトします。 渡した場合**NULL**代わりに、 **CDaoRecordset**を作成、`CDaoDatabase`オブジェクトそのソリューションを開きます。 いずれの場合、`CDaoRecordset`この変数にマウス ポインターを格納します。  
  
 通常は直接不要に格納されているポインターを使用する**m_pDatabase**します。 独自の拡張機能を記述する場合`CDaoRecordset`、ただし、ポインターを使用する必要があります。 たとえば、する必要があります、ポインターをスローする場合、独自`CDaoException`(s)。  
  
 関連情報については、「データベースのオブジェクト」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namemstrfiltera--cdaorecordsetmstrfilter"></a><a name="m_strfilter"></a>CDaoRecordset::m_strFilter  
 構築するために使用する文字列を含む、 **、** SQL ステートメントの句。  
  
### <a name="remarks"></a>コメント  
 予約語を含まない**、**をレコード セットをフィルター処理します。 このデータ メンバーの使用は、テーブル型のレコード セットに適用されません。 使用**か**を使用して、レコード セットを開くときに影響を与えません、`CDaoQueryDef`ポインター。  
  
 米国の日付形式 (1 か月-日-年) を使用して、米国版の Microsoft Jet データベース エンジンを使用していない場合でも、日付を持つフィールドをフィルター処理する場合それ以外の場合、データがフィルター選択されません期待どおりにします。  
  
 関連情報については、DAO ヘルプの「フィルター プロパティ」を参照してください。  
  
##  <a name="a-namemstrsorta--cdaorecordsetmstrsort"></a><a name="m_strsort"></a>CDaoRecordset::m_strSort  
 含む文字列を含む、 **ORDERBY**予約語を含まない SQL ステートメントの句**ORDERBY**します。  
  
### <a name="remarks"></a>コメント  
 ダイナセットとスナップショット タイプの recordset オブジェクトを並べ替えることができます。  
  
 テーブル型のレコード セット オブジェクトを並べ替えることはできません。 テーブル型のレコード セットの並べ替え順序を確認するのには、呼び出す[SetCurrentIndex](#setcurrentindex)します。  
  
 使用`m_strSort`を使用して、レコード セットを開くときに影響を与えません、`CDaoQueryDef`ポインター。  
  
 関連情報については、DAO ヘルプの「並べ替えプロパティ」を参照してください。  
  
##  <a name="a-namemovea--cdaorecordsetmove"></a><a name="move"></a>CDaoRecordset::Move  
 このメンバー関数を呼び出してレコード セットに移動`lRows`現在のレコードからのレコードです。  
  
```  
virtual void Move(long lRows);
```  
  
### <a name="parameters"></a>パラメーター  
 `lRows`  
 前方または後方に移動するレコードの数。 正の値は、レコード セットの終了に向けて前方移動します。 負の値は、先頭に向かって後方移動します。  
  
### <a name="remarks"></a>コメント  
 前方または後方に移動することができます。 `Move( 1 )`等価`MoveNext`、および`Move( -1 )`と等価`MovePrev`します。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後**開く**または**Requery**、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  先頭またはレコード セットの末尾を越えてスクロールした場合 (`IsBOF`または`IsEOF`0 以外を返します) への呼び出し**移動**スロー、`CDaoException`です。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 呼び出すと**移動**前方スクロールのスナップショットで、`lRows`パラメーターは正の整数である必要がありますに移動できるように前方のみ、ブックマークは使用できません。  
  
 First、last をするためには、次に、以前レコードまたはレコード セットの現在のレコードを呼び出し、 **MoveFirst**、 `MoveLast`、 `MoveNext`、または`MovePrev`メンバー関数。  
  
 関連情報については、トピックを参照して、「Move メソッド」および"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="a-namemovefirsta--cdaorecordsetmovefirst"></a><a name="movefirst"></a>CDaoRecordset::MoveFirst  
 このメンバー関数を呼び出して、レコード セットでの最初のレコードを (ある場合)、現在のレコードです。  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要はありません**MoveFirst**レコード セットを開いた直後にします。 その時点では、最初のレコードが (もしあれば) と、現在のレコードでは自動的にです。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後**開く**または**Requery**、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 使用して、**移動**条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に一致するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクト内のレコードを検索、呼び出す`Seek`します。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックスのプロパティを使用します。 現在のインデックスを設定しないと、返されるレコードの順序は未定義です。  
  
 呼び出した場合`MoveLast`SQL クエリまたはクエリ定義に基づくレコード セット オブジェクトでは、クエリが完了するまで強制実行され、レコード セット オブジェクトが完全に作成します。  
  
 呼び出すことができない、 **MoveFirst**または`MovePrev`前方スクロール スナップショットを使用してメンバー関数。  
  
 現在の位置では、特定の個のレコードを前方または後方をレコード セット オブジェクト内に記録するには、呼び出す**移動**します。  
  
 関連情報については、トピックを参照して、「Move メソッド」および"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="a-namemovelasta--cdaorecordsetmovelast"></a><a name="movelast"></a>CDaoRecordset::MoveLast  
 レコード セットの現在のレコードの (存在する場合) は、最後のレコードを作成するには、このメンバー関数を呼び出します。  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後**開く**または**Requery**、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 使用して、**移動**条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に一致するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクト内のレコードを検索、呼び出す`Seek`します。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックスのプロパティを使用します。 現在のインデックスを設定しないと、返されるレコードの順序は未定義です。  
  
 呼び出した場合`MoveLast`SQL クエリまたはクエリ定義に基づくレコード セット オブジェクトでは、クエリが完了するまで強制実行され、レコード セット オブジェクトが完全に作成します。  
  
 現在の位置では、特定の個のレコードを前方または後方をレコード セット オブジェクト内に記録するには、呼び出す**移動**します。  
  
 関連情報については、トピックを参照して、「Move メソッド」および"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="a-namemovenexta--cdaorecordsetmovenext"></a><a name="movenext"></a>CDaoRecordset::MoveNext  
 このメンバー関数を呼び出してレコード セットの現在のレコード内の次のレコードを作成します。  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>コメント  
 呼び出すことをお勧め`IsBOF`前のレコードに移動しようとする前にします。 呼び出し`MovePrev`をスロー、`CDaoException`場合`IsBOF`、最初のレコードの前に既にスクロールしたか、レコード セットからレコードが選択されていないことを示す&0; 以外を返します。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後**開く**または**Requery**、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 使用して、**移動**条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に一致するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクト内のレコードを検索、呼び出す`Seek`します。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックスのプロパティを使用します。 現在のインデックスを設定しないと、返されるレコードの順序は未定義です。  
  
 現在の位置では、特定の個のレコードを前方または後方をレコード セット オブジェクト内に記録するには、呼び出す**移動**します。  
  
 関連情報については、トピックを参照して、「Move メソッド」および"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="a-namemovepreva--cdaorecordsetmoveprev"></a><a name="moveprev"></a>CDaoRecordset::MovePrev  
 このメンバー関数を呼び出してレコード セットの現在のレコードの前のレコードを作成します。  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>コメント  
 呼び出すことをお勧め`IsBOF`前のレコードに移動しようとする前にします。 呼び出し`MovePrev`をスロー、`CDaoException`場合`IsBOF`、最初のレコードの前に既にスクロールしたか、レコード セットからレコードが選択されていないことを示す&0; 以外を返します。  
  
> [!CAUTION]
>  呼び出す、**移動**レコード セットにレコードが存在しない場合、関数が例外をスローします。 一般に、両方を呼び出す`IsBOF`と`IsEOF`移動操作をいくつかのレコードをレコード セットが存在するかどうかを判断する前にします。 呼び出した後**開く**または**Requery**、いずれかを呼び出す`IsBOF`または`IsEOF`です。  
  
> [!NOTE]
>  いずれかを呼び出す場合、**移動**機能の現在のレコードがされている間に更新または追加、更新プログラムが警告なしに失われます。  
  
 使用して、**移動**条件を適用することがなくレコード間を移動する関数。 ダイナセット タイプまたは特定の条件に一致するスナップショットの種類のレコード セット オブジェクト内でレコードを検索するのにには、検索操作を使用します。 テーブル型のレコード セット オブジェクト内のレコードを検索、呼び出す`Seek`します。  
  
 レコード セットは、テーブル型のレコード セットを参照している場合、移動は、テーブルの現在のインデックスをたどります。 現在のインデックスを設定するには、基になる DAO オブジェクトのインデックスのプロパティを使用します。 現在のインデックスを設定しないと、返されるレコードの順序は未定義です。  
  
 呼び出すことができない、 **MoveFirst**または`MovePrev`前方スクロール スナップショットを使用してメンバー関数。  
  
 現在の位置では、特定の個のレコードを前方または後方をレコード セット オブジェクト内に記録するには、呼び出す**移動**します。  
  
 関連情報については、トピックを参照して、「Move メソッド」および"MoveFirst、MoveLast、MoveNext、MovePrevious メソッド"DAO のヘルプ。  
  
##  <a name="a-nameopena--cdaorecordsetopen"></a><a name="open"></a>Cdaorecordset::open  
 レコード セットのレコードを取得するには、このメンバー関数を呼び出す必要があります。  
  
```  
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    int nOptions = 0);

 
virtual void Open(
    CDaoTableDef* pTableDef,  
    int nOpenType = dbOpenTable,  
    int nOptions = 0);

 
virtual void Open(
    CDaoQueryDef* pQueryDef,  
    int nOpenType = dbOpenDynaset,  
    int nOptions = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nOpenType`  
 次のいずれかの値です。  
  
- **dbOpenDynaset**双方向にスクロールできるダイナセット タイプのレコード セット。 既定値です。  
  
- **dbOpenTable**双方向スクロールがテーブル型のレコード セット。  
  
- **dbOpenSnapshot**双方向にスクロールできるスナップショット タイプのレコード セット。  
  
 `lpszSQL`  
 次のいずれかを含む文字列ポインター:  
  
-   A **NULL**ポインター。  
  
-   1 つまたは複数のテーブル定義およびクエリ定義の (コンマ区切り) の名前です。  
  
-   SQL**選択**ステートメント (必要に応じて、SQL で**場所**または**ORDERBY**句)。  
  
-   パススルー クエリです。  
  
 `nOptions`  
 1 つ以上の次のオプションです。 既定値は 0 です。 次の値を指定できます。  
  
- **dbAppendOnly**のみ (ダイナセット タイプのレコード セットのみ) の新しいレコードを追加することができます。 このオプションは、レコードが追加されるだけことにリテラルを意味します。 MFC ODBC データベース クラスには、レコードの取得し、追加可能追加専用オプションが用意されています。  
  
- **dbForwardOnly**レコード セットを順方向専用のスナップショットがスクロールします。  
  
- **dbSeeChanges**別のユーザーが編集してデータを変更する場合、例外が生成されます。  
  
- **dbDenyWrite**他のユーザーを変更またはレコードを追加できません。  
  
- **dbDenyRead**他のユーザーがレコード (テーブル型のレコード セットのみ) を表示できません。  
  
- **dbReadOnly**レコードのみを表示できます。 他のユーザーが変更できます。  
  
- **組み合わせて**一貫性のない更新を許可 (ダイナセット タイプのレコード セットのみ)。  
  
- **指定できます**のみ一貫性のある更新が (ダイナセット タイプのレコード セットのみ) を許可します。  
  
> [!NOTE]
>  定数**指定できます**と**組み合わせて**は相互に排他的です。 1 つを使用することができますか、別の両方ではなくの特定のインスタンスで**開く**します。  
  
 *pTableDef*  
 ポインター、[どちら](../../mfc/reference/cdaotabledef-class.md)オブジェクトです。 このバージョンは、テーブル型のレコード セットに対してのみ有効です。 このオプションを使用する場合、`CDaoDatabase`ポインターの構築に使用される、`CDaoRecordset`は使用されません。 テーブル定義が存在するデータベースを使用する代わりに、します。  
  
 *pQueryDef*  
 ポインター、 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)オブジェクトです。 このバージョンでは、ダイナセット タイプとスナップショット タイプのレコード セットに対してのみ有効です。 このオプションを使用する場合、`CDaoDatabase`ポインターの構築に使用される、`CDaoRecordset`は使用されません。 クエリ定義が存在するデータベースを使用する代わりに、します。  
  
### <a name="remarks"></a>コメント  
 呼び出しの前に**開く**、レコード セット オブジェクトを構築する必要があります。 これにはいくつかの方法があります。  
  
-   レコード セット オブジェクトを構築する場合へのポインターを渡す、`CDaoDatabase`既に開かれているオブジェクト。  
  
-   レコード セット オブジェクトを構築する場合へのポインターを渡す、`CDaoDatabase`が開かれていないオブジェクトです。 レコード セットが開く、`CDaoDatabase`オブジェクトが、レコード セット オブジェクトの終了時に、その閉じられません。  
  
-   レコード セット オブジェクトを構築するときに渡す、 **NULL**ポインター。 レコード セット オブジェクトの呼び出し`GetDefaultDBName`Microsoft Access の名前を取得します。MDB ファイルを開きます。 レコード セットが、開く、`CDaoDatabase`オブジェクトと、レコード セットが開いている限りで開くことができます。 呼び出すと**閉じる**、レコード セットで、`CDaoDatabase`オブジェクトも閉じられます。  
  
    > [!NOTE]
    >  レコード セットを開くと、`CDaoDatabase`オブジェクトの非排他アクセス権を持つデータ ソースを開きます。  
  
 バージョンの**開く**を使用する、`lpszSQL`パラメーター、いくつかの方法の&1; つのレコードを取得するには、レコード セットが開く。 DFX 関数に&1; つ目は、`DoFieldExchange`です。 2 番目のオプションは、呼び出すことによって動的バインドを使用する、`GetFieldValue`メンバー関数。 これらのオプションは、単独または組み合わせで実装できます。 これらを組み合わせた場合を渡す必要が SQL ステートメントで自分自身への呼び出しにある**開く**します。  
  
 第&2; のバージョンを使用する場合**開く**に渡せば、`CDaoTableDef`オブジェクトを使用してバインドできる結果として得られる列`DoFieldExchange`DFX 機構やによって動的にバインド`GetFieldValue`します。  
  
> [!NOTE]
>  のみ呼び出すことができます**開く**を使用して、`CDaoTableDef`レコード セットのテーブル型のオブジェクト。  
  
 3 番目のバージョンを使用する場合**開く**に渡せば、`CDaoQueryDef`オブジェクト、クエリが実行され、結果として得られる列があるを使用してバインドするために使用可能な`DoFieldExchange`DFX 機構やによって動的にバインド`GetFieldValue`します。  
  
> [!NOTE]
>  のみ呼び出すことができます**開く**を使用して、`CDaoQueryDef`ダイナセットの型とスナップショット タイプのレコード セット オブジェクトです。  
  
 最初のバージョンの**開く**を使用する、`lpszSQL`パラメーター、レコードは、次の表に示すようにに基づいて条件を選択します。  
  
|パラメーター `lpszSQL` の値。|レコードの選択基準|例|  
|--------------------------------------|----------------------------------------|-------------|  
|**NULL**|`GetDefaultSQL` の返す文字列。||  
|1 つまたは複数のテーブル定義またはクエリ定義名のコンマ区切りの一覧です。|表されるすべての列、`DoFieldExchange`です。|`"Customer"`|  
|**選択**列リスト**FROM**テーブル リスト|指定されたテーブルまたはクエリ定義から指定した列。|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|  
  
 通常のプロシージャでは**NULL**に**開く**。 この場合は、**開く**呼び出し`GetDefaultSQL`、ClassWizard 生成を作成する場合、オーバーライド可能なメンバー関数、 `CDaoRecordset`-クラスを派生します。 この値は ClassWizard で指定したテーブル、またはクエリ定義の名前を示します。 代わりに、その他の情報を `lpszSQL` パラメーターに指定できます。  
  
 何を渡した**開く**クエリの最終的な SQL 文字列を構築 (SQL も**、**と**ORDERBY**句が追加された、`lpszSQL`文字列が渡されました) し、そのクエリを実行します。 呼び出して、作成された文字列を調べることができます`GetSQL`呼び出した後**開く**します。  
  
 レコードセット クラスのフィールド データ メンバーは、選択したデータの列に結び付けられています。 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 レコード セットは、フィルターや並べ替えなどのオプションを設定する場合は、設定`m_strSort`または**か**を呼び出す前に、レコード セット オブジェクトを作成した後**開く**します。 レコード セットが開いて、レコード セット内のレコードを更新する場合は、呼び出す**Requery**します。  
  
 呼び出す場合**開いている**ダイナセット型またはスナップショットの種類のレコード セットに使用することはできません、データ ソースを参照する場合、SQL ステートメントまたはアタッチ テーブルを表すテーブル定義または**dbOpenTable**型の引数の場合は、MFC 例外をスローします。 テーブル定義のオブジェクトが接続されているテーブルを表すかどうかを確認するのには、作成、[どちら](../../mfc/reference/cdaotabledef-class.md)オブジェクトと呼び出しの[GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect)メンバー関数。  
  
 使用して、 **dbSeeChanges**を編集または同じレコードを削除するときに、別のユーザーまたはコンピューターに別のプログラムによって行われた変更をトラップする場合にフラグを設定します。 たとえば、2 人のユーザーが同じレコードを呼び出す最初のユーザーの編集を開始、**更新**メンバー関数が成功しました。 **更新**2 番目のユーザーによって呼び出される、`CDaoException`がスローされます。 同様に、2 番目のユーザーが呼び出すしようとすると**削除**、レコードおよびそれを削除するが既に変更されて、最初のユーザーが、`CDaoException`に発生します。  
  
 通常、ユーザーがこの場合`CDaoException`の更新中に、コード必要があります、フィールドの内容を更新し、新しく変更された値を取得します。 削除する処理を行って、例外が発生した場合、コードは、データが最近変更されたことを示すメッセージをユーザーに新しいレコード データを表示する可能性があります。 この時点で、コードでは、ユーザーがレコードを削除してもよいことの確認を要求できます。  
  
> [!TIP]
>  順方向専用のスクロール オプションを使用して ( **dbForwardOnly**)、ODBC データ ソースから開かれたとき、アプリケーションでレコード セットを&1; つのパスは、パフォーマンスを向上させる。  
  
 関連情報については、DAO ヘルプの「OpenRecordset メソッド」を参照してください。  
  
##  <a name="a-namerequerya--cdaorecordsetrequery"></a><a name="requery"></a>CDaoRecordset::Requery  
 レコード セット (更新) を再構築するには、このメンバー関数を呼び出します。  
  
```  
virtual void Requery();
```  
  
### <a name="remarks"></a>コメント  
 いくつかのレコードが返された場合、最初のレコードが現在のレコードになります。  
  
 追加と削除、または他のユーザーがデータ ソースに対して実行するを反映するように、レコード セットのためを呼び出してレコード セットをリビルドする必要があります**Requery**します。 レコード セットがダイナセットの場合は、自動的に、その既存のレコード (ただし追加は除きます) に対してや他のユーザーが行った更新を反映します。 レコード セットがスナップショットである場合は、呼び出す必要があります**Requery**編集内容を他のユーザーだけでなく追加および削除を反映するようにします。  
  
 ダイナセットまたはスナップショットのどちらかを呼び出して**Requery**パラメーターの値を使用してレコード セットを再構築するとき。 設定して、新しいフィルターまたは並べ替えを設定[か](#m_strfilter)と[レコード](#m_strsort)呼び出す前に**Requery**します。 新しい値を呼び出す前にパラメーター データ メンバーに割り当てることで新しいパラメーターを設定**Requery**します。  
  
 レコード セットを再構築に失敗した場合、レコード セットは閉じられます。 呼び出す前に**Requery**を呼び出して、レコード セットを表示できるかどうかを指定できます、 [CanRestart](#canrestart)メンバー関数。 `CanRestart`限りませんが**Requery**は成功します。  
  
> [!CAUTION]
>  呼び出す**Requery**を呼び出した後にのみ**開く**します。  
  
> [!NOTE]
>  呼び出す[Requery](#requery) DAO ブックマークを変更します。  
  
 呼び出すことができない**Requery**ダイナセット型またはスナップショットの種類のレコード セットを呼び出す場合に`CanRestart`0 を返しますに使用するテーブル型のレコード セットでも。  
  
 両方`IsBOF`と`IsEOF`以外を返します。 呼び出し後**Requery**、いくつかのレコードとレコード セットはデータを含まないクエリが返されませんでした。  
  
 関連情報については、「Requery メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-nameseeka--cdaorecordsetseek"></a><a name="seek"></a>CDaoRecordset::Seek  
 現在の指定された条件は、インデックスし、そのレコードを現在のレコードを満たしているインデックス付きのテーブル型のレコード セット オブジェクト内でレコードを検索するには、このメンバー関数を呼び出します。  
  
```  
BOOL Seek(
    LPCTSTR lpszComparison,  
    COleVariant* pKey1,  
    COleVariant* pKey2 = NULL,  
    COleVariant* pKey3 = NULL);

 
BOOL Seek(
    LPCTSTR lpszComparison,  
    COleVariant* pKeyArray,  
    WORD nKeys);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszComparison`  
 次の文字列式のいずれか:"<",></",>\<="、「=」、"> ="、または">"です。  
  
 `pKey1`  
 ポインター、 [COleVariant](../../mfc/reference/colevariant-class.md)値を持つが、インデックスの最初のフィールドに対応します。 必須です。  
  
 *pKey2*  
 ポインター、`COleVariant`存在する場合に、値を持つが、インデックスでは、2 番目のフィールドに対応します。 既定値は**NULL**します。  
  
 *pKey3*  
 ポインター、`COleVariant`存在する場合に、値を持つが、インデックスでは、3 番目のフィールドに対応します。 既定値は**NULL**します。  
  
 *pKeyArray*  
 Variant の配列へのポインター。 配列のサイズは、インデックスのフィールドの数に対応します。  
  
 *nKeys*  
 これは、インデックスのフィールドの数と、配列のサイズに対応する整数。  
  
> [!NOTE]
>  キーには、ワイルドカードを指定しません。 ワイルドカードと、`Seek`に一致するレコードを返しません。  
  
### <a name="return-value"></a>戻り値  
 一致するレコードが見つかった場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>コメント  
 2 つ目の (配列) のバージョンを使用して`Seek`以上の&4; つのフィールドのインデックスを処理します。  
  
 `Seek`高度なインデックスがテーブル型のレコード セットの検索を有効にします。 呼び出して、現在のインデックスを設定する必要があります`SetCurrentIndex`呼び出す前に`Seek`します。 インデックスは一意でないキー フィールドまたはフィールドを指定する場合`Seek`条件を満たす最初のレコードを見つけます。 インデックスを設定しないと、例外がスローされます。  
  
 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要が明示的に宣言する ANSI です。 使用してそのため、 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **、** `vtSrc` **)**形式を持つコンス トラクターの`vtSrc`に設定`VT_BSTRT`(ANSI) またはを使用して、 **COleVariant**関数[SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **、** `vtSrc` **)**と`vtSrc`に設定`VT_BSTRT`します。  
  
 呼び出すと`Seek`、渡す&1; つまたは複数のキー値と比較演算子 ("<",></",>\<="、「=」、"> ="、または">") です。 `Seek`指定されたキー フィールドを検索しで指定された条件を満たす最初のレコードでは、検索`lpszComparison`と`pKey1`です。 見つかったら、 `Seek` 、0 以外を返すし、そのレコードは現在、します。 場合`Seek`、一致の検索に失敗`Seek`0 が返されます、および現在のレコードが定義されています。 直接に DAO を使用している場合は、NoMatch プロパティを明示的にチェックする必要があります。  
  
 場合`lpszComparison`は「=」、"> ="、または">"、`Seek`インデックスの先頭から開始します。 場合`lpszComparison`は"<" or=""> </"> <=",> </=",> `Seek`インデックスの末尾から開始し、最後に重複するインデックス エントリがない限り、逆方向に検索します。 この場合、`Seek`インデックスの最後に重複するインデックス エントリの中で任意のエントリから開始します。  
  
 存在しなくても使用する場合は、現在のレコードをする`Seek`です。  
  
 ダイナセット タイプまたは特定の条件を満たすスナップショット型のレコード セットのレコードを検索するには、検索操作を使用します。 特定の条件を満たすレコードだけでなく、すべてのレコードを含めるには、レコード間を移動する移動操作を使用します。  
  
 呼び出すことができない`Seek`のいずれかの接続されているテーブルをダイナセット型またはスナップショット タイプとしてアタッチされているテーブルを開く必要があるために、入力します。 ただしを呼び出す場合`CDaoDatabase::Open`インストール可能な ISAM データベースを直接開き、呼び出すことができます`Seek`、そのデータベース内のテーブルにが、パフォーマンスが低速です。  
  
 関連情報については、「Seek メソッド」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namesetabsolutepositiona--cdaorecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CDaoRecordset::SetAbsolutePosition  
 レコード セット オブジェクトの現在のレコードの相対レコード番号を設定します。  
  
```  
void SetAbsolutePosition(long lPosition);
```  
  
### <a name="parameters"></a>パラメーター  
 *lPosition*  
 レコード セット内の現在のレコードの序数位置に対応します。  
  
### <a name="remarks"></a>コメント  
 呼び出す`SetAbsolutePosition`ダイナセット タイプまたはスナップショットの種類のレコード セットの序数位置に基づいて特定のレコードを現在のレコード ポインターを配置することができます。 呼び出して、現在のレコード番号を確認することも[GetAbsolutePosition](#getabsoluteposition)します。  
  
> [!NOTE]
>  このメンバー関数では、ダイナセット タイプとスナップショット タイプのレコード セットに対してのみ有効です。  
  
 基になる DAO オブジェクトの AbsolutePosition プロパティの値は 0 から始まります。0 の設定は、レコード セット内の最初のレコードを表します。 格納済みのレコードと、例外をスローする MFC の数より大きい値を設定します。 呼び出して、レコード セット内のデータが設定されたレコードの数を指定できます、`GetRecordCount`メンバー関数。  
  
 現在のレコードが削除された場合は、AbsolutePosition プロパティの値が定義されていませんし、MFC は、参照されている場合に例外をスローします。 新しいレコードは、シーケンスの末尾に追加されます。  
  
> [!NOTE]
>  このプロパティは、レコード番号の代わりとして使用するものではありません。 ブックマークはまだ保持して、指定した位置に戻るための推奨される方法であり、すべての種類のブックマークをサポートしているレコード セット オブジェクトで現在のレコードを配置する唯一の方法です。 具体的には、前のレコードが削除されたときに、指定されたレコードの位置が変わります。 また、特定のレコードがある絶対位置を同じ場合は、レコード セットを再作成を使用して SQL ステートメントを使用して作成された場合を除き、レコード セット内の各レコードの順序は保証されないため保証はありません、 **ORDERBY**句。  
  
 関連情報については、DAO ヘルプの「AbsolutePosition プロパティ」を参照してください。  
  
##  <a name="a-namesetbookmarka--cdaorecordsetsetbookmark"></a><a name="setbookmark"></a>CDaoRecordset::SetBookmark  
 指定されたブックマークを含むレコードをレコード セットを配置するには、このメンバー関数を呼び出します。  
  
```  
void SetBookmark(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 `varBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md)特定のレコードのブックマークの値を表すオブジェクト。  
  
### <a name="remarks"></a>コメント  
 レコード セット オブジェクトを作成したり開いたりすると、各レコードは既に一意のブックマークを持っています。 呼び出して現在のレコードのブックマークを取得し`GetBookmark`に値を保存して、`COleVariant`オブジェクトです。 後で呼び出すことでそのレコードを返すことができます`SetBookmark`保存したブックマークの値を使用します。  
  
> [!NOTE]
>  呼び出す[Requery](#requery) DAO ブックマークを変更します。  
  
 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要が明示的に宣言する ANSI です。 使用してそのため、 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **、** `vtSrc` **)**形式を持つコンス トラクターの`vtSrc`に設定`VT_BSTRT`(ANSI) またはを使用して、 **COleVariant**関数[SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **、** `vtSrc` **)**と`vtSrc`に設定`VT_BSTRT`します。  
  
 関連情報については、トピックを参照して、「ブックマーク プロパティ」とブックマークを設定のプロパティ"DAO のヘルプでできます。  
  
##  <a name="a-namesetcachesizea--cdaorecordsetsetcachesize"></a><a name="setcachesize"></a>CDaoRecordset::SetCacheSize  
 キャッシュするレコードの数を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetCacheSize(long lSize);
```  
  
### <a name="parameters"></a>パラメーター  
 `lSize`  
 レコードの数を指定します。 一般的な値は 100 です。 0 の設定は、キャッシュを無効にします。 設定は、5 ~ 1200 レコード間で指定する必要があります。 キャッシュは、相当量のメモリを使用できます。  
  
### <a name="remarks"></a>コメント  
 キャッシュは、アプリケーションの実行中に、データをもう一度要求は、最近、サーバーから取得するデータを保持するローカル メモリ内のスペースです。 データ キャッシュでは、ダイナセット タイプの recordset オブジェクトを経由してリモート サーバーからデータを取得するアプリケーションのパフォーマンスが向上します。 データが要求されると、Microsoft Jet データベース エンジン、要求されたデータのキャッシュまずチェック時間がかかると、サーバーから取得するには。 ODBC データ ソースから発生しないデータがキャッシュに保存されません。  
  
 アタッチのテーブルなどの ODBC データ ソースには、ローカル キャッシュを持つことができます。 キャッシュを作成するには、リモート データ ソースの呼び出しから recordset オブジェクトを開く、`SetCacheSize`と`SetCacheStart`メンバー関数と、呼び出し、`FillCache`メンバー関数または移動操作のいずれかを使用して、レコード間のステップです。 `lSize`のパラメーター、`SetCacheSize`メンバー関数は、アプリケーションが同時に使用できるレコードの数に基づくことができます。 たとえば、レコード セットは、画面に表示されるデータのソースとして使用されている場合を渡す、 `SetCacheSize``lSize` 20 20 個のレコードを同時に表示する場合のパラメーターです。  
  
 関連情報については、DAO のヘルプ トピック「CacheSize、CacheStart プロパティ」を参照してください。  
  
##  <a name="a-namesetcachestarta--cdaorecordsetsetcachestart"></a><a name="setcachestart"></a>CDaoRecordset::SetCacheStart  
 キャッシュすることをレコード セット内の最初のレコードのブックマークを指定するには、このメンバー関数を呼び出します。  
  
```  
void SetCacheStart(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>パラメーター  
 `varBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md)キャッシュされるレコード セット内の最初のレコードのブックマークを指定します。  
  
### <a name="remarks"></a>コメント  
 すべてのレコードのブックマークの値を使用する、`varBookmark`のパラメーター、`SetCacheStart`メンバー関数。 現在のレコードを含む、キャッシュを開始するには、レコードを使用してそのブックマークを確立するレコード[SetBookmark](#setbookmark)、ブックマーク値のパラメーターとして渡すと、`SetCacheStart`メンバー関数。  
  
 Microsoft Jet データベース エンジンが、キャッシュからキャッシュの範囲内のレコードを要求し、サーバーからのキャッシュの範囲外のレコードを要求します。  
  
 キャッシュから取得されたレコードでは、他のユーザーがデータ ソースに同時に行われた変更は反映されません。  
  
 キャッシュされたすべてのデータの更新を強制的に渡す、`lSize`のパラメーター `SetCacheSize` 0 として呼び出す`SetCacheSize`もう一度では、キャッシュのサイズを最初に要求しを呼び出す、`FillCache`メンバー関数。  
  
 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要が明示的に宣言する ANSI です。 使用してそのため、 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **、** `vtSrc` **)**形式を持つコンス トラクターの`vtSrc`に設定`VT_BSTRT`(ANSI) またはを使用して、 **COleVariant**関数[SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **、** `vtSrc` **)**と`vtSrc`に設定`VT_BSTRT`します。  
  
 関連情報については、トピックを参照して、CacheSize、CacheStart プロパティ"DAO のヘルプでできます。  
  
##  <a name="a-namesetcurrentindexa--cdaorecordsetsetcurrentindex"></a><a name="setcurrentindex"></a>CDaoRecordset::SetCurrentIndex  
 テーブル型のレコード セットのインデックスを設定するには、このメンバー関数を呼び出します。  
  
```  
void SetCurrentIndex(LPCTSTR lpszIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszIndex`  
 設定するインデックスの名前を含むポインター。  
  
### <a name="remarks"></a>コメント  
 ベース テーブルのレコードは、特定の順序では格納されません。 インデックスを設定すると、データベースから返されるレコードの順序変更が、レコードが格納されている順序には影響しません。 指定したインデックスは、既に定義されている必要があります。 存在しないインデックス オブジェクトを使用しようとする場合、またはを呼び出すときに、インデックスが設定されていない場合[Seek](#seek)MFC は、例外をスローします。  
  
 呼び出して、テーブルの新しいインデックスを作成することができます[CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex)を呼び出すことによって、基になるテーブルのインデックス コレクションに新しいインデックスを追加すること[CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append)、および、レコード セットを再開します。  
  
 テーブル型のレコード セットから返されるレコードの順序には基になるテーブルの定義されたインデックスでのみを指定できます。 その他の順序でレコードを並べ替えるには、ダイナセット型または SQL を使用して、スナップショットの種類のレコード セットを開くことができます**ORDERBY**に格納されている句[CDaoRecordset::m_strSort](#m_strsort)します。  
  
 関連情報については、トピック「インデックス オブジェクト」と定義の DAO のヘルプでは、"現在のインデックス"を参照してください。  
  
##  <a name="a-namesetfielddirtya--cdaorecordsetsetfielddirty"></a><a name="setfielddirty"></a>CDaoRecordset::SetFieldDirty  
 このメンバー関数を呼び出して、変更の有無、レコード セットのフィールド データ メンバーにフラグを設定します。  
  
```  
void SetFieldDirty(
    void* pv,  
    BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 レコード セット内のフィールド データ メンバーのアドレスを格納または**NULL**します。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では「値を持たない」という意味)。  
  
 `bDirty`  
 **TRUE**かどうか、フィールド データ メンバーは「ダーティ」(変更されている) としてフラグが付けられます。 それ以外の場合**FALSE**かどうか、フィールド データ メンバーは「クリーン」(変更されていない) としてフラグが付けられます。  
  
### <a name="remarks"></a>コメント  
 未変更としてフィールドをマークすることにより、フィールドは更新されません。  
  
 フレームワークでは、確実に DAO レコード フィールド エクス (チェンジ DFX) メカニズムによって、データ ソースのレコードに書き込まれる、フィールド データ メンバーを変更します。 フィールドの値を変更すると、通常フィールドを設定、ダーティ、自動的を呼び出す必要があります頻度の低い`SetFieldDirty`が自分で場合もありますようにすることも、列が明示的に更新または挿入するフィールド データ メンバーがどのような値に関係なく。 DFX 機構は、の使用も採用されています。 **PSEUDONULL**します。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)します。  
  
 ダブル バッファリング機構が使用されていない場合、フィールドの値を変更しては自動的に設定されません、フィールドをダーティと。 この場合、フィールドをダーティとして明示的に設定する必要があります。 含まれているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
> [!NOTE]
>  呼び出した後にのみ、このメンバー関数を呼び出して[編集](#edit)または[AddNew](#addnew)します。  
  
 使用して**NULL**関数の最初の引数はすべてに、関数を適用するため**outputColumn**フィールドいない**param**フィールド`CDaoFieldExchange`します。 たとえばの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase&6;](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドが影響を受けません。  
  
 動作する、 **param**、個々 の実際のアドレスを指定する必要があります**param**など、作業します。  
  
 [!code-cpp[NVC_MFCDatabase&#7;](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]  
  
 つまり、すべて設定することはできません**param**フィールドを**NULL**の場合と、 **outputColumn**フィールドです。  
  
 `SetFieldDirty`によって実装され`DoFieldExchange`します。  
  
##  <a name="a-namesetfieldnulla--cdaorecordsetsetfieldnull"></a><a name="setfieldnull"></a>CDaoRecordset::SetFieldNull  
 このメンバー関数を呼び出してレコード セット (具体的には値を持たない) Null または null 以外のフィールド データ メンバーにフラグを設定します。  
  
```  
void SetFieldNull(
    void* pv,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pv`  
 レコード セット内のフィールド データ メンバーのアドレスを格納または**NULL**します。 場合**NULL**、レコード セット内のすべてのフィールド データ メンバーのフラグが付けられます。 (C++ **NULL**は Null の場合と同じデータベース用語では「値を持たない」という意味)。  
  
 `bNull`  
 以外の場合は、フィールド データ メンバーは、値 (Null) がないものとしてフラグが付けられます。 フィールド データ メンバーは、Null としてフラグを設定する場合は、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `SetFieldNull`フィールドにバインドされているため、`DoFieldExchange`メカニズムです。  
  
 新しいレコードをレコード セットに追加するときにすべてのフィールド データ メンバーは最初に Null 値に設定され「ダーティ」(変更されている) フラグが付けられます。 データ ソースからレコードを取得するときにその列既に値があるかは Null です。 Null の場合、フィールドに適切でない場合、 [CDaoException](../../mfc/reference/cdaoexception-class.md)がスローされます。  
  
 たとえば、具体的には呼び出し、値を持っていないと、現在のレコードのフィールドを指定する場合、ダブル バッファリングのメカニズムを使用している場合`SetFieldNull`と`bNull`に設定**TRUE**に Null としてフラグを設定します。 Null フィールドが対象としてマーク済みしようとしています、値を指定する場合は、単にその新しい値を設定します。 Null フラグを削除する必要はありません`SetFieldNull`します。 フィールドの null が許可されたかどうかを確認するのには、呼び出す[調べる](#isfieldnullable)します。  
  
 ダブル バッファリング機構を使用していない場合、フィールドの値を変更しては自動的に設定されませんフィールド ダーティと Null 以外。 ダーティと非 Null フィールドを明示的に設定する必要があります。 含まれているフラグ[m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)このフィールドの自動チェックを制御します。  
  
 DFX 機構の使用を採用して**PSEUDONULL**します。 詳細については、次を参照してください。 [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)します。  
  
> [!NOTE]
>  呼び出した後にのみ、このメンバー関数を呼び出して[編集](#edit)または[AddNew](#addnew)します。  
  
 使用して**NULL**関数の最初の引数が関数をのみに適用の**outputColumn**フィールドいない**param**フィールド`CDaoFieldExchange`します。 たとえばの呼び出し  
  
 [!code-cpp[NVC_MFCDatabase&#8;](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]  
  
 セットのみが**outputColumn**フィールドを**NULL**です。**param**フィールドが影響を受けません。  
  
##  <a name="a-namesetfieldvaluea--cdaorecordsetsetfieldvalue"></a><a name="setfieldvalue"></a>たび  
 順序位置で、または文字列の値を変更することで、フィールドの値を設定するには、このメンバー関数を呼び出します。  
  
```  
virtual void SetFieldValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetFieldValue(
    int nIndex,  
    const COleVariant& varValue);

 
void SetFieldValue(
    LPCTSTR lpszName,  
    LPCTSTR lpszValue);

 
void SetFieldValue(
    int nIndex,  
    LPCTSTR lpszValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 フィールドの名前を含む文字列へのポインター。  
  
 `varValue`  
 参照、 [COleVariant](../../mfc/reference/colevariant-class.md)フィールドの内容の値を表すオブジェクト。  
  
 `nIndex`  
 (0 から始まる)、レコード セットのフィールド コレクション内のフィールドの序数位置を表す整数。  
  
 `lpszValue`  
 フィールドの内容の値を含む文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
 使用`SetFieldValue`と[GetFieldValue](#getfieldvalue)実行時ではなくで静的にバインド列を使用してフィールドを動的にバインドする、 [DoFieldExchange](#dofieldexchange)メカニズムです。  
  
 UNICODE のレコード セットを作成するので、いずれかの形式を使用する必要がありますに注意してください`SetFieldValue`を含まない、`COleVariant`パラメーター、または`COleVariant`オブジェクト必要が明示的に宣言する ANSI です。 使用してそのため、 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **、** `vtSrc` **)**形式を持つコンス トラクターの`vtSrc`に設定`VT_BSTRT`(ANSI) またはを使用して、 **COleVariant**関数[SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **、** `vtSrc` **)**と`vtSrc`に設定`VT_BSTRT`します。  
  
 関連情報については、"フィールド Object"、「値プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namesetfieldvaluenulla--cdaorecordsetsetfieldvaluenull"></a><a name="setfieldvaluenull"></a>CDaoRecordset::SetFieldValueNull  
 フィールドを Null 値に設定するには、このメンバー関数を呼び出します。  
  
```  
void SetFieldValueNull(int nIndex);  
void SetFieldValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 から始まるインデックスで検索する場合、レコード セット内のフィールドのインデックス。  
  
 `lpszName`  
 名前で検索する場合、レコード セット内のフィールドの名前。  
  
### <a name="remarks"></a>コメント  
 C++ **NULL** Null の場合、データベース用語では、これと同じではありません「値を持たない」。  
  
 関連情報については、"フィールド Object"、「値プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="a-namesetlockingmodea--cdaorecordsetsetlockingmode"></a><a name="setlockingmode"></a>CDaoRecordset::SetLockingMode  
 レコード セットのロックの種類を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetLockingMode(BOOL bPessimistic);
```  
  
### <a name="parameters"></a>パラメーター  
 *bPessimistic*  
 ロックの種類を示すフラグです。  
  
### <a name="remarks"></a>コメント  
 呼び出すと、すぐにロックされているときに排他ロックが実際には、編集しているレコードを含む 2 K ページ、**編集**メンバー関数。 ページのロックが解除されてを呼び出したときに、**更新**または**閉じる**メンバー関数または移動または検索操作のいずれかです。  
  
 レコードの更新中にのみ、レコードを含む 2 K ページがロックされているオプティミスティック ロックが有効の場合、**更新**メンバー関数。  
  
 ページがロックされている場合その他のユーザーを編集できません同じページ上のレコード。 呼び出した場合`SetLockingMode`とは、0 以外の値を渡すをし他のユーザーには既にロックされているページを呼び出すときに、例外がスローされます**編集**します。 他のユーザーは、ロックされたページからデータを読み取ることができます。  
  
 呼び出した場合`SetLockingMode`、ゼロ値の以降の呼び出し**更新**ページが別のユーザーによってロックされている間には、例外が発生します。 別のユーザーが、レコードに加えられた変更を参照してください (し、変更内容が失われる)、電話、`SetBookmark`メンバー関数を現在のレコードのブックマークの値。  
  
 ODBC データ ソースを使用する場合、ロックのモードは常にオプティミスティックです。  
  
##  <a name="a-namesetparamvaluea--cdaorecordsetsetparamvalue"></a><a name="setparamvalue"></a>CDaoRecordset::SetParamValue  
 このメンバー関数を呼び出してレコード セットの実行時にパラメーターの値を設定します。  
  
```  
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 クエリ定義のパラメーター コレクション内のパラメーターの数値の位置。  
  
 `var`  
 値が設定されます。「解説」を参照してください。  
  
 `lpszName`  
 パラメーターを設定する値の名前。  
  
### <a name="remarks"></a>コメント  
 パラメーター既に、レコード セットの SQL 文字列の一部として設定されていなければなりません。 名前またはコレクションのインデックス位置のいずれかのパラメーターを表示できます。  
  
 として設定する値を指定して、`COleVariant`オブジェクトです。 目的の値と型の設定については、`COleVariant`オブジェクト、クラスを参照して[COleVariant](../../mfc/reference/colevariant-class.md)します。 UNICODE のレコード セットを作成していない場合、`COleVariant`オブジェクト必要が明示的に宣言する ANSI です。 使用してそのため、 [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **、** `vtSrc` **)**形式を持つコンス トラクターの`vtSrc`に設定`VT_BSTRT`(ANSI) またはを使用して、 **COleVariant**関数[SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **、** `vtSrc` **)**と`vtSrc`に設定`VT_BSTRT`します。  
  
##  <a name="a-namesetparamvaluenulla--cdaorecordsetsetparamvaluenull"></a><a name="setparamvaluenull"></a>CDaoRecordset::SetParamValueNull  
 このメンバー関数を呼び出して、パラメーターを Null 値に設定します。  
  
```  
void SetParamValueNull(int nIndex);  
void SetParamValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIndex`  
 0 から始まるインデックスで検索する場合、レコード セット内のフィールドのインデックス。  
  
 `lpszName`  
 名前で検索する場合、レコード セット内のフィールドの名前。  
  
### <a name="remarks"></a>コメント  
 C++ **NULL** Null の場合、データベース用語では、これと同じではありません「値を持たない」。  
  
##  <a name="a-namesetpercentpositiona--cdaorecordsetsetpercentposition"></a><a name="setpercentposition"></a>CDaoRecordset::SetPercentPosition  
 このメンバー関数を呼び出して、レコード セット内のレコードの割合に基づいているレコード セット オブジェクトの現在のレコードのおおよその位置を変更する値を設定します。  
  
```  
void SetPercentPosition(float fPosition);
```  
  
### <a name="parameters"></a>パラメーター  
 *fPosition*  
 0 ～ 100 の値。  
  
### <a name="remarks"></a>コメント  
 移動することで、最後のレコードを呼び出す前に、recordset をまず作成ダイナセット型またはレコードを使用する場合`SetPercentPosition`します。 呼び出した場合`SetPercentPosition`、レコード セットを完全に設定するには、前に、移動の量が、アクセスできるレコード数の値で指定された基準としたが[GetRecordCount](#getrecordcount)します。 行うことができますし、最後のレコードを呼び出して`MoveLast`します。  
  
 呼び出す`SetPercentPosition`、その値に対応するおおよその位置にあるレコードが最新になった。  
  
> [!NOTE]
>  呼び出す`SetPercentPosition`を移動、レコード セット内の特定のレコードを現在のレコードはお勧めしません。 呼び出す、 [SetBookmark](#setbookmark)メンバー関数を使用します。  
  
 関連情報については、DAO ヘルプの「PercentPosition プロパティ」を参照してください。  
  
##  <a name="a-nameupdatea--cdaorecordsetupdate"></a><a name="update"></a>CDaoRecordset::Update  
 このメンバー関数を呼び出した後、`AddNew`または**編集**メンバー関数。  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>コメント  
 この呼び出しが完了するために必要な`AddNew`または**編集**操作します。  
  
 両方とも`AddNew`と**編集**データ ソースに保存するための追加または編集したデータが置かれている編集バッファーを準備します。 **更新プログラム**データを保存します。 マークまたは変更されたものとして検出されたフィールドのみが更新されます。  
  
 データ ソースは、トランザクションをサポートする場合は、**更新**を呼び出す (およびその対応する`AddNew`または**編集**呼び出し)、トランザクションの一部です。  
  
> [!CAUTION]
>  呼び出した場合**更新**最初にいずれかの操作を呼び出すこと`AddNew`または**編集**、**更新**スロー、`CDaoException`です。 呼び出した場合`AddNew`または**編集**、呼び出す必要があります**更新**を呼び出す前に[MoveNext](#movenext)またはレコード セットかデータ ソース接続を閉じます。 それ以外の場合、変更は、警告を表示せず失われます。  
  
 時刻からロックは、レコードがレコード セット オブジェクトがマルチ ユーザー環境で排他ロックされると、**編集**更新が完了するまでに使用します。 レコード セットがやロックされている場合は、レコードがロックされ、データベースで更新される直前に、編集前のレコードと比較します。 呼び出されるため、レコードが変更された場合**編集**、**更新**操作が失敗して、MFC は例外をスローします。 ロック モードを変更する`SetLockingMode`です。  
  
> [!NOTE]
>  オプティミスティック ロックは常に、インストール可能な ISAM、ODBC などの外部データベース形式で使用します。  
  
 関連情報については、「AddNew メソッド」、"ただし Method"、「メソッドの削除」、「LastModified プロパティ」、「Update メソッド」および「EditMode プロパティ」DAO ヘルプのトピックを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)

