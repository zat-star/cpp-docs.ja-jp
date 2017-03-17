---
title: "どちらのクラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], DAO
- tabledefs [C++]
- CDaoTableDef class
- database tables [C++], attached table definition
- database tables [C++], base table definition
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
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
ms.openlocfilehash: 8bfd0ef3c63c243cabb0a4f841ba278fbeed4ae8
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledef-class"></a>どちらのクラス
ベース テーブル、またはアタッチ テーブルの格納された定義を表現します。  
  
## <a name="syntax"></a>構文  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|構築、**どちら**オブジェクトです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoTableDef::Append](#append)|データベースに新しいテーブルを追加します。|  
|[CDaoTableDef::CanUpdate](#canupdate)|テーブルを更新する場合は&0; 以外を返します (フィールドやテーブルのプロパティの定義を変更することができます)。|  
|[CDaoTableDef::Close](#close)|開いているテーブル定義を終了します。|  
|[CDaoTableDef::Create](#create)|使用してデータベースに追加できるテーブルを作成[Append](#append)します。|  
|[CDaoTableDef::CreateField](#createfield)|テーブルのフィールドを作成するには、呼び出されます。|  
|[CDaoTableDef::CreateIndex](#createindex)|テーブルのインデックスを作成するには、呼び出されます。|  
|[CDaoTableDef::DeleteField](#deletefield)|テーブルからフィールドを削除するには、呼び出されます。|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|テーブルからインデックスを削除するには、呼び出されます。|  
|[CDaoTableDef::GetAttributes](#getattributes)|1 つまたは複数の特性を示す値を返す、`CDaoTableDef`オブジェクトです。|  
|[CDaoTableDef::GetConnect](#getconnect)|テーブルのソースに関する情報を示す値を返します。|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|基になるベース テーブルの日付と時刻を返す、`CDaoTableDef`オブジェクトが作成されました。|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|ベース テーブルのデザインに加えられた最新の変更日時を返します。|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|テーブル内のフィールドの数を表す値を返します。|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|テーブルの特定の種類のフィールドについての情報を返します。|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|テーブルのインデックスの数を返します。|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|特定の種類のテーブルのインデックスに関する情報を返します。|  
|[CDaoTableDef::GetName](#getname)|テーブルのユーザー定義名を返します。|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|テーブルのレコードの数を返します。|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|ソース データベースに接続されているテーブルの名前を指定する値を返します。|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|変更されたか、テーブルに追加するフィールドのデータを検証する値を返します。|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|フィールド オブジェクトの値が指定した検証規則を満たしていない場合、アプリケーションで表示されるメッセージのテキストを示す値を返します。|  
|[CDaoTableDef::IsOpen](#isopen)|テーブルの場合&0; 以外を返しますが開きます。|  
|[CDaoTableDef::Open](#open)|開き、データベースに格納されている既存のテーブル定義のテーブル定義のコレクションです。|  
|[CDaoTableDef::RefreshLink](#refreshlink)|アタッチ テーブルの接続情報を更新します。|  
|[CDaoTableDef::SetAttributes](#setattributes)|1 つまたは複数の特性を示す値を設定、`CDaoTableDef`オブジェクトです。|  
|[CDaoTableDef::SetConnect](#setconnect)|テーブルのソースに関する情報を提供する値を設定します。|  
|[CDaoTableDef::SetName](#setname)|テーブルの名前を設定します。|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|ソース データベースに接続されているテーブルの名前を指定する値を設定します。|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|変更またはテーブルに追加するフィールドのデータを検証する値を設定します。|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|フィールド オブジェクトの値が指定した検証規則を満たしていない場合、アプリケーションで表示されるメッセージのテキストを指定する値を設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|テーブル定義のオブジェクトを基になる DAO インターフェイスへのポインター。|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|このテーブルのソース データベースです。|  
  
## <a name="remarks"></a>コメント  
 各 DAO データベース オブジェクトは、保存されているすべての DAO tabledef オブジェクトを含むテーブル定義と呼ばれる、コレクションを保持します。  
  
 使用してテーブル定義を操作する、`CDaoTableDef`オブジェクトです。 たとえば、次のように操作できます。  
  
-   データベース内の任意のローカル、接続されている、または外部テーブルのフィールドおよびインデックスの構造を確認します。  
  
-   呼び出す、`SetConnect`と`SetSourceTableName`アタッチされているテーブルおよび使用するメンバー関数、`RefreshLink`メンバー関数への接続を更新するには、テーブルが接続されています。  
  
-   呼び出す、`CanUpdate`かどうかは、テーブル内のフィールド定義を編集するかを調べます。  
  
-   取得または設定を使用して検証条件、`GetValidationRule`と`SetValidationRule`、および`GetValidationText`と`SetValidationText`メンバー関数。  
  
-   使用して、**開く**メンバー関数、テーブル、ダイナセット、またはスナップショットの種類を作成する`CDaoRecordset`オブジェクトです。  
  
    > [!NOTE]
    >  DAO データベース クラスは、ODBC Open Database Connectivity () を基 MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"というプレフィックスが付いています。 DAO クラスで ODBC データ ソースにアクセスできます。Microsoft Jet データベース エンジンに固有であるために、DAO クラスは一般に優れた機能を提供します。  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>既存のテーブルを操作するか、新しいテーブルを作成、テーブル定義のオブジェクトを使用するには  
  
1.  常に、最初に構築、`CDaoTableDef`へのポインターを提供するオブジェクト、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)テーブルが所属するオブジェクトします。  
  
2.  目的に応じて、次の操作を行います。  
  
    -   既存のテーブルの名前を使用するには、定義オブジェクトを呼び出す[開く](#open)保存されているテーブルの名前を指定して、メンバー関数。  
  
    -   新しいテーブルを作成するには、テーブル定義オブジェクトを呼び出す[作成](#create)テーブルの名前を指定して、メンバー関数。 呼び出す[CreateField](#createfield)と[CreateIndex](#createindex)フィールドとインデックスをテーブルに追加します。  
  
    -   呼び出す[Append](#append)データベースのテーブル定義のコレクションに追加して、テーブルを保存します。 **作成**テーブル定義では、開いている状態を呼び出した後は**作成**呼び出さないでください**開く**します。  
  
        > [!TIP]
        >  保存されているテーブルを作成する最も簡単な方法を作成し、Microsoft Access を使用して、データベースに格納します。 そして開きし、MFC コードで使用します。  
  
 テーブル定義のオブジェクトを開くまたは作成したを使用するには、作成し、開く、`CDaoRecordset`にテーブル定義の名前を指定するオブジェクト、 **dbOpenTable**内の値、`nOpenType`パラメーター。  
  
 テーブル定義のオブジェクトを使用して作成する、`CDaoRecordset`通常を作成したか、テーブル定義を開き、上記と後、レコード セット オブジェクトを作成するを呼び出すときは、テーブル定義オブジェクトにポインターを渡すこと、object [cdaorecordset::open](../../mfc/reference/cdaorecordset-class.md#open)します。 渡すテーブル定義は、開いている状態にする必要があります。 詳細については、クラスを参照してください。 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)します。  
  
 テーブル定義オブジェクトの使用が終了したらを呼び出すその[閉じる](../../mfc/reference/cdaorecordset-class.md#close)メンバー関数は、テーブル定義のオブジェクトを破棄します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="append"></a>CDaoTableDef::Append  
 呼び出した後に、このメンバー関数を呼び出して[作成](#create)データベースにテーブル定義を保存する新しいテーブル定義オブジェクトを作成します。  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>コメント  
 関数は、データベースのテーブル定義のコレクションにオブジェクトを追加します。 追加しないことを定義する際に一時オブジェクトとして、テーブル定義を使用できますが、保存して使用する場合は、呼び出す必要があります**Append**します。  
  
> [!NOTE]
>  (Null または空の文字列を含む)、名前のないテーブルの定義を追加しようとすると、MFC は、例外をスローします。  
  
 関連情報については、DAO ヘルプの「メソッドの追加」を参照してください。  
  
##  <a name="canupdate"></a>CDaoTableDef::CanUpdate  
 判断するには、このメンバー関数を呼び出すかどうか基になるテーブルの定義、`CDaoTableDef`オブジェクトを変更できます。  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>戻り値  
 テーブルの構造 (スキーマ) を変更する場合は 0 以外 (追加またはフィールドとインデックスを削除)、それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 既定では、基になるテーブルを新しく作成された、`CDaoTableDef`オブジェクトを更新することができます、関連付けられているテーブルの基になると、`CDaoTableDef`オブジェクトを更新することはできません。 A`CDaoTableDef`結果のレコード セットが更新可能でない場合でも、オブジェクトが更新可能なあります。  
  
 関連情報については、DAO ヘルプの「更新可能なプロパティ」を参照してください。  
  
##  <a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef  
 構築、**どちら**オブジェクトです。  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDatabase`  
 ポインター、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを構築後に呼び出す必要があります、[作成](#create)または[開く](#open)メンバー関数。 オブジェクトを終了するときに呼び出す必要があります、[閉じる](#close)メンバー関数し、破棄、`CDaoTableDef`オブジェクトです。  
  
##  <a name="close"></a>CDaoTableDef::Close  
 このメンバー関数を呼び出してを閉じるし、テーブル定義のオブジェクトを解放します。  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>コメント  
 呼び出した後に通常**閉じる**で割り当てられた場合は、テーブル定義のオブジェクトを削除する**新しい**します。  
  
 呼び出すことができます[開く](#open)呼び出した後でもう一度**閉じる**します。 これにより、テーブル定義オブジェクトを再利用できます。  
  
 関連情報については、DAO ヘルプの「閉じるメソッド」を参照してください。  
  
##  <a name="create"></a>CDaoTableDef::Create  
 このメンバー関数を呼び出して新しい保存されているテーブルを作成します。  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 テーブルの名前を含む文字列へのポインター。  
  
 `lAttributes`  
 テーブル定義オブジェクトによって表されるテーブルの特性に対応する値。 ビットごとの OR を使用して、次の定数のいずれかを結合できます。  
  
|定数|説明|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet データベース エンジンを使用するデータベースの場合は、排他的に開かれてアタッチされたテーブルを示します。|  
|**dbAttachSavePWD**|Microsoft Jet データベース エンジンを使用してデータベースの場合は、ユーザー ID と接続されているテーブルのパスワードは接続情報が保存されていることを示します。|  
|**dbSystemObject**|テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|  
|**dbHiddenObject**|テーブルが、Microsoft Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|  
  
 *lpszSrcTable*  
 ソース テーブル名を含む文字列へのポインター。 既定では、この値として初期化されます**NULL**します。  
  
 `lpszConnect`  
 既定の接続文字列を含む文字列へのポインター。 既定では、この値として初期化されます**NULL**します。  
  
### <a name="remarks"></a>コメント  
 呼び出すことができます、テーブル定義を付けた後[Append](#append)をデータベースのテーブル定義のコレクションに、テーブル定義を保存します。 呼び出した後**Append**、テーブル定義が、開いている状態であり、これを使用して、作成することができます、 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)オブジェクトです。  
  
 関連情報については、DAO ヘルプの「CreateTableDef メソッド」を参照してください。  
  
##  <a name="createfield"></a>CDaoTableDef::CreateField  
 テーブルにフィールドを追加するには、このメンバー関数を呼び出します。  
  
```  
void CreateField(
    LPCTSTR lpszName,  
    short nType,  
    long lSize,  
    long lAttributes = 0);  
  
void CreateField(CDaoFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 このフィールドの名前を指定する文字列式へのポインター。  
  
 `nType`  
 フィールドのデータ型を示す値。 設定は、これらの値のいずれかになります。  
  
|型|サイズ (バイト)|説明|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 バイト|BOOL|  
|**dbByte**|1|BYTE|  
|**dbInteger**|2|int|  
|**dbLong**|4|long|  
|**dbCurrency**|9|通貨 ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|フローティング|  
|**dbDouble**|9|double|  
|**dbDate**|9|日付/時刻 ([時刻](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 – 255|テキスト ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|長いバイナリ (OLE オブジェクト) [CLongBinary](../../mfc/reference/clongbinary-class.md)または[CByteArray](../../mfc/reference/cbytearray-class.md)|  
|**dbMemo**|0|メモ ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 テキストを含むフィールドのバイト単位の最大サイズ、またはテキストまたは数値を含むフィールドの固定サイズを示す値です。 `lSize`テキスト フィールドを除くすべてのパラメーターは無視されます。  
  
 `lAttributes`  
 フィールドの特性に対応する値は、ビットごとの OR を使用して結合できます。  
  
|定数|説明|  
|--------------|-----------------|  
|**dbFixedField**|フィールド サイズは固定 (数値フィールドの既定)。|  
|**dbVariableField**|フィールド サイズは、変数 (テキスト フィールドのみ) です。|  
|**dbAutoIncrField**|新しいレコードのフィールドの値は変更できない一意の long 整数を自動的に増分されます。 Microsoft Jet データベースのテーブルのみサポートされます。|  
|**dbUpdatableField**|フィールドの値を変更できます。|  
|**dbDescending**|降順で並べ替えられます (Z ~ A または 100-0) (インデックス オブジェクトのフィールド コレクション内のフィールド オブジェクトにのみ適用) の順序。 この定数を省略した場合に昇順に並べ替えられます (A ~ Z または 0 ~ 100) 順 (既定値)。|  
  
 `fieldinfo`  
 参照、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 A **DAOField** (OLE) オブジェクトが作成され、追加のフィールド コレクションに、 **DAOTableDef** (OLE) オブジェクト。 オブジェクトのプロパティを調べる際のほか、使用することも`CDaoFieldInfo`テーブル定義内の新しいフィールドを作成するための入力パラメーターを作成します。 最初のバージョン`CreateField`は使いやすくより細かく制御する場合は、第&2; のバージョンを使用することができますが、 `CreateField`、受け取り、`CDaoFieldInfo`パラメーター。  
  
 バージョンを使用する場合`CreateField`を受け取り、`CDaoFieldInfo`パラメーター、する必要があります慎重に設定するは、次のメンバーの各、`CDaoFieldInfo`構造体。  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 残りのメンバー`CDaoFieldInfo`に設定する必要があります**0**、 **FALSE**、またはメンバーの必要に応じて、空の文字列または`CDaoException`発生する可能性があります。  
  
 関連情報については、DAO ヘルプの「CreateField メソッド」を参照してください。  
  
##  <a name="createindex"></a>CDaoTableDef::CreateIndex  
 テーブルにインデックスを追加するには、この関数を呼び出します。  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>パラメーター  
 `indexinfo`  
 参照、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。  
  
### <a name="remarks"></a>コメント  
 インデックスは、データベースのテーブルと重複するレコードが受け入れられるかどうかからアクセスされるレコードの順序を指定します。 インデックスでは、データに対する効率的なアクセスも提供します。  
  
 テーブルにインデックスを作成する必要はありません、大規模なインデックスを持たないテーブルの特定のレコードにアクセスするか、レコード セットを作成することができます時間がかかる、します。 その一方で、多くのインデックスを作成する速度が低下し更新、追加、および削除の操作をすべてのインデックスが自動的に更新します。 作成するインデックスを決定するときに、これらの要因を考慮します。  
  
 次のメンバー、`CDaoIndexInfo`構造体を設定する必要があります。  
  
- **m_strName**名前を提供する必要があります。  
  
- `m_pFieldInfos`型の配列を指す必要があります`CDaoIndexFieldInfo`構造体。  
  
- `m_nFields`配列内のフィールドの数を指定する必要があります`CDaoFieldInfo`構造体。  
  
 残りのメンバーは無視される場合に設定されます**FALSE**します。 さらに、 **m_lDistinctCount**メンバーは、インデックスの作成時に無視されます。  
  
##  <a name="deletefield"></a>CDaoTableDef::DeleteField  
 フィールドを削除し、アクセスできないようにするには、このメンバー関数を呼び出します。  
  
```  
void DeleteField(LPCTSTR lpszName);  
void DeleteField(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 既存のフィールドの名前を表す文字列式へのポインター。  
  
 `nIndex`  
 インデックスで検索する場合のテーブルの&0; から始まる Fields コレクション内のフィールドのインデックス。  
  
### <a name="remarks"></a>コメント  
 データベースに追加されていない新しいオブジェクトでこのメンバー関数を使用するとき、または[CanUpdate](#canupdate)&0; 以外を返します。  
  
 関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。  
  
##  <a name="deleteindex"></a>CDaoTableDef::DeleteIndex  
 基になるテーブルのインデックスを削除するには、このメンバー関数を呼び出します。  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 既存のインデックスの名前を表す文字列式へのポインター。  
  
 `nIndex`  
 インデックスで検索する場合のデータベースの&0; から始まる TableDefs コレクション内のインデックス オブジェクトの配列インデックス。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数を使用するには、データベースに追加されていない新しいオブジェクトでまたは[CanUpdate](#canupdate)&0; 以外を返します。  
  
 関連情報については、DAO ヘルプの「メソッドの削除」を参照してください。  
  
##  <a name="getattributes"></a>CDaoTableDef::GetAttributes  
 `CDaoTableDef`オブジェクト、戻り値の指定によって表されるテーブルの特性、`CDaoTableDef`オブジェクトし、これらの定数を加えた値を指定できます。  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>戻り値  
 1 つまたは複数の特性を示す値を返す、`CDaoTableDef`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
  
|定数|説明|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet データベース エンジンを使用するデータベースの場合は、排他的に開かれてアタッチされたテーブルを示します。|  
|**dbAttachSavePWD**|Microsoft Jet データベース エンジンを使用してデータベースの場合は、ユーザー ID と接続されているテーブルのパスワードは接続情報が保存されていることを示します。|  
|**dbSystemObject**|テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|  
|**dbHiddenObject**|テーブルが、Microsoft Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|  
|**dbAttachedTable**|テーブルが Paradox データベースなどの非 ODBC データベースからの接続されているテーブルであることを示します。|  
|**dbAttachedODBC**|Microsoft SQL Server などの ODBC データベースからの接続されているテーブルを示します。|  
  
 システム テーブルは、さまざまな内部情報を格納する Microsoft Jet データベース エンジンによって作成されるテーブルです。  
  
 非表示の表は、一時的な使用の Microsoft Jet データベース エンジンによって作成されたテーブルです。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getconnect"></a>CDaoTableDef::GetConnect  
 データ ソースの接続文字列を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`テーブルのパスとデータベースの種類を格納するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CDaoTableDef` 、接続されているテーブルを表すオブジェクト、`CString`オブジェクトは、1 つまたは&2; つの部分 (データベースの型指定子およびデータベースへのパス) で構成されます。  
  
 次の表に示すようには、このパスが、データベース ファイルを含むディレクトリの完全なパスは、前に、識別子が必要"データベース ="です。 場合によっては (Microsoft Jet や Microsoft Excel で次のようにデータベース) と、データベース パス引数で特定のファイル名が含まれています。  
  
 テーブルに[CDaoTableDef::SetConnect](#setconnect)可能なデータベースの型およびその対応するデータベースの指定子とパスを示しています。  
  
 Microsoft Jet データベースのベース テーブルを指定子は空の文字列 ("") です。  
  
 ODBC ドライバーが、テーブルにアクセス ログイン ダイアログ ボックスの最初の時刻を表示、パスワードが必要なが指定されていない場合、もう一度接続を閉じてから再度開く場合です。 接続されているテーブルがある場合、 **dbAttachSavePWD**属性に、ログイン プロンプトは表示されませんテーブルが再度開かれたとき。  
  
 関連情報については、DAO のヘルプ「プロパティの接続」を参照してください。  
  
##  <a name="getdatecreated"></a>CDaoTableDef::GetDateCreated  
 テーブルの基になる日付と時刻を判断するには、この関数を呼び出して、`CDaoTableDef`オブジェクトが作成されました。  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>戻り値  
 基になるテーブルの作成日時を含む値、`CDaoTableDef`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 日付と時刻の設定は、ベース テーブルが作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境で、矛盾を避けるため、ファイル サーバーから直接のこれらの設定を取得する必要があります。つまり、すべてのクライアントが「標準」のタイム ソースを使用する必要があります: おそらく&1; つのサーバーからです。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated  
 テーブルの基になる日付と時刻を判断するには、この関数を呼び出して、**どちら**オブジェクトが最後に更新します。  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>戻り値  
 基になるテーブルの日付と時刻を格納する値、**どちら**オブジェクトが最後に更新します。  
  
### <a name="remarks"></a>コメント  
 日付と時刻の設定は、ベース テーブルが作成または最後に更新されたコンピューターから派生します。 マルチ ユーザー環境で、矛盾を避けるため、ファイル サーバーから直接のこれらの設定を取得する必要があります。つまり、すべてのクライアントが「標準」のタイム ソースを使用する必要があります: おそらく&1; つのサーバーからです。  
  
 関連情報については、DAO ヘルプのトピックの「作成日時、LastUpdated プロパティ」を参照してください。  
  
##  <a name="getfieldcount"></a>CDaoTableDef::GetFieldCount  
 テーブルで定義されたフィールドの数を取得するには、このメンバー関数を呼び出します。  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブル内のフィールドの数。  
  
### <a name="remarks"></a>コメント  
 その値が 0 の場合に含まれないオブジェクト コレクションです。  
  
 関連情報については、DAO ヘルプの「Count プロパティ」を参照してください。  
  
##  <a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo  
 各種のテーブル定義で定義されたフィールドに関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 インデックスで検索する場合のテーブルの&0; から始まる Fields コレクション内のフィールド オブジェクトのインデックス。  
  
 `fieldinfo`  
 参照、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。  
  
 `dwInfoOptions`  
 取得するフィールドに関する情報を指定するオプションです。 使用可能なオプションは、それらの原因として何を返す関数もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`(既定値)名前、種類、サイズ、属性です。 最も高速なパフォーマンスを得るには、このオプションを使用します。  
  
- `AFX_DAO_SECONDARY_INFO`プライマリについては、プラス: 序数の位置、必要に応じて、ゼロの長さ、照合順序では、外部名、ソース フィールドに、ソース テーブルを許可します。  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報と: 検証規則、検証のテキストの既定値  
  
 `lpszName`  
 名前で検索する場合、フィールド オブジェクトの名前へのポインター。 名前は、フィールドの一意名で、最大 64 文字の文字列です。  
  
### <a name="remarks"></a>コメント  
 関数の&1; つのバージョンでは、インデックスでフィールドを検索することができます。 その他のバージョンでは、フィールドを名前で検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求するときは、そのレベルもの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getindexcount"></a>CDaoTableDef::GetIndexCount  
 このメンバー関数を呼び出して、テーブルのインデックスの数を取得します。  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブルのインデックスの数。  
  
### <a name="remarks"></a>コメント  
 その値が 0 の場合に含まれないインデックス コレクションです。  
  
 関連情報については、DAO ヘルプの「Count プロパティ」を参照してください。  
  
##  <a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo  
 各種のテーブル定義で定義されているインデックスに関する情報を取得するには、このメンバー関数を呼び出します。  
  
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
 コレクション内での位置で検索する場合のテーブルの&0; から始まるインデックス コレクション内のインデックス オブジェクトの数値インデックス。  
  
 `indexinfo`  
 参照、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。  
  
 `dwInfoOptions`  
 取得するインデックスに関する情報を指定するオプションです。 使用可能なオプションは、それらの原因として何を返す関数もここで表示されます。  
  
- `AFX_DAO_PRIMARY_INFO`名前、フィールド情報フィールドです。 最も高速なパフォーマンスを得るには、このオプションを使用します。  
  
- `AFX_DAO_SECONDARY_INFO`プライマリについては、プラス: プライマリ、Unique、Clustered、Null を無視、必要に応じて、異形式  
  
- `AFX_DAO_ALL_INFO`プライマリとセカンダリの情報と: 個別のカウント  
  
 `lpszName`  
 Index オブジェクトの名前で検索する場合の名前へのポインター。  
  
### <a name="remarks"></a>コメント  
 関数の&1; つのバージョンでは、コレクション内の位置でインデックスを検索することができます。 その他のバージョンでは、名前によってインデックスを検索することができます。  
  
 返される情報については、次を参照してください。、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)構造体。 この構造体メンバーの説明に上記の情報項目に対応するは`dwInfoOptions`です。 1 つのレベルでの情報を要求するときは、そのレベルもの情報を取得します。  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="getname"></a>CDaoTableDef::GetName  
 基になるテーブルのユーザー定義名を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>戻り値  
 テーブルのユーザー定義の名前。  
  
### <a name="remarks"></a>コメント  
 この名前は文字で始まるし、最大 64 文字を含めることができます。 数字を含めることができ、アンダー スコア文字しますが、区切り記号やスペースを含めることはできません。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="getrecordcount"></a>CDaoTableDef::GetRecordCount  
 レコードの数を調べるには、このメンバー関数を呼び出す、`CDaoTableDef`オブジェクトです。  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>戻り値  
 テーブル定義のオブジェクトにアクセスするレコードの数。  
  
### <a name="remarks"></a>コメント  
 呼び出す`GetRecordCount`テーブル型に対する`CDaoTableDef`オブジェクトがテーブル内のレコードのおおよその数を反映し、テーブルのレコードの追加し、削除、すぐに影響を受けますができます。 呼び出されるまで、レコードの数の一部としてのトランザクションが表示されますがロールバック[CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase)します。 A`CDaoTableDef`レコードのないオブジェクトが 0 のレコード数プロパティの設定です。 アタッチされているテーブルや ODBC データベースで使用する`GetRecordCount`常に-1 を返します。  
  
 関連情報については、DAO ヘルプの「RecordCount プロパティ」を参照してください。  
  
##  <a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName  
 ソース データベースのアタッチ テーブルの名前を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`場合は、ネイティブ データ テーブルに接続されているテーブルの場合、または空の文字列のソース名を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 接続されたテーブルは、Microsoft Jet データベースにリンクされている別のデータベース内のテーブルです。 アタッチ テーブルのデータは、他のアプリケーションで操作できる外部データベースに残ります。  
  
 関連情報については、DAO ヘルプの「SourceTableName プロパティ」を参照してください。  
  
##  <a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule  
 テーブル定義の検証規則を取得するには、このメンバー関数を呼び出します。  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>戻り値  
 A **CString**が変更またはテーブルに追加すると、フィールドのデータを検証するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 検証規則は、更新操作に関連して使用されます。 テーブル定義に検証規則が含まれている場合、そのテーブル定義の更新プログラムは、データが変更される前に事前に定義された条件に一致する必要があります。 変更が一致しない場合、条件の値を含む例外[GetValidationText](#getvalidationtext)がスローされます。 `CDaoTableDef`オブジェクトをこの`CString`は関連付けられているテーブルとベース テーブルの読み取り/書き込みの読み取り専用です。  
  
 関連情報については、DAO ヘルプの「ValidationRule プロパティ」を参照してください。  
  
##  <a name="getvalidationtext"></a>CDaoTableDef::GetValidationText  
 検証規則に一致しないデータが入力されたときに表示する文字列を取得するには、この関数を呼び出します。  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>戻り値  
 A`CString`検証規則に一致しないデータを入力した場合に表示されるテキストを指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 `CDaoTableDef`オブジェクトをこの`CString`は関連付けられているテーブルとベース テーブルの読み取り/書き込みの読み取り専用です。  
  
 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
##  <a name="isopen"></a>CDaoTableDef::IsOpen  
 判断するには、このメンバー関数を呼び出すかどうか、`CDaoTableDef`オブジェクトが現在開いています。  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CDaoTableDef`オブジェクトが開かれている場合は 0 です。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase  
 ポインターを含む、 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)このテーブルのオブジェクト。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef  
 DAO tabledef オブジェクト基になるは、OLE インターフェイスへのポインターを含む、`CDaoTableDef`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 DAO インターフェイスに直接アクセスする必要がある場合は、このポインターを使用します。  
  
##  <a name="open"></a>CDaoTableDef::Open  
 テーブル定義を開くには、このメンバー関数は、データベースに以前保存した呼び出しはのテーブル定義のコレクションです。  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 テーブル名を指定する文字列へのポインター。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="refreshlink"></a>CDaoTableDef::RefreshLink  
 接続されているテーブルの接続情報を更新するには、このメンバー関数を呼び出します。  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>コメント  
 呼び出して、接続されているテーブルの接続情報を変更する[SetConnect](#setconnect) 、対応する`CDaoTableDef`オブジェクトとを使用して、`RefreshLink`情報を更新するメンバー関数。 呼び出すと`RefreshLink`、接続されているテーブルのプロパティは変更されません。  
  
 強制的に、変更された接続情報を反映する、すべての開いている[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)このテーブルの定義に基づくオブジェクトを閉じる必要があります。  
  
 関連情報については、DAO ヘルプの「RefreshLink メソッド」を参照してください。  
  
##  <a name="setattributes"></a>CDaoTableDef::SetAttributes  
 1 つまたは複数の特性を示す値を設定、`CDaoTableDef`オブジェクトです。  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>パラメーター  
 `lAttributes`  
 によって表されるテーブルの特性、`CDaoTableDef`オブジェクトし、これらの定数を加えた値を指定できます。  
  
|定数|説明|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet データベース エンジンを使用するデータベースの場合は、排他的に開かれてアタッチされたテーブルを示します。|  
|**dbAttachSavePWD**|Microsoft Jet データベース エンジンを使用してデータベースの場合は、ユーザー ID と接続されているテーブルのパスワードは接続情報が保存されていることを示します。|  
|**dbSystemObject**|テーブルが、Microsoft Jet データベース エンジンによって提供されるシステム テーブルであることを示します。|  
|**dbHiddenObject**|テーブルが、Microsoft Jet データベース エンジンによって提供される非表示のテーブルであることを示します。|  
  
### <a name="remarks"></a>コメント  
 複数の属性を設定する場合は、ビットごとの OR 演算子を使用して適切な定数合計することで組み合わせることができます。 設定**dbAttachExclusive**非添付テーブルで例外が発生します。 結合、次の値も、例外が発生します。  
  
- **dbAttachExclusive |dbAttachedODBC**  
  
- **dbAttachSavePWD |dbAttachedTable**  
  
 関連情報については、DAO ヘルプの「属性プロパティ」を参照してください。  
  
##  <a name="setconnect"></a>CDaoTableDef::SetConnect  
 `CDaoTableDef`接続されているテーブルの文字列オブジェクトを表すオブジェクトは、1 つまたは&2; つの部分 (データベースの型指定子およびデータベースへのパス) で構成されます。  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszConnect`  
 ODBC またはインストール可能な ISAM ドライバーに渡す追加のパラメーターを指定する文字列式へのポインター。  
  
### <a name="remarks"></a>コメント  
 次の表に示すようには、このパスが、データベース ファイルを含むディレクトリの完全なパスは、前に、識別子が必要"データベース ="です。 場合によっては (Microsoft Jet や Microsoft Excel で次のようにデータベース) と、データベース パス引数で特定のファイル名が含まれています。  
  
> [!NOTE]
>  フォームのパス ステートメントに等号 (=) の前後に空白を含めない"データベース ドライブの =:\\\path"です。 これがスローされる例外と、接続に失敗した場合に発生します。  
  
 次の表は、可能なデータベースの型およびその対応するデータベースの指定子とパスを示します。  
  
|データベースの種類|指定子|パス|  
|-------------------|---------------|----------|  
|Jet データベース エンジンを使用して、データベース|"[ `database`];"|" `drive`:\\\ *path*\\\ *filename*.MDB"|  
|dBASE III|"dBASE III;"|" `drive`:\\\ *path*"|  
|dBASE IV|"dBASE IV;"|" `drive`:\\\ *path*"|  
|dBASE 5|"dBASE 5.0 です。"|" `drive`:\\\ *path*"|  
|Paradox 3.x|"Paradox 3.x;"|" `drive`:\\\ *path*"|  
|Paradox 4.x|"Paradox 4.x;"|" `drive`:\\\ *path*"|  
|Paradox 5.x|"Paradox 5.x;"|" `drive`:\\\ *path*"|  
|Excel 3.0|「Excel 3.0;」|" `drive`:\\\ *path*\\\ *filename*.XLS"|  
|Excel 4.0|「Excel 4.0;」|" `drive`:\\\ *path*\\\ *filename*.XLS"|  
|Excel 5.0 または Excel 95|「Excel 5.0」です。|" `drive`:\\\ *path*\\\ *filename*.XLS"|  
|Excel 97|「Excel 8.0」です。|" `drive`:\\\ *path*\ *filename*.XLS"|  
|HTML のインポート|「HTML インポート;」|" `drive`:\\\ *path*\ *filename*"|  
|HTML のエクスポート|「HTML エクスポート;」|" `drive`:\\\ *path*"|  
|テキスト|「テキスト」|"ドライブ:\\\path"|  
|ODBC|"ODBC;データベース =`database`です。UID= *user*;PWD =*パスワード*です。DSN = *datasourcename;*LOGINTIMEOUT =*秒;*"(すべてのサーバーの完全な接続文字列とは限りませんではほんの一例です。 これはパラメーター間にスペースが非常に重要です。)|なし|  
|Exchange|"Exchange です。<br /><br /> MAPILEVEL = *folderpath*です。<br /><br /> [TABLETYPE = {0 | 1};]<br /><br /> [プロファイル =*プロファイル*;]<br /><br /> [PWD =*パスワード*;]<br /><br /> [データベース = `database`;]"|*"drive*:\\\ *path*\\\ *filename*.MDB"|  
  
> [!NOTE]
>  DAO 3.5 の時点では、市販がサポートされていません。  
  
 二重の円記号を使用する必要があります (\\\\)、接続文字列にします。 既存の接続を使用して、プロパティを変更したかどうかは`SetConnect`、後で呼び出す必要があります[RefreshLink](#refreshlink)します。 使用して接続のプロパティを初期化すると`SetConnect`、呼び出しではない必要があります`RefreshLink`、テーブル定義を追加するように選択する必要があります、最初にします。  
  
 ODBC ドライバーが、テーブルにアクセス ログイン ダイアログ ボックスの最初の時刻を表示、パスワードが必要なが指定されていない場合、もう一度接続を閉じてから再度開く場合です。  
  
 接続文字列を設定することができます、`CDaoTableDef`オブジェクトに元の引数を提供することにより、**作成**メンバー関数。 型、パス、ユーザー ID、パスワード、またはデータベースの ODBC データ ソースを確認する設定を確認することができます。 詳細については、特定のドライバーのマニュアルを参照してください。  
  
 関連情報については、DAO のヘルプ「プロパティの接続」を参照してください。  
  
##  <a name="setname"></a>CDaoTableDef::SetName  
 このメンバー関数を呼び出して、テーブルのユーザー定義の名前を設定します。  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszName`  
 テーブルの名前を指定する文字列式へのポインター。  
  
### <a name="remarks"></a>コメント  
 名前では、先頭を英字にする必要があり、最大 64 文字を含めることができます。 数字を含めることができ、アンダー スコア文字しますが、区切り記号やスペースを含めることはできません。  
  
 関連情報については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
##  <a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName  
 接続されているテーブルの名前またはベース テーブルの名前を指定するには、このメンバー関数を呼び出す、`CDaoTableDef`オブジェクトが基のデータの元のソース内に存在します。  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszSrcTableName*  
 外部データベースのテーブル名を指定する文字列式へのポインター。 ベース テーブルの設定は、空の文字列 ("") です。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要がありますし、 [RefreshLink](#refreshlink)します。 このプロパティの設定は、ベース テーブルと接続されているテーブルまたはコレクションに追加されていないオブジェクトの読み取り/書き込みのでは空です。  
  
 関連情報については、DAO ヘルプの「SourceTableName プロパティ」を参照してください。  
  
##  <a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule  
 テーブル定義の検証規則を設定するには、このメンバー関数を呼び出します。  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszValidationRule*  
 操作を評価する文字列式へのポインター。  
  
### <a name="remarks"></a>コメント  
 検証規則は、更新操作に関連して使用されます。 テーブル定義に検証規則が含まれている場合、そのテーブル定義の更新プログラムは、データが変更される前に事前に定義された条件に一致する必要があります。 変更が一致しない場合、条件のテキストを含む例外[GetValidationText](#getvalidationtext)が表示されます。  
  
 検証は、Microsoft Jet データベース エンジンを使用するデータベースでのみサポートされます。 式は、ユーザー定義関数、集計関数のドメイン、SQL 集計関数、またはクエリを参照できません。 検証規則、`CDaoTableDef`オブジェクトがそのオブジェクト内の複数のフィールドを参照できます。  
  
 たとえば、名前付きフィールド`hire_date`と`termination_date`、検証規則があります。  
  
 [!code-cpp[NVC_MFCDatabase #&34;](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 関連情報については、DAO ヘルプの「ValidationRule プロパティ」を参照してください。  
  
##  <a name="setvalidationtext"></a>CDaoTableDef::SetValidationText  
 検証規則の例外のテキストを設定するには、このメンバー関数を呼び出す、 `CDaoTableDef` Microsoft Jet データベース エンジンでサポートされている、基になるベース テーブルを持つオブジェクト。  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszValidationText*  
 データを入力した場合に表示されるテキストを指定する文字列式へのポインターが有効ではありません。  
  
### <a name="remarks"></a>コメント  
 接続されているテーブルの検証のテキストを設定することはできません。  
  
 関連情報については、「プロパティ」DAO ヘルプのトピックを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)

