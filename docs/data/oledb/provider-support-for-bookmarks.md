---
title: "プロバイダーのブックマーク サポート | Microsoft Docs"
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
  - "ブックマーク, OLE DB"
  - "IRowsetLocate クラス"
  - "IRowsetLocate クラス, プロバイダーのブックマーク サポート"
  - "OLE DB プロバイダー テンプレート, ブックマーク"
  - "OLE DB プロバイダー, ブックマーク サポート"
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# プロバイダーのブックマーク サポート
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの例では、`CMyProviderRowset` クラスに `IRowsetLocate` インターフェイスを追加します。  ほとんどの場合、既存の COM オブジェクトにインターフェイスを追加することから始めます。  その後、コンシューマー テンプレートからの呼び出しを追加して、インターフェイスをテストできます。  この例では、次の方法を示します。  
  
-   プロバイダーにインターフェイスを追加する方法  
  
-   コンシューマーに返す列を動的に決める方法  
  
-   ブックマーク サポートを追加する方法  
  
 `IRowsetLocate` インターフェイスは `IRowset` インターフェイスを継承します。  `IRowsetLocate` インターフェイスを追加するには、`CMyProviderRowset` を [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md) から派生させます。  
  
 `IRowsetLocate` インターフェイスの追加方法は、ほかのほとんどのインターフェイスの場合と少し異なります。  VTABLE を準備するために、OLE DB プロバイダー テンプレートには、派生インターフェイスを処理するテンプレート パラメーターがあります。  新しい継承のリストを次のコードに示します。  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> >  
```  
  
 4 番目、5 番目、および 6 番目のパラメーターがすべて追加されます。  この例では、4 番目と 5 番目のパラメーターには既定値を使用しますが、6 番目のパラメーターとして `IRowsetLocateImpl` を指定します。  `IRowsetLocateImpl` は、2 つのテンプレート パラメーターを取得する OLE DB テンプレート クラスです。これらのパラメーターは、`IRowsetLocate` インターフェイスを `CMyProviderRowset` クラスにフックします。  ほとんどのインターフェイスの追加では、この手順をスキップして次の手順に進みます。  この方法で処理する必要があるのは、`IRowsetLocate` インターフェイスと `IRowsetScroll` インターフェイスだけです。  
  
 次に、`CMyProviderRowset` に `IRowsetLocate` インターフェイスの `QueryInterface` を呼び出させる必要があります。  `COM_INTERFACE_ENTRY(IRowsetLocate)` 行をマップに追加します。  `CMyProviderRowset` のインターフェイス マップは、次のコードのようになります。  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate> > _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 マップを `CRowsetImpl` クラスにフックする必要もあります。  フックする COM\_INTERFACE\_ENTRY\_CHAIN マクロを `CRowsetImpl` マップに追加します。  また、継承情報から構成される `RowsetBaseClass` という typedef を作成します。  この typedef は任意であり、無視できます。  
  
 最後に、**IColumnsInfo::GetColumnsInfo** 呼び出しを処理します。  通常は PROVIDER\_COLUMN\_ENTRY マクロを使用してこれを行います。  ただし、コンシューマーはブックマークを使用する場合があります。  コンシューマーがブックマークを要求するかどうかに応じて、プロバイダーから返される列を変更できるようにする必要があります。  
  
 **IColumnsInfo::GetColumnsInfo** 呼び出しを処理するには、`CTextData` クラスの **PROVIDER\_COLUMN** マップを削除します。  PROVIDER\_COLUMN\_MAP マクロは `GetColumnInfo` 関数を定義します。  独自の `GetColumnInfo` 関数を定義する必要があります。  関数宣言は次のようになります。  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 その後、次のように `GetColumnInfo` 関数を MyProviderRS.cpp ファイルに実装します。  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
template <class TInterface>  
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   CComQIPtr<TInterface> spProps = pPropsUnk;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spProps)  
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   // Check the property flag for bookmarks, if it is set, set the   
// zero ordinal entry in the column map with the bookmark   
// information.  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,   
                     sizeof(DWORD), DBTYPE_BYTES,  
            0, 0, GUID_NULL, CAgentMan, dwBookmark,         
                        DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
  
   }  
  
   // Next set the other columns up.  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,   
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)  
   ulCols++;  
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,  
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
     ULONG* pcCols)  
{  
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),  
        pcCols);  
}  
  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)  
{  
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);  
}  
```  
  
 `GetColumnInfo` は、最初に、**DBPROP\_IRowsetLocate** というプロパティが設定されているかどうかを調べます。  OLE DB では、行セット オブジェクトとは独立して、省略可能なインターフェイスごとにプロパティが用意されています。  省略可能なインターフェイスを使用するコンシューマーは、そのインターフェイスのプロパティを true に設定します。  プロバイダーはこのプロパティを調べ、これに基づいて独自の処置をとることができるようになります。  
  
 実装では、コマンド オブジェクトへのポインターを使用してプロパティを取得します。  `pThis` ポインターは行セットまたはコマンド クラスを表します。  ここではテンプレートを使用するため、このポインターを `void` 型のポインターとして渡す必要があります。そうしないとコードがコンパイルされません。  
  
 次に、列情報を格納するための静的配列を指定します。  コンシューマーがブックマーク列を要求しない場合は、配列のエントリを 1 つ余分に使用することになります。  この配列を動的に割り当てることができますが、割り当てた配列が適切に破棄されるようにする必要があります。  ここでは ADD\_COLUMN\_ENTRY マクロと ADD\_COLUMN\_ENTRY\_EX マクロを定義および使用して、情報を配列に挿入します。  このマクロを以下のように MyProviderRS.H ファイルに追加できます。  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```  
  
 コンシューマー内のコードをテストするには、`OnRun` ハンドラーに多少の変更を加える必要があります。  この関数に加える最初の変更は、プロパティ セットにプロパティを追加するコードを追加することです。  このコードは **DBPROP\_IRowsetLocate** プロパティを true に設定します。これでブックマーク列を使用することをプロバイダーに通知できます。  `OnRun` ハンドラーのコードは次のようになります。  
  
```  
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider> > table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
          NULL) != S_OK)  
      return;  
  
   if (session.Open(source) != S_OK)  
      return;  
  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   propset.AddProperty(DBPROP_IRowsetLocate, true);  
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),   
          &propset) != S_OK)  
      return;  
  
   CBookmark<4> tempBookmark;  
   ULONG ulCount=0;  
   while (table.MoveNext() == S_OK)  
   {  
  
      DBCOMPARE compare;  
      if (ulCount == 2)  
         tempBookmark = table.bookmark;  
      HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,  
                 &compare);  
      if (FAILED(hr))  
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);  
      else  
         _ASSERTE(compare == DBCOMPARE_EQ);  
  
      m_ctlString1.AddString(table.szField1);  
      m_ctlString2.AddString(table.szField2);  
      ulCount++;  
   }  
  
   table.MoveToBookmark(tempBookmark);  
   m_ctlString1.AddString(table.szField1);  
   m_ctlString2.AddString(table.szField2);  
}  
```  
  
 while ループには、`IRowsetLocate` インターフェイスの `Compare` メソッドを呼び出すためのコードが含まれています。  まったく同じブックマークを比較することになるため、このコードは常に成功します。  同時に一方のブックマークをテンポラリ変数に格納します。これは、while ループの終了後にこのブックマークを使用して、コンシューマー テンプレートの `MoveToBookmark` 関数を呼び出すためです。  `MoveToBookmark` 関数は、`IRowsetLocate` の `GetRowsAt` メソッドを呼び出します。  
  
 コンシューマーのユーザー レコードも更新する必要があります。  ブックマークを処理するクラスと **COLUMN\_MAP** にそれぞれエントリを 1 つ追加します。  
  
```  
///////////////////////////////////////////////////////////////////////  
// TestProvDlg.cpp  
  
class CProvider  
{  
// Attributes  
public:  
   CBookmark<4>    bookmark;  // Add this line  
   char   szCommand[16];  
   char   szText[256];  
  
   // Binding Maps  
BEGIN_ACCESSOR_MAP(CProvider, 1)  
   BEGIN_ACCESSOR(0, true)   // auto accessor  
      BOOKMARK_ENTRY(bookmark)  // Add this line  
      COLUMN_ENTRY(1, szField1)  
      COLUMN_ENTRY(2, szField2)  
   END_ACCESSOR()  
END_ACCESSOR_MAP()  
};  
```  
  
 コードを更新すると、`IRowsetLocate` インターフェイスを使用してプロバイダーをビルドし、実行できるようになります。  
  
## 参照  
 [高度なプロバイダー手法](../Topic/Advanced%20Provider%20Techniques.md)