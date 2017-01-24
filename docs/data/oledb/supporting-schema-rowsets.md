---
title: "スキーマ行セットのサポート | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB コンシューマー テンプレート, スキーマ行セット"
  - "OLE DB プロバイダー, スキーマ行セット"
  - "OLE DB, スキーマ行セット"
  - "スキーマ行セット"
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# スキーマ行セットのサポート
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

スキーマ行セットを使用すると、コンシューマーは、基になる構造やスキーマを知らなくてもデータ ストアに関する情報を取得できます。  たとえば、データ ストア内のテーブルは、ユーザー定義の階層で構成されている場合があります。この場合、スキーマに関する情報を得るにはスキーマを読み取る以外に方法はありません。別の例として、Visual C\+\+ の各種ウィザードはスキーマ行セットを使用してコンシューマーのアクセサーを生成します。コンシューマーが情報を取得できるように、プロバイダーのセッション オブジェクトは [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) インターフェイスにメソッドを公開します。  Visual C\+\+ アプリケーションでは、[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) クラスを使用して **IDBSchemaRowset** を実装します。  
  
 `IDBSchemaRowsetImpl` は、以下のメソッドをサポートします。  
  
-   [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) は、スキーマ行セットに対する制約の有効性を調べます。  
  
-   [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) は、テンプレート パラメーターで指定されたオブジェクトの COM オブジェクト作成関数を実装します。  
  
-   [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) は、特定のスキーマ行セットでユーザーがサポートする制約を指定します。  
  
-   [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) は、インターフェイスから継承したスキーマ行セットを返します。  
  
-   [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) は、インターフェイスから継承した `IDBSchemaRowsetImpl::GetRowset` を使ってアクセスできるスキーマ行セットの一覧を返します。  
  
## ATL OLE DB プロバイダー ウィザードのサポート  
 ATL OLE DB プロバイダー ウィザードは、セッション ヘッダー ファイルに以下の 3 つのスキーマ クラスを作成します。  
  
-   **C** *ShortName* **SessionTRSchemaRowset**  
  
-   **C** *ShortName* **SessionColSchemaRowset**  
  
-   **C** *ShortName* **SessionPTSchemaRowset**  
  
 これらのクラスは、スキーマ情報に関するコンシューマーの要求に応答します。OLE DB 仕様ではこれらの 3 つのスキーマ行セットをサポートするように指定されています。  
  
-   **C** *ShortName* **SessionTRSchemaRowset** は、テーブル情報 \(`DBSCHEMA_TABLES` スキーマ行セット\) の要求を処理します。  
  
-   **C** *ShortName* **SessionColSchemaRowset** は、列情報 \(**DBSCHEMA\_COLUMNS** スキーマ行セット\) の要求を処理します。  ウィザードは、これらのクラスのサンプル実装を提供します。この実装は DOS プロバイダーのスキーマ情報を返します。  
  
-   **C** *ShortName* **SessionPTSchemaRowset** は、プロバイダーの種類に関するスキーマ情報 \(**DBSCHEMA\_PROVIDER\_TYPES** スキーマ行セット\) の要求を処理します。  ウィザードに用意されている既定の実装は `S_OK` を返します。  
  
 これらのクラスをカスタマイズして、プロバイダーに適したスキーマ情報を処理できます。  
  
-   **C** *ShortName* **SessionTRSchemaRowset** では、カタログ、テーブル、および記述フィールド \(**trData.m\_szType**、**trData.m\_szTable**、**trData.m\_szDesc**\) を指定する必要があります。  ウィザードで生成された例では、1 行 \(テーブル\) だけを使用します。  他のプロバイダーは複数のテーブルを返すことがあります。  
  
-   **C** *ShortName* **SessionColSchemaRowset** では、テーブルの名前を **DBID** として渡します。  
  
## 制約の設定  
 スキーマ行セットのサポートで重要な概念は、制約の設定です。これは、`SetRestrictions` を使用して行います。  制約により、コンシューマーは一致する行だけをフェッチできます。たとえば、テーブル "MyTable" 内のすべての列を検索します。  制約は省略できます。制約が 1 つもサポートされていない場合 \(既定\) は、常にすべてのデータが返されます。  制約をサポートするプロバイダーの例については、[UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) サンプルに関するトピックを参照してください。  
  
## スキーマ マップの設定  
 次のようなスキーマ マップを UpdatePV の Session.h に設定します。  
  
```  
BEGIN_SCHEMA_MAP(CUpdateSession)  
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)  
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)  
END_SCHEMA_MAP()  
```  
  
 **IDBSchemaRowset** をサポートするには、`DBSCHEMA_TABLES`、**DBSCHEMA\_COLUMNS**、および **DBSCHEMA\_PROVIDER\_TYPES** をサポートする必要があります。  スキーマ行セットは任意に追加できます。  
  
 スキーマ行セット クラスは `Execute` メソッドで宣言します。UpdatePV の `CUpdateSessionTRSchemaRowset` の例を示します。  
  
```  
class CUpdateSessionTRSchemaRowset :   
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,   
                              CTABLESRow, CUpdateSession >  
...  
// Execute looks like this; what pointers does the consumer use?  
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,   
                    ULONG cRestrictions, const VARIANT* rgRestrictions)  
```  
  
 `CUpdateSession` は `IDBSchemaRowsetImpl` を継承するため、すべての制約処理メソッドを持ちます。  `CSchemaRowsetImpl` を使用して、上記のスキーマ マップの一覧にある 3 つの子クラス \(`CUpdateSessionTRSchemaRowset`、`CUpdateSessionColSchemaRowset`、および `CUpdateSessionPTSchemaRowset`\) を宣言します。  これらの子クラスには、それぞれの制約 \(検索条件\) のセットを処理する `Execute` メソッドがあります。  各 `Execute` メソッドは、`cRestrictions` パラメーターと `rgRestrictions` パラメーターの値を比較します。  これらのパラメーターの説明については、「[IDBSchemaRowsetImpl::SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md)」を参照してください。  
  
 特定のスキーマ行セットに対応している制限の種類については、[!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)] の『OLE DB Programmer's Reference』で、「[IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx)」にあるスキーマ行セット GUID の表を参照してください。  
  
 たとえば、`DBSCHEMA_TABLES` で **TABLE\_NAME** 制約をサポートした場合は、以下の操作を行います。  
  
 最初に、`DBSCHEMA_TABLES` を検索し、次の 4 つの制約を順番にサポートしていることを確認します。  
  
|スキーマ行セット制約|制約値|  
|----------------|---------|  
|**TABLE\_CATALOG**|0x1 \(バイナリ 1\)|  
|**TABLE\_SCHEMA**|0x2 \(バイナリ 10\)|  
|**TABLE\_NAME**|0x4 \(バイナリ 100\)|  
|**TABLE\_TYPE**|0x8 \(バイナリ 1000\)|  
  
 各制約用に 1 ビットの値が用意されています。  サポートするのは **TABLE\_NAME** だけなので、`rgRestrictions` 要素に 0x4 を返します。  **TABLE\_CATALOG** と **TABLE\_NAME** をサポートした場合は、0x5 \(バイナリ 101\) を返します。  
  
 既定では、実装はすべての要求に 0 \(制約をサポートしない\) を返します。  UpdatePV は、制約をサポートしないプロバイダーの例です。  
  
### 例  
 このコードは、[UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) サンプルから引用しました。  UpdatePv は、3 つの必須スキーマ行セット \(`DBSCHEMA_TABLES`、**DBSCHEMA\_COLUMNS**、および **DBSCHEMA\_PROVIDER\_TYPES**\) をサポートします。  このトピックでは、プロバイダーでスキーマ サポートを実装する方法の例として、**DBSCHEMA\_TABLE** 行セットの実装を説明します。  
  
> [!NOTE]
>  サンプル コードは、ここに記載されているコードと異なる場合がありますが、その場合はサンプル コードの方が最新バージョンであると考えてください。  
  
 スキーマ サポートを追加する最初の手順として、サポートする制約を決定します。  スキーマ行セットで使用できる制約を判断するために、OLE DB 仕様で **IDBSchemaRowset** の定義を参照します。  主要な定義に続いて、スキーマ行セット名、制約数、および制限列が記載されたテーブルを参照します。  サポートするスキーマ行セットを選択し、制約数と制限列をメモしておきます。  たとえば、`DBSCHEMA_TABLES` は 4 つの制約 \(**TABLE\_CATALOG**、**TABLE\_SCHEMA**、**TABLE\_NAME**、および **TABLE\_TYPE**\) をサポートします。  
  
```  
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,   
   ULONG* rgRestrictions)  
{  
    for (ULONG l=0; l<cRestrictions; l++)  
    {  
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
            rgRestrictions[l] = 0x0C;  
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))  
                 rgRestrictions[l] = 0x04;  
             else if (InlineIsEqualGUID(rguidSchema[l],  
                                        DBSCHEMA_PROVIDER_TYPES))  
                      rgRestrictions[l] = 0x00;  
   }  
}  
```  
  
 各ビットは、それぞれ制限列を表します。  制約をサポートする場合 \(つまり、制約条件によりクエリを実行できるようにする場合\) は、そのビットを 1 にセットします。  制約をサポートしない場合は、そのビットを 0 にセットします。  上のコード行では、UpdatePV は `DBSCHEMA_TABLES` 行セットで **TABLE\_NAME** 制約と **TABLE\_TYPE** 制約をサポートします。  これらは、3 番目 \(ビット マスク 100\) と 4 番目 \(ビット マスク 1000\) の制約です。  したがって、UpdatePv のビットマスクは 1100 \(0x0C\) になります。  
  
```  
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))  
    rgRestrictions[l] = 0x0C;  
```  
  
 次の `Execute` 関数は、通常の行セットの場合と同様です。  3 つの引数 \(`pcRowsAffected`、`cRestrictions`、および `rgRestrictions`\) があります。  `pcRowsAffected` 変数は、プロバイダーがスキーマ行セットの行数を返すための出力パラメーターです。  `cRestrictions` パラメーターは、コンシューマーがプロバイダーに渡した制約数を保持する入力パラメーターです。  `rgRestrictions` パラメーターは、制約値を保持する **VARIANT** 値の配列です。  
  
```  
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,   
                const VARIANT* rgRestrictions)  
```  
  
 `cRestrictions` 変数は、プロバイダーによってサポートされているかどうかに関係なく、スキーマ行セットの制約の合計数に基づいています。  UpdatePv は、2 つの制約 \(3 番目と 4 番目\) をサポートするため、このコードでは、3 以上の `cRestrictions` 値だけを検索します。  
  
 **TABLE\_NAME** 制約の値は、`rgRestrictions[2]` に格納されます。0 から始まる配列の 3 番目の制約は 2 になります。  制約を実際にサポートするには、その制約が `VT_EMPTY` でないことを確認する必要があります。  **VT\_NULL** は `VT_EMPTY` とは異なります。  **VT\_NULL** は有効な制約値を表します。  
  
 テーブル名の UpdatePv 定義は、テキスト ファイルの絶対パス名です。  制約値を抽出し、ファイルのオープンを試みることにより、そのファイルが実際に存在することを確認します。  ファイルが存在しない場合は、`S_OK` を返します。  これは少し奇妙に思えますが、コードがコンシューマーに対して実際に示しているのは、指定された名前でサポートされているテーブルがなかったということです。  この `S_OK` は、コードが正常に実行されたことを意味します。  
  
```  
USES_CONVERSION;  
enum {  
            sizeOfszFile = 255  
};  
CTABLESRow  trData;  
FILE        *pFile = NULL;  
TCHAR       szFile[ sizeOfszFile ];  
errcode     err = 0;  
  
// Handle any restrictions sent to us. This only handles  
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th   
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets   
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04   
// for a total of (0x0C)  
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)  
{  
    CComBSTR bstrName = rgRestrictions[2].bstrVal;  
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))  
    {  
        // Check to see if the file exists  
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));  
        if (szFile[0] == _T('\0') ||   
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))  
        {  
            return S_OK;// Their restriction was invalid return no data  
        }  
        else  
        {  
            fclose(pFile);  
        }  
    }  
}  
```  
  
 4 番目の制約 \(**TABLE\_TYPE**\) のサポートは、3 番目の制約のサポートと同様です。  値が `VT_EMPTY` でないことを確認します。  この制約は、テーブルタイプ \(**TABLE**\) だけを返します。  `DBSCHEMA_TABLES` に対して有効な値を判断するには、『OLE DB Programmer's Reference』の「Appendix B: Schema Rowsets」で、「**TABLES** rowset」のセクションを参照してください。  
  
```  
// TABLE_TYPE restriction:  
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)  
{  
    CComBSTR bstrType = rgRestrictions[3].bstrVal;  
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))  
    {  
        // This is kind of a blind restriction.  
        // This only actually supports  
        // TABLES so if you get anything else,   
        // just return an empty rowset.  
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)  
            return S_OK;  
    }  
}  
```  
  
 ここでは、行セットの行エントリが実際に作成されます。  変数 `trData` は、OLE DB プロバイダー テンプレートに定義されている構造体 **CTABLESRow** に対応します。  **CTABLESRow** は、OLE DB 仕様の付録 B にある **TABLES** 行セット定義に対応します。  一度にサポートできるのは 1 つのテーブルだけなので、追加できる行も 1 行だけです。  
  
```  
// Bring over the data:  
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);  
wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);  
wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());  
```  
  
 UpdatePV は、**TABLE\_NAME**、**TABLE\_TYPE**、および **DESCRIPTION** の 3 列だけを設定します。  情報を取得する列をメモしておく必要があります。`GetDBStatus` を実装する場合にこの情報が必要になるためです。  
  
```  
    _ATLTRY  
    {  
        m_rgRowData.Add(trData);  
    }  
    _ATLCATCHALL()  
    {  
        return E_OUTOFMEMORY;  
    }  
    //if (!m_rgRowData.Add(trData))  
    //    return E_OUTOFMEMORY;  
    *pcRowsAffected = 1;  
    return S_OK;  
}  
```  
  
 `GetDBStatus` 関数は、スキーマ行セットを適切に動作させるために重要です。  **TABLES** 行セットのすべての列のデータを返すわけではないため、データを返す \(または返さない\) 列を指定する必要があります。  
  
```  
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pColInfo != NULL);  
  
    switch(pColInfo->iOrdinal)  
    {  
    case 3:     // TABLE_NAME  
    case 4:     // TABLE_TYPE  
    case 6:     // DESCRIPTION  
        return DBSTATUS_S_OK;  
        break;  
    default:  
        return DBSTATUS_S_ISNULL;  
    break;  
    }  
}  
```  
  
 `Execute` 関数では、**TABLES** 行セットの **TABLE\_NAME**、**TABLE\_TYPE**、および **DESCRIPTION** の各フィールドについてのデータを返します。OLE DB 仕様の付録 B を参照して、フィールドを上から順に数えると、これらが 3、4、および 6 番目にあることがわかります。  これらの各列について、**DBSTATUS\_S\_OK** を返します。  その他すべての列については、**DBSTATUS\_S\_ISNULL** を返します。  コンシューマーは、返された値が **NULL** かどうかを認識しない場合があるため、このステータスを返すことは重要です。  ここでも、**NULL** 値は空値のと同等ではないことに注意してください。  
  
 OLE DB スキーマ行セット インターフェイスの詳細については、『OLE DB Programmer's Reference』の [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) インターフェイスに関するトピックを参照してください。  
  
 コンシューマーが **IDBSchemaRowset** メソッドを使用する方法については、「[スキーマ行セットを使用したメタデータの取得](../../data/oledb/obtaining-metadata-with-schema-rowsets.md)」を参照してください。  
  
 スキーマ行セットをサポートするプロバイダーの例については、[UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) サンプルを参照してください。  
  
## 参照  
 [高度なプロバイダー手法](../Topic/Advanced%20Provider%20Techniques.md)