---
title: "CMyProviderWindowsFile | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cmyproviderwindowsfile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderWindowsFile クラス"
  - "OLE DB プロバイダー, ウィザードが生成したファイル"
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderWindowsFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ウィザードは、1 行のデータを格納するためにクラスを作成します。このクラスは `CMyProviderWindowsFile` と呼ばれます。  `CMyProviderWindowsFile` の次のコードはウィザードで生成されたコードであり、**WIN32\_FIND\_DATA** 構造体を使用してディレクトリ内のすべてのファイルを一覧表示します。  `CMyProviderWindowsFile` は、**WIN32\_FIND\_DATA** 構造体を継承します。  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CMyProviderWindowsFile:   
   public WIN32_FIND_DATA  
{  
public:  
BEGIN_PROVIDER_COLUMN_MAP(CMyProviderWindowsFile)  
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)  
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)  
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)  
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)  
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)  
END_PROVIDER_COLUMN_MAP()  
};  
```  
  
 `CMyProviderWindowsFile` は、プロバイダーの行セット内の列を記述するマップも含むため、[ユーザー レコード クラス](../../data/oledb/user-record.md)と呼ばれます。  プロバイダーの列マップには、PROVIDER\_COLUMN\_ENTRY マクロによって定義された、行セット内の各フィールドに対する 1 つのエントリが含まれます。  マクロは、列名、序数、および構造体エントリへのオフセットを指定します。  上のコードのプロバイダー列エントリには、**WIN32\_FIND\_DATA** 構造体へのオフセットが含まれます。  コンシューマーが **IRowset::GetData** を呼び出すと、データが 1 つの連続バッファーに転送されます。  つまり、ポインター演算の代わりに、マップを使用してデータ メンバーを指定できます。  
  
 `CMyProviderRowset` クラスには、`Execute` メソッドも含まれます。  `Execute` は、ネイティブなソースから実際にデータを読み込むメソッドです。  ウィザードで生成された `Execute` メソッドを次のコードに示します。  関数は、Win32 の **FindFirstFile** API と `FindNextFile` API を使用して、ディレクトリ内のファイルに関する情報を取得し、それらを `CMyProviderWindowsFile` クラスのインスタンスに配置します。  
  
```  
/////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)  
{  
   USES_CONVERSION;  
   BOOL bFound = FALSE;  
   HANDLE hFile;  
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :  
       OLE2T(m_strCommandText);  
   CMyProviderWindowsFile wf;  
   hFile = FindFirstFile(szDir, &wf);  
   if (hFile == INVALID_HANDLE_VALUE)  
      return DB_E_ERRORSINCOMMAND;  
   LONG cFiles = 1;  
   BOOL bMoreFiles = TRUE;  
   while (bMoreFiles)  
   {  
      if (!m_rgRowData.Add(wf))  
         return E_OUTOFMEMORY;  
      bMoreFiles = FindNextFile(hFile, &wf);  
      cFiles++;  
   }  
   FindClose(hFile);  
   if (pcRowsAffected != NULL)  
      *pcRowsAffected = cFiles;  
   return S_OK;  
}  
```  
  
 検索するディレクトリは、`m_strCommandText` で表されます。これには、コマンド オブジェクト内の `ICommandText` インターフェイスで表されるテキストが含まれます。  ディレクトリが指定されていない場合は、現在のディレクトリが使用されます。  
  
 メソッドは、各ファイルにつき 1 エントリを作成し \(1 行に対応\)、**m\_rgRowData** データ メンバーに配置します。  `CRowsetImpl` クラスは、**m\_rgRowData** データ メンバーを定義します。  この配列内のデータはテーブル全体を表し、テンプレート全体で使用されます。  
  
## 参照  
 [プロバイダー ウィザードで生成されたファイル](../../data/oledb/provider-wizard-generated-files.md)