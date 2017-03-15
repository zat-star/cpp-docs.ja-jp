---
title: "更新可能なプロバイダーの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "通知, サポート (プロバイダーでの)"
  - "OLE DB プロバイダー, 作成"
  - "OLE DB プロバイダー, 更新可能な"
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 更新可能なプロバイダーの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ 6.0 は、読み取り専用プロバイダーだけをサポートしていました。  Visual C\+\+ .NET は、更新可能なプロバイダー、つまりデータ ストアを更新 \(書き込み\) できるプロバイダーをサポートします。  ここでは、OLE DB テンプレートを使用して更新可能なプロバイダーを作成する方法について説明します。  
  
 このトピックでは、既に動作しているプロバイダーがあることを前提とします。  更新可能なプロバイダーは、2 つのステップで作成します。  最初に、プロバイダーがデータ ストアに変更を加える方法を決定します。具体的には、変更を即時に行うかどうか、または更新コマンドが実行されるまで遅延するかどうかを決定します。  「[プロバイダーの更新可能化](#vchowmakingprovidersupdatable)」では、プロバイダー コードで行う必要のある変更と設定について説明します。  
  
 次に、コンシューマーの要求をサポートするためのすべての機能がプロバイダーに含まれていることを確認する必要があります。  コンシューマーがデータ ストアを更新する必要がある場合、プロバイダーには、データをデータ ストアに保持するコードを含める必要があります。  たとえば、C ランタイム ライブラリまたは MFC を使用して、データ ソースに対してこのような更新操作を実行できます。  「[データ ソースへの書き込み](#vchowwritingtothedatasource)」では、データ ソースへの書き込み方法、**NULL** と既定値の処理方法、および列フラグの設定方法について説明します。  
  
> [!NOTE]
>  UpdatePV は、更新可能プロバイダーの例です。  UpdatePV は、更新機能がサポートされている以外は MyProv と同じです。  
  
##  <a name="vchowmakingprovidersupdatable"></a> プロバイダーの更新可能化  
 プロバイダーを更新可能にするには、プロバイダーがデータ ストアに対して実行する操作と、それらの操作を実行する方法の理解が重要です。  特に、データ ストアに対する更新を即時に実行するか、更新コマンドが実行されるまで遅延させる \(バッチ処理化する\) かが大きな検討事項となります。  
  
 最初に、行セット クラスの `IRowsetChangeImpl` と `IRowsetUpdateImpl` のどちらを継承するかを決定します。  このどちらを実装するかによって、`SetData`、**InsertRows**、および `DeleteRows` の 3 つのメソッドの機能に影響があります。  
  
-   [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md) から継承する場合は、この 3 つのメソッドを呼び出すとデータ ストアが即時に変更されます。  
  
-   [IRowsetUpdateImpl](../Topic/IRowsetUpdateImpl%20Class.md) から継承する場合は、**Update**、`GetOriginalData`、または **Undo** を呼び出すまでデータ ストアへの変更が遅延されます。  更新に複数の変更が含まれる場合は、バッチ モードで実行されます。変更のバッチ化により、メモリのオーバーヘッドがかなり増加する可能性があります。  
  
 `IRowsetUpdateImpl` は `IRowsetChangeImpl` から派生します。  したがって、`IRowsetUpdateImpl` には変更機能に加えてバッチ機能が用意されています。  
  
#### プロバイダーの更新機能をサポートするには  
  
1.  行セット クラスで、`IRowsetChangeImpl` または `IRowsetUpdateImpl` を継承します。  これらのクラスには、データ ストアを変更するための適切なインターフェイスが用意されています。  
  
     **IRowsetChange の追加**  
  
     `IRowsetChangeImpl` を継承チェーンに追加するには、次の形式で記述します。  
  
    ```  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     行セット クラスの `BEGIN_COM_MAP` セクションに `COM_INTERFACE_ENTRY(IRowsetChange)` も追加します。  
  
     **IRowsetUpdate の追加**  
  
     `IRowsetUpdate` を継承チェーンに追加するには、次の形式で記述します。  
  
    ```  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  継承チェーンから `IRowsetChangeImpl` 行を削除する必要があります。  これは、前に説明したディレクティブへの変更と唯一異なる点ですが、`IRowsetChangeImpl` のコードも同時に削除する必要があります。  
  
2.  COM マップ \(**BEGIN\_COM\_MAP ...END\_COM\_MAP**\) に次の要素を追加します。  
  
    |実装する要素|COM マップに追加する要素|  
    |------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  コマンドで、プロパティ セット マップ \(**BEGIN\_PROPSET\_MAP ...END\_PROPSET\_MAP**\) に次の要素を追加します。  
  
    |実装する要素|プロパティ セット マップに追加する要素|  
    |------------|--------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  プロパティ セット マップには、以下の設定をこの記述どおりにすべて含める必要もあります。  
  
    ```  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     これらのマクロ呼び出しで使用される値は、そのプロパティ ID と値を Atldb.h で検索することにより参照できます。Atldb.h がオンライン ドキュメントの内容と異なる場合は、Atldb.h を優先してください。  
  
    > [!NOTE]
    >  **VARIANT\_FALSE** と `VARIANT_TRUE` の設定の多くは、OLE DB テンプレートで必要になります。OLE DB 仕様では、OLE DB テンプレートは読み取り\/書き込みともに可能とされていますが、実際は OLE DB テンプレートはどちらか 1 つの値しかサポートしません。  
  
     **IRowsetChangeImpl を実装する場合**  
  
     `IRowsetChangeImpl` を実装する場合は、プロバイダーで以下のプロパティを設定する必要があります。  これらのプロパティは、主に **ICommandProperties::SetProperties** を通じてインターフェイスを要求するために使用されます。  
  
    -   `DBPROP_IRowsetChange`: このプロパティを設定すると、**DBPROP\_IRowsetChange** が自動的に設定されます。  
  
    -   `DBPROP_UPDATABILITY`: `IRowsetChange` でサポートされるメソッドである `SetData`、`DeleteRows`、または `InsertRow` を指定するビットマスクです。  
  
    -   `DBPROP_CHANGEINSERTEDROWS`: コンシューマーは、新しく挿入された行に対して **IRowsetChange::DeleteRows** または `SetData` を呼び出すことができます。  
  
    -   `DBPROP_IMMOBILEROWS`: 行セットは、挿入または更新された行を並べ替えません。  
  
     **IRowsetUpdateImpl を実装する場合**  
  
     `IRowsetUpdateImpl` を実装する場合は、前に一覧を示した `IRowsetChangeImpl` のすべてのプロパティの設定に加えて、以下のプロパティをプロバイダーに設定する必要があります。  
  
    -   `DBPROP_IRowsetUpdate`.  
  
    -   `DBPROP_OWNINSERT`: READ\_ONLY および VARIANT\_TRUE にする必要があります。  
  
    -   `DBPROP_OWNUPDATEDELETE`: READ\_ONLY および VARIANT\_TRUE にする必要があります。  
  
    -   `DBPROP_OTHERINSERT`: READ\_ONLY および VARIANT\_TRUE にする必要があります。  
  
    -   `DBPROP_OTHERUPDATEDELETE`: READ\_ONLY および VARIANT\_TRUE にする必要があります。  
  
    -   `DBPROP_REMOVEDELETED`: READ\_ONLY および VARIANT\_TRUE にする必要があります。  
  
    -   `DBPROP_MAXPENDINGROWS`.  
  
        > [!NOTE]
        >  通知をサポートする場合、他のプロパティも同様に設定する必要があります。この一覧については、`IRowsetNotifyCP` に関するトピックを参照してください。  
  
     プロパティの設定方法の例については、「[UpdatePV サンプル : 更新可能な OLE DB プロバイダーの実装](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f)」の **CUpdateCommand** \(Rowset.h 内\) のプロパティ セット マップを参照してください。  
  
##  <a name="vchowwritingtothedatasource"></a> データ ソースへの書き込み  
 データ ソースからの読み取りには、**Execute** 関数を呼び出します。  データ ソースへの書き込みには、`FlushData` 関数を呼び出します。一般的に、フラッシュとは、テーブルまたはインデックスに対する変更をディスクに保存することを意味します。  
  
```  
FlushData(HROW, HACCESSOR);  
```  
  
 行ハンドル \(*HROW*\) 引数とアクセサー ハンドル \(*HACCESSOR*\) 引数を使用して、書き込む範囲を指定できます。  通常は、一度に 1 つのデータ フィールドを書き込みます。  
  
 `FlushData` メソッドは、最初に保存された形式でデータを書き込みます。  この関数をオーバーライドしなくても、プロバイダーは正しく機能しますが、変更はデータ ストアにフラッシュされません。  
  
### フラッシュする状況  
 プロバイダー テンプレートは、データをデータ ストアに書き込む必要があるかどうかにかかわらず、`FlushData` を呼び出します。これは通常、以下の関数の呼び出しの結果として発生します \(呼び出されない場合もあります\)。  
  
-   **IRowsetChange::DeleteRows**  
  
-   **IRowsetChange::SetData**  
  
-   **IRowsetChange::InsertRows** \(行に挿入する新規データがある場合\)  
  
-   **IRowsetUpdate::Update**  
  
### 処理の詳細  
 コンシューマーが、フラッシュが発生する呼び出し \(**Update** など\) を行うと、この呼び出しはプロバイダーに渡され、プロバイダーでは常に次の処理が行われます。  
  
-   バインドされているステータス値がある場合は `SetDBStatus` を呼び出します。『OLE DB Programmer's Reference』の「Chapter 6: Getting and Setting Data」を参照してください。  
  
-   列フラグを調べます。  
  
-   `IsUpdateAllowed` を呼び出します。  
  
 この 3 つの手順で、セキュリティが確保できます。  次に、プロバイダーは `FlushData` を呼び出します。  
  
### FlushData の実装方法  
 `FlushData` を実装するには、以下の事項を検討する必要があります。  
  
-   データ ストアが変更を処理できるかの確認  
  
-   **NULL** 値の処理  
  
-   既定値の処理  
  
 独自の `FlushData` メソッドを実装するには、以下を行う必要があります。  
  
-   行セット クラスに移動します。  
  
-   行セット クラスに次の宣言を挿入します。  
  
```  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    // Insert your implementation here and return an HRESULT.  
}  
```  
  
-   `FlushData` の実装を用意します。  
  
 `FlushData` の実装では、実際に更新された行と列だけを格納することをお勧めします。  *HROW* パラメーターと *HACCESSOR* パラメーターを使用して、最適化のために格納される現在の行と列を判断できます。  
  
 通常、最大の課題は独自のネイティブなデータ ストアの処理です。  可能な場合は次の操作を行ってください。  
  
-   データ ストアに書き込む方法はできるだけ単純にします。  
  
-   **NULL** 値を処理します。これは省略できますが、処理することをお勧めします。  
  
-   既定値を処理します。これは省略できますが、処理することをお勧めします。  
  
 最善の方法は、**NULL** と既定値に対して実際に特定の値をデータ ストアに持つことです。  これは、このデータを推定できた方が便利だからです。  データを推定できない場合は、**NULL** と既定値を許可しないことをお勧めします。  
  
 [UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) サンプルの `RUpdateRowset` クラスに `FlushData` を実装する方法の例を次に示します。サンプル コードの Rowset.h を参照してください。  
  
```  
///////////////////////////////////////////////////////////////////////////  
// class RUpdateRowset (in rowset.h)  
...  
HRESULT FlushData(HROW, HACCESSOR)  
{  
    ATLTRACE2(atlTraceDBProvider, 0, "RUpdateRowset::FlushData\n");  
  
    USES_CONVERSION;  
    enum {  
        sizeOfString = 256,  
        sizeOfFileName = MAX_PATH  
    };  
    FILE*    pFile = NULL;  
    TCHAR    szString[sizeOfString];  
    TCHAR    szFile[sizeOfFileName];  
    errcode  err = 0;  
  
    ObjectLock lock(this);  
  
    // From a filename, passed in as a command text,   
    // scan the file placing data in the data array.  
    if (m_strCommandText == (BSTR)NULL)  
    {  
        ATLTRACE( "RRowsetUpdate::FlushData -- "  
                  "No filename specified\n");  
        return E_FAIL;  
    }  
  
    // Open the file  
    _tcscpy_s(szFile, sizeOfFileName, OLE2T(m_strCommandText));  
    if ((szFile[0] == _T('\0')) ||   
        ((err = _tfopen_s(&pFile, &szFile[0], _T("w"))) != 0))  
    {  
        ATLTRACE("RUpdateRowset::FlushData -- Could not open file\n");  
        return DB_E_NOTABLE;  
    }  
  
    // Iterate through the row data and store it.  
    for (long l=0; l<m_rgRowData.GetSize(); l++)  
    {  
        CAgentMan am = m_rgRowData[l];  
  
        _putw((int)am.dwFixed, pFile);  
  
        if (_tcscmp(&am.szCommand[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szCommand2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szCommand2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
  
        if (_tcscmp(&am.szText2[0], _T("")) != 0)  
            _stprintf_s(&szString[0], _T("%s\n"), am.szText2);  
        else  
            _stprintf_s(&szString[0], _T("%s\n"), _T("NULL"));  
        _fputts(szString, pFile);  
    }  
  
    if (fflush(pFile) == EOF || fclose(pFile) == EOF)  
    {  
        ATLTRACE("RRowsetUpdate::FlushData -- "  
                 "Couldn't flush or close file\n");  
    }  
  
    return S_OK;  
}  
```  
  
### 変更の処理  
 プロバイダーで変更を処理するには、まず、データ ストア \(テキスト ファイルやビデオ ファイルなど\) に、そのデータ ストアを変更するための機能があることを確認する必要があります。  この機能がない場合は、プロバイダー プロジェクトとは別にそのコードを作成する必要があります。  
  
### NULL データの処理  
 エンド ユーザーが **NULL** データを送信する場合もあります。  データ ソース内のフィールドに **NULL** 値を書き込むと、問題が発生する可能性があります。  市区町村と郵便番号の値を受け入れる注文受け付けアプリケーションがあるとします。このアプリケーションは、一方または両方の値を受け付けることができますが、両方とも指定されていないと配達ができないため、少なくとも一方の値が必要です。  したがって、アプリケーションで重要なフィールドでは、特定の組み合わせでの **NULL** 値を制限する必要があります。  
  
 プロバイダーの開発時にきは、データの格納方法、データ ストアからのデータの読み取り方法、およびユーザーへの指定方法を考慮する必要があります。  具体的には、データ ソース内の行セット データのデータ ステータスの変更方法を検討する必要があります \(DataStatus \= **NULL** など\)。  コンシューマーが **NULL** 値を含むフィールドにアクセスしたときに返す値も決めておきます。  
  
 [UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) サンプルのコードを参照してください。このコードでは、プロバイダーによる **NULL** データの処理方法を示しています。  UpdatePV では、プロバイダーはデータ ストアに "NULL" という文字列を書き込むことによって **NULL** データを格納します。  プロバイダーは **NULL** データをデータ ストアから読み取ると、その文字列を認識し、バッファーを空にして、**NULL** 文字列を作成します。  また、`IRowsetImpl::GetDBStatus` をオーバーライドしています。ここでは、データ値が空の場合に、**DBSTATUS\_S\_ISNULL** を返しています。  
  
### NULL 許容列のマーク  
 スキーマ行セットも実装する場合 \(`IDBSchemaRowsetImpl` を参照\) は、列が **NULL** 許容であることを **DBSCHEMA\_COLUMNS** 行セットに指定する必要があります。この行セットは、通常プロバイダーでは **C***xxx***SchemaColSchemaRowset** で表されます。  
  
 作成するバージョンの `GetColumnInfo` で、**NULL** 許容であるすべての列に **DBCOLUMNFLAGS\_ISNULLABLE** 値が含まれるように指定する必要もあります。  
  
 OLE DB テンプレートの実装では、列で null 許容であることをマークしておかないと、プロバイダーはその列に値が含まれる必要があると想定し、コンシューマーがその列に null 値を送信することを許可しません。  
  
 UpdatePV の **CUpdateCommand** \(UpProvRS.cpp を参照\) で **CommonGetColInfo** 関数を実装する方法の例を次に示します。  NULL 許容列について **DBCOLUMNFLAGS\_ISNULLABLE** がどのように指定されているか注意してください。  
  
```  
/////////////////////////////////////////////////////////////////////////////  
// CUpdateCommand (in UpProvRS.cpp)  
  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols, bool bBookmark)  
{  
    static ATLCOLUMNINFO _rgColumns[6];  
    ULONG ulCols = 0;  
  
    if (bBookmark)  
    {  
        ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,  
                            sizeof(DWORD), DBTYPE_BYTES,  
                            0, 0, GUID_NULL, CAgentMan, dwBookmark,  
                            DBCOLUMNFLAGS_ISBOOKMARK)  
        ulCols++;  
    }  
  
    // Next set the other columns up.  
    // Add a fixed length entry for OLE DB conformance testing purposes  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Fixed"), 1, 4, DBTYPE_UI4,  
                        10, 255, GUID_NULL, CAgentMan, dwFixed,   
                        DBCOLUMNFLAGS_WRITE |   
                        DBCOLUMNFLAGS_ISFIXEDLENGTH)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command"), 2, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand,  
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text"), 3, 16, DBTYPE_STR,   
                        255, 255, GUID_NULL, CAgentMan, szText,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Command2"), 4, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szCommand2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
    ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Text2"), 5, 16, DBTYPE_STR,  
                        255, 255, GUID_NULL, CAgentMan, szText2,   
                        DBCOLUMNFLAGS_WRITE | DBCOLUMNFLAGS_ISNULLABLE)  
    ulCols++;  
  
    if (pcCols != NULL)  
    {  
        *pcCols = ulCols;  
    }  
  
    return _rgColumns;  
}  
```  
  
### 既定値  
 **NULL** データと同様に、既定値の変更を行う必要があります。  
  
 既定では、`FlushData` と **Execute** は `S_OK` を返します。  したがって、この関数をオーバーライドしない場合は、`S_OK` が返されるため変更は成功したように見えますが、変更された値はデータ ストアに転送されません。  
  
 [UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) サンプル \(Rowset.h\) 内では、`SetDBStatus` メソッドは既定値を次のように処理します。  
  
```  
virtual HRESULT SetDBStatus(DBSTATUS* pdbStatus, CSimpleRow* pRow,  
                            ATLCOLUMNINFO* pColInfo)  
{  
    ATLASSERT(pRow != NULL && pColInfo != NULL && pdbStatus != NULL);  
  
    void* pData = NULL;  
    char* pDefaultData = NULL;  
    DWORD* pFixedData = NULL;  
  
    switch (*pdbStatus)  
    {  
        case DBSTATUS_S_DEFAULT:  
            pData = (void*)&m_rgRowData[pRow->m_iRowset];  
            if (pColInfo->wType == DBTYPE_STR)  
            {  
                pDefaultData = (char*)pData + pColInfo->cbOffset;  
                strcpy_s(pDefaultData, "Default");  
            }  
            else  
            {  
                pFixedData = (DWORD*)((BYTE*)pData +   
                                          pColInfo->cbOffset);  
                *pFixedData = 0;  
                return S_OK;  
            }  
            break;  
        case DBSTATUS_S_ISNULL:  
        default:  
            break;  
    }  
    return S_OK;  
}  
```  
  
### 列フラグ  
 列の既定値をサポートする場合は、**\<***プロバイダー クラス*の**\>SchemaRowset** クラスのメタデータを使用して設定する必要があります。  *m\_bColumnHasDefault* に `VARIANT_TRUE` を設定します。  
  
 また、**DBCOLUMNFLAGS** 列挙型を使用して指定される列フラグも設定する必要があります。  列フラグは、列の特性を表します。  
  
 たとえば、[UpdatePV](http://msdn.microsoft.com/ja-jp/c8bed873-223c-4a7d-af55-f90138c6f38f) \(Session.h 内\) の `CUpdateSessionColSchemaRowset` クラスでは、最初の列は次のように設定されます。  
  
```  
// Set up column 1  
trData[0].m_ulOrdinalPosition = 1;  
trData[0].m_bIsNullable = VARIANT_FALSE;  
trData[0].m_bColumnHasDefault = VARIANT_TRUE;  
trData[0].m_nDataType = DBTYPE_UI4;  
trData[0].m_nNumericPrecision = 10;  
trData[0].m_ulColumnFlags = DBCOLUMNFLAGS_WRITE |  
                            DBCOLUMNFLAGS_ISFIXEDLENGTH;  
lstrcpyW(trData[0].m_szColumnDefault, OLESTR("0"));  
m_rgRowData.Add(trData[0]);  
```  
  
 このコードは、列が既定値 0 をサポートすること、書き込みができること、列内のすべてのデータの長さが同じであることを示します。  列のデータを可変長にする場合は、このフラグを設定しません。  
  
## 参照  
 [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)