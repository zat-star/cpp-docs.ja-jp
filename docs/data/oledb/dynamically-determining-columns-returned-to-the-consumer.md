---
title: "コンシューマーに返される列の動的な判断 | Microsoft Docs"
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
  - "ブックマーク [C++], 動的に決定される列"
  - "動的に決定される列 [C++]"
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コンシューマーに返される列の動的な判断
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

PROVIDER\_COLUMN\_ENTRY マクロは、通常は **IColumnsInfo::GetColumnsInfo** 呼び出しを処理します。  ただし、コンシューマーはブックマークを使用する場合があるため、プロバイダーは、コンシューマーがブックマークを要求するかどうかに応じて、返された列を変更できるようにする必要があります。  
  
 **IColumnsInfo::GetColumnsInfo** 呼び出しを処理するには、`GetColumnInfo` 関数を定義する PROVIDER\_COLUMN\_MAP を MyProviderRS.h の `CAgentMan` ユーザー レコードから削除し、独自の `GetColumnInfo` 関数の定義で置き換えます。  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
 次に、以下のコードのように、MyProviderRS.cpp に `GetColumnInfo` 関数を実装します。  
  
 `GetColumnInfo` は、OLE DB プロパティ **DBPROP\_BOOKMARKS** が設定されているかどうかを最初に調べます。  プロパティを取得するために、`GetColumnInfo` は行セット オブジェクトへのポインター \(`pRowset`\) を使用します。  `pThis` ポインターは、行セットを作成したクラスを表します。これは、プロパティ マップが格納されるクラスです。  `GetColumnInfo` は、`pThis` ポインターを `RMyProviderRowset` ポインター型にキャストします。  
  
 `GetColumnInfo` は、**DBPROP\_BOOKMARKS** プロパティを調べるために `IRowsetInfo` インターフェイスを使用します。このインターフェイスは、`pRowset` インターフェイスで `QueryInterface` を呼び出すことにより取得できます。  代わりに ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) メソッドを使用することもできます。  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
   // ordinal entry in the column map with the bookmark information.  
   CAgentRowset* pRowset = (CAgentRowset*) pThis;  
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
   CDBPropIDSet set(DBPROPSET_ROWSET);  
   set.AddPropertyID(DBPROP_BOOKMARKS);  
   DBPROPSET* pPropSet = NULL;  
   ULONG ulPropSet = 0;  
   HRESULT hr;  
  
   if (spRowsetProps)  
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
   if (pPropSet)  
   {  
      CComVariant var = pPropSet->rgProperties[0].vValue;  
      CoTaskMemFree(pPropSet->rgProperties);  
      CoTaskMemFree(pPropSet);  
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
      {  
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),   
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText)  
   ulCols++;  
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand2)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
```  
  
 この例では、静的配列に列情報を格納します。  コンシューマーがブックマーク列を不要とする場合は、配列のエントリの 1 つは使用されません。  情報を処理するには、ADD\_COLUMN\_ENTRY および ADD\_COLUMN\_ENTRY\_EX という 2 つの配列マクロを作成します。  ADD\_COLUMN\_ENTRY\_EX には、ADD\_COLUMN\_ENTRY に比べて、ブックマーク列を指定する場合に必要な `flags` という追加のパラメーターがあります。  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision,   
scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type,   
precision, scale, guid, dataClass, member, flags) \  
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
  
 `GetColumnInfo` 関数では、ブックマーク マクロは次のように使用されます。  
  
```  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 これで、拡張されたプロバイダーをコンパイルして実行できます。  プロバイダーをテストするには、「[単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」の説明のとおりにテスト コンシューマーを変更します。  テスト コンシューマーをプロバイダーと共に実行します。  \[テスト コンシューマー\] ダイアログ ボックスの \[実行\] ボタンをクリックしたときに、テスト コンシューマーが適切な文字列をプロバイダーから取得することを確認します。  
  
## 参照  
 [単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)