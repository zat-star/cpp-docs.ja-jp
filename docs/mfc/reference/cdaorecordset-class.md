---
title: "CDaoRecordset クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRecordset クラス"
  - "レコード, CDaoRecordSet"
  - "レコードセット, types"
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CDaoRecordset クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソースから選択された 1 組のレコードセットを表現します。  
  
## 構文  
  
```  
  
class CDaoRecordset : public CObject  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDaoRecordset::CDaoRecordset](../Topic/CDaoRecordset::CDaoRecordset.md)|`CDaoRecordset` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoRecordset::AddNew](../Topic/CDaoRecordset::AddNew.md)|新規レコードを追加するための準備。  加算を実行します [更新](../Topic/CDaoRecordset::Update.md)。|  
|[CDaoRecordset::CanAppend](../Topic/CDaoRecordset::CanAppend.md)|新しいレコードが [AddNew](../Topic/CDaoRecordset::AddNew.md) のメンバー関数でレコードセットに追加できる場合はを返します。|  
|[CDaoRecordset::CanBookmark](../Topic/CDaoRecordset::CanBookmark.md)|レコードセットがブックマークをサポートする場合は、を返します。|  
|[CDaoRecordset::CancelUpdate](../Topic/CDaoRecordset::CancelUpdate.md)|[AddNew](../Topic/CDaoRecordset::AddNew.md) の [&#91;編集&#93;](../Topic/CDaoRecordset::Edit.md) または操作による保留中の更新をキャンセルします。|  
|[CDaoRecordset::CanRestart](../Topic/CDaoRecordset::CanRestart.md)|レコードセットのクエリを再実行するために [&#91;再クエリ&#93;](../Topic/CDaoRecordset::Requery.md) を呼び出すことができる場合はを返します。|  
|[CDaoRecordset::CanScroll](../Topic/CDaoRecordset::CanScroll.md)|レコード間をスクロールできる場合はを返します。|  
|[CDaoRecordset::CanTransact](../Topic/CDaoRecordset::CanTransact.md)|データ ソースがトランザクションをサポートしている場合は、を返します。|  
|[CDaoRecordset::CanUpdate](../Topic/CDaoRecordset::CanUpdate.md)|レコードセットが更新できる場合はゼロを返します \(レコードを追加、更新、または削除できます\)。|  
|[CDaoRecordset::Close](../Topic/CDaoRecordset::Close.md)|レコードセットを閉じます。|  
|[CDaoRecordset::Delete](../Topic/CDaoRecordset::Delete.md)|レコードセットの現在のレコードを削除します。  削除した後で別のレコードに明示的にスクロールする必要があります。|  
|[CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)|\(両方向に\) レコードセットのフィールド データ メンバーとデータ ソース内の対応するレコード間のデータ交換に呼び出されます。  実装の DAO レコード フィールド エクスチェンジ \(DFX\)。|  
|[CDaoRecordset::Edit](../Topic/CDaoRecordset::Edit.md)|現在のレコードへの変更の準備。  編集を終了します **更新**。|  
|[CDaoRecordset::FillCache](../Topic/CDaoRecordset::FillCache.md)|ODBC データ ソースのデータを含むレコードセット オブジェクトのローカル キャッシュすべてまたは一部を塗りつぶします。|  
|[CDaoRecordset::Find](../Topic/CDaoRecordset::Find.md)|指定された基準を満たす探し、ダイナセットに型のレコードセット内の特定の文字列の最初の、を、前または最後の場所を現在のレコードを記録します。|  
|[CDaoRecordset::FindFirst](../Topic/CDaoRecordset::FindFirst.md)|指定された基準を満たす探し、ダイナセットする型またはスナップショット タイプのレコードセットの最初のレコードが現在のレコードを記録します。|  
|[CDaoRecordset::FindLast](../Topic/CDaoRecordset::FindLast.md)|指定された基準を満たす探し、ダイナセットする型またはスナップショット タイプのレコードセットの最後のレコードが現在のレコードを記録します。|  
|[CDaoRecordset::FindNext](../Topic/CDaoRecordset::FindNext.md)|指定された基準を満たす探し、ダイナセットする型またはスナップショット タイプのレコードセットの次のレコードが現在のレコードを記録します。|  
|[CDaoRecordset::FindPrev](../Topic/CDaoRecordset::FindPrev.md)|指定された基準を満たす探し、ダイナセットする型またはスナップショット タイプのレコードセットの前のレコードが現在のレコードを記録します。|  
|[CDaoRecordset::GetAbsolutePosition](../Topic/CDaoRecordset::GetAbsolutePosition.md)|レコードセット オブジェクトのレコード数を返します。|  
|[CDaoRecordset::GetBookmark](../Topic/CDaoRecordset::GetBookmark.md)|レコードのブックマークを表す値を返します。|  
|[CDaoRecordset::GetCacheSize](../Topic/CDaoRecordset::GetCacheSize.md)|ローカルで ODBC データ ソースからキャッシュするデータを含むダイナセット型のレコードセット内のレコード数を指定する値を返します。|  
|[CDaoRecordset::GetCacheStart](../Topic/CDaoRecordset::GetCacheStart.md)|キャッシュするレコードセットの最初のレコードのブックマークを示す値を返します。|  
|[CDaoRecordset::GetCurrentIndex](../Topic/CDaoRecordset::GetCurrentIndex.md)|最新インデックス付きの型テーブル `CDaoRecordset`で使用されているインデックスの名前を含む `CString` を返します。|  
|[CDaoRecordset::GetDateCreated](../Topic/CDaoRecordset::GetDateCreated.md)|返します `CDaoRecordset` のオブジェクトの基になるベース テーブルの作成日時|  
|[CDaoRecordset::GetDateLastUpdated](../Topic/CDaoRecordset::GetDateLastUpdated.md)|行われた `CDaoRecordset` のオブジェクトの基になるベース テーブルのデザインに対する直前の変更の日時を返します。|  
|[CDaoRecordset::GetDefaultDBName](../Topic/CDaoRecordset::GetDefaultDBName.md)|既定のデータ ソースの名前を返します。|  
|[CDaoRecordset::GetDefaultSQL](../Topic/CDaoRecordset::GetDefaultSQL.md)|既定の SQL 文字列を実装するために取得するために呼び出されます。|  
|[CDaoRecordset::GetEditMode](../Topic/CDaoRecordset::GetEditMode.md)|現在のレコードの編集の状態を示す値を返します。|  
|[CDaoRecordset::GetFieldCount](../Topic/CDaoRecordset::GetFieldCount.md)|レコードセットのフィールド数を表す値を返します。|  
|[CDaoRecordset::GetFieldInfo](../Topic/CDaoRecordset::GetFieldInfo.md)|特定の種類のレコードセットのフィールドに関する情報を返します。|  
|[CDaoRecordset::GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md)|レコードセットのフィールドの値を返します。|  
|[CDaoRecordset::GetIndexCount](../Topic/CDaoRecordset::GetIndexCount.md)|レコードセットの下にあるテーブル インデックスの数を取得します。|  
|[CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)|さまざまな種類のインデックスに関する情報を返します。|  
|[CDaoRecordset::GetLastModifiedBookmark](../Topic/CDaoRecordset::GetLastModifiedBookmark.md)|最後に、追加または更新されたレコードを特定するために使用します。|  
|[CDaoRecordset::GetLockingMode](../Topic/CDaoRecordset::GetLockingMode.md)|そのロックの種類は、エディット コンティニュ中に仮想あることを示す値を返します。|  
|[CDaoRecordset::GetName](../Topic/CDaoRecordset::GetName.md)|レコードセットの名前を含む `CString` を返します。|  
|[CDaoRecordset::GetParamValue](../Topic/CDaoRecordset::GetParamValue.md)|DAOParameter の基になるオブジェクトに格納されているパラメーター指定の現在の値を取得します。|  
|[CDaoRecordset::GetPercentPosition](../Topic/CDaoRecordset::GetPercentPosition.md)|合計の割合でレコード数として現在のレコードの位置を返します。|  
|[CDaoRecordset::GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|レコードセット オブジェクトにアクセスするレコード数を返します。|  
|[CDaoRecordset::GetSQL](../Topic/CDaoRecordset::GetSQL.md)|SQL 文字列をレコードセットのレコードを選択するために使用するを取得します。|  
|[CDaoRecordset::GetType](../Topic/CDaoRecordset::GetType.md)|レコードセットの型を決定するために呼び出される: テーブル型、型、ダイナセットとスナップショット型。|  
|[CDaoRecordset::GetValidationRule](../Topic/CDaoRecordset::GetValidationRule.md)|フィールドに入力されたときにデータを検証する値を含む `CString` を返します。|  
|[CDaoRecordset::GetValidationText](../Topic/CDaoRecordset::GetValidationText.md)|検証規則が満たされない場合に表示されるテキストを取得します。|  
|[CDaoRecordset::IsBOF](../Topic/CDaoRecordset::IsBOF.md)|レコードセットが前に、最初のレコード設定以外の値を返します。  現在のレコードがありません。|  
|[CDaoRecordset::IsDeleted](../Topic/CDaoRecordset::IsDeleted.md)|レコードセットが削除したレコードに配置されている場合は、を返します。|  
|[CDaoRecordset::IsEOF](../Topic/CDaoRecordset::IsEOF.md)|レコードセットが最後のレコードの後で設定された場合は、を返します。  現在のレコードがありません。|  
|[CDaoRecordset::IsFieldDirty](../Topic/CDaoRecordset::IsFieldDirty.md)|現在のレコードのフィールドが変更された場合は、を返します。|  
|[CDaoRecordset::IsFieldNull](../Topic/CDaoRecordset::IsFieldNull.md)|現在のレコードのフィールドが null の場合はを返し、値はです \(なし\)。|  
|[CDaoRecordset::IsFieldNullable](../Topic/CDaoRecordset::IsFieldNullable.md)|現在のレコードのフィールドに NULL に設定できます以外の値を返し \(値を持つ場合\)。|  
|[CDaoRecordset::IsOpen](../Topic/CDaoRecordset::IsOpen.md)|[&#91;開く&#93;](../Topic/CDaoRecordset::Open.md) が前に呼び出された場合は、を返します。|  
|[CDaoRecordset::Move](../Topic/CDaoRecordset::Move.md)|どちらの方向にも現在のレコードから指定されたレコードの数にレコードセットを設定します。|  
|[CDaoRecordset::MoveFirst](../Topic/CDaoRecordset::MoveFirst.md)|レコードセットの最初のレコードが現在のレコードを設定します。|  
|[CDaoRecordset::MoveLast](../Topic/CDaoRecordset::MoveLast.md)|レコードセットの最後のレコードが現在のレコードを設定します。|  
|[CDaoRecordset::MoveNext](../Topic/CDaoRecordset::MoveNext.md)|レコードセットの次のレコードが現在のレコードを設定します。|  
|[CDaoRecordset::MovePrev](../Topic/CDaoRecordset::MovePrev.md)|レコードセットのレコードの前に現在のレコードを設定します。|  
|[CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)|テーブル、ダイナセットとスナップショットから新しいレコードセットを作成します。|  
|[CDaoRecordset::Requery](../Topic/CDaoRecordset::Requery.md)|レコードセットのクエリを指定のレコードを更新するに再度実行します。|  
|[CDaoRecordset::Seek](../Topic/CDaoRecordset::Seek.md)|現在のインデックスに指定された条件を満たす探し、インデックス付きの型テーブルにレコードセット オブジェクトのレコードが現在のレコードを記録します。|  
|[CDaoRecordset::SetAbsolutePosition](../Topic/CDaoRecordset::SetAbsolutePosition.md)|レコードセット オブジェクトのレコード数を設定します。|  
|[CDaoRecordset::SetBookmark](../Topic/CDaoRecordset::SetBookmark.md)|指定したブックマークを含むレコードをレコードセットに設定します。|  
|[CDaoRecordset::SetCacheSize](../Topic/CDaoRecordset::SetCacheSize.md)|ローカルで ODBC データ ソースからキャッシュするデータを含むダイナセット型のレコードセット内のレコード数を指定する値を設定します。|  
|[CDaoRecordset::SetCacheStart](../Topic/CDaoRecordset::SetCacheStart.md)|キャッシュするレコードセットの最初のレコードのブックマークを指定する値を設定します。|  
|[CDaoRecordset::SetCurrentIndex](../Topic/CDaoRecordset::SetCurrentIndex.md)|テーブル タイプのレコードセットのインデックスが設定されます。|  
|[CDaoRecordset::SetFieldDirty](../Topic/CDaoRecordset::SetFieldDirty.md)|変更されるように現在のレコードのフィールドをマークします。|  
|[CDaoRecordset::SetFieldNull](../Topic/CDaoRecordset::SetFieldNull.md)|Null に現在のレコードのフィールドの値を設定します \(値を持つ場合\)。|  
|[CDaoRecordset::SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md)|レコードセットのフィールドの値を設定します。|  
|[CDaoRecordset::SetFieldValueNull](../Topic/CDaoRecordset::SetFieldValueNull.md)|Null にレコードセットのフィールドの値を設定します。  \(値を持つ場合\)。|  
|[CDaoRecordset::SetLockingMode](../Topic/CDaoRecordset::SetLockingMode.md)|エディット中に実行するロックの種類を示す値を設定します。|  
|[CDaoRecordset::SetParamValue](../Topic/CDaoRecordset::SetParamValue.md)|DAOParameter の基になるオブジェクトに格納されているパラメーター指定の現在の値を設定します|  
|[CDaoRecordset::SetParamValueNull](../Topic/CDaoRecordset::SetParamValueNull.md)|Null に指定されたパラメーターの現在の値を設定します \(値を持つ場合\)。|  
|[CDaoRecordset::SetPercentPosition](../Topic/CDaoRecordset::SetPercentPosition.md)|レコードセットの割合としておけるレコードの総数に対応する場所に現在のレコードの位置を設定します。|  
|[CDaoRecordset::Update](../Topic/CDaoRecordset::Update.md)|データ ソースの新規または編集されたデータを保存して `AddNew` または **\[編集\]** 操作を完了します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDaoRecordset::m\_bCheckCacheForDirtyFields](../Topic/CDaoRecordset::m_bCheckCacheForDirtyFields.md)|フィールドが変更されるように自動的にマークされているかどうかを示すフラグが含まれます。|  
|[CDaoRecordset::m\_nFields](../Topic/CDaoRecordset::m_nFields.md)|レコードセット クラスでフィールド データ メンバーの数と、データ ソースからレコードセット オブジェクトによって選択された列数が含まれます。|  
|[CDaoRecordset::m\_nParams](../Topic/CDaoRecordset::m_nParams.md)|レコードセット クラス—レコードセットのクエリで渡されるパラメーターの数のパラメーター データ メンバーの数。|  
|[CDaoRecordset::m\_pDAORecordset](../Topic/CDaoRecordset::m_pDAORecordset.md)|レコードセット オブジェクトの下にある DAO インターフェイスへのポインター。|  
|[CDaoRecordset::m\_pDatabase](../Topic/CDaoRecordset::m_pDatabase.md)|この結果セットのソース データベース。  [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) のオブジェクトへのポインターが格納されます。|  
|[CDaoRecordset::m\_strFilter](../Topic/CDaoRecordset::m_strFilter.md)|SQL の **WHERE** のステートメントの構築に使用される文字列が含まれています。|  
|[CDaoRecordset::m\_strSort](../Topic/CDaoRecordset::m_strSort.md)|SQL の **ORDER BY** のステートメントの構築に使用される文字列が含まれています。|  
  
## 解説  
 「レコードセットと呼ばれる」、`CDaoRecordset` のオブジェクトには、次の 3 とおりの形式にあります:  
  
-   テーブル タイプのレコードセットは、一つのデータベース テーブルからレコードをチェックするか、追加、変更、または削除するために使用できるベース テーブルを表します。  
  
-   レコードセットが更新可能なダイナセット型のレコードを変更できるクエリの結果です。  これらのレコードセットは、基になるテーブルからレコードをチェックするか、追加、変更、または削除するために使用できる一連のレコードになります。  レコードセットがダイナセット型のデータベースで一つ以上のテーブルのフィールドを含めることができます。  
  
-   スナップショット タイプのレコードセットでは、データを検索するか、またはレポートを生成するために使用できる一連のレコードの静的なコピーです。  これらのレコードセットは、データベースに一つ以上のテーブルのフィールドを含めることができますが、更新できません。  
  
 レコードセットの各フォームは、レコードセットを開いたときに修正レコードを表します。  テーブルのレコードセットがダイナセット型または型のレコードセットのレコードにスクロールすると、レコードセットが他のユーザーまたはアプリケーションの他のレコードセットによって、開いた後で行われたレコードへの変更を反映します。  \(A のスナップショット タイプのレコードセットを更新できません\)。`CDaoRecordset` を直接使用するか、`CDaoRecordset`からアプリケーション固有のレコードセット クラスを派生させることができます。  この場合、次のいずれかの操作を行うことができます。  
  
-   レコードをスクロールします。  
  
-   インデックスを設定し、[&#91;シーク&#93;](../Topic/CDaoRecordset::Seek.md) \(テーブル タイプのレコードセットのみ\) を使用してすぐにレコードを検索します。  
  
-   文字列比較に基づいてレコードを検索する: "\<"、"\<\="、"\="、"\>\="、または "\>" 型 \(ダイナセットとスナップショット タイプのレコードセット\)。  
  
-   レコードを更新し、ロック モードを指定します \(スナップショット タイプのレコードセットを除く\)。  
  
-   制約するには、レコードがデータ ソースで使用可能なから、選択したレコードセットをフィルター処理します。  
  
-   レコードセットを並べ替える。  
  
-   実行時までわからない情報を含むオプションをカスタマイズするには、レコードセットのパラメーター化します。  
  
 `CDaoRecordset` の指定を `CRecordset`クラスに似たインターフェイス並べ替える。  主な違いは、データ アクセス、クラスの `CDaoRecordset` Access データが OLE オブジェクトに基づいて \(DAO\) にすることです。  クラス `CRecordset` は、ODBC \(Open Database Connectivity\) と、DBMS の ODBC ドライバーを通じて DBMS にアクセスします。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC \(Open Database Connectivity\) に基づく MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  まだ DAO クラスと ODBC データ ソースにアクセスできます; DAO クラスは、一般に Microsoft Jet データベース エンジンに固有であるため、優れた機能を提供します。  
  
 `CDaoRecordset` を直接使用するか、`CDaoRecordset`からクラスを派生させることができます。  レコードセット クラスのどちらでも使用し、データベースを開き、`CDaoDatabase` のオブジェクトへのポインターをコンストラクターに渡してレコードセット オブジェクトを構築する。  また `CDaoRecordset` のオブジェクトを作成し、MFC は、の `CDaoDatabase` の一時的なオブジェクトを作成できます。  その後、オブジェクトがテーブル タイプのレコードセット、ダイナセット型のレコードセット、またはスナップショット タイプのレコードセットかどうかを指定する [&#91;開く&#93;](../Topic/CDaoRecordset::Open.md) のレコードセットのメンバー関数を呼び出します。  **\[開く\]** を呼び出すと、データベースのデータを選択し、最初のレコードを取得します。  
  
 オブジェクトのメンバー関数とデータ メンバーをスクロールするレコードを利用して動作します。  操作の一つに、オブジェクトがテーブル タイプのレコードセット、ダイナセット型のレコードセット、またはスナップショット タイプのレコードセットであるか、および更新可能または読み取り専用かどうかによって異なります。これは、データベース ODBC \(Open Database Connectivity\) データ ソースの機能に依存することができます。  **\[開く\]** の呼び出しが、オブジェクトの [&#91;再クエリ&#93;](../Topic/CDaoRecordset::Requery.md) のメンバー関数を呼び出すため変更または追加される可能性があるレコードを更新します。  処理を終了するときのオブジェクトの **\[閉じる\]** のメンバー関数を呼び出して、オブジェクトを破棄します。  
  
 の `CDaoRecordset`、または `CDaoRecordset`派生クラスのタイプ セーフな C\+\+ のメンバーを使用してレコード フィールドの読み取りと更新の 使用をサポートする`CDaoRecordset` DAO レコード フィールド エクスチェンジ \(DFX\)。  また [GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md) と [SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md)を使用して DFX 機構を使用せずにデータベース列の動的な連結を実行できます。  
  
 関連情報は、DAO ヘルプ トピック「レコードセット オブジェクト」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoRecordset`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)