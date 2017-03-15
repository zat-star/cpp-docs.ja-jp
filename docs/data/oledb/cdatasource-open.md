---
title: "CDataSource::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::Open"
  - "ATL.CDataSource.Open"
  - "CDataSource::Open"
  - "CDataSource.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open メソッド"
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDataSource::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソースへの接続を **CLSID**、**ProgID**、または `CEnumerator` モニカーを使用して開くか、ロケーター ダイアログ ボックスでユーザーに確認します。  
  
## 構文  
  
```  
  
        HRESULT Open(  
   const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   HWND hWnd = GetActiveWindow( ),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET   
) throw( );  
HRESULT Open(   
   LPCWSTR szProgID,   
   DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(   
   LPCSTR szProgID,   
   LPCTSTR pName,   
   LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0   
) throw( );  
```  
  
#### パラメーター  
 `clsid`  
 \[入力\] データ プロバイダーの **CLSID**。  
  
 *pPropSet*  
 \[入力\] 設定するプロパティと値を含む [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の配列へのポインター。  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] に含まれる *OLE DB プログラマーズ リファレンス*の[プロパティ セットとプロパティ グループ](https://msdn.microsoft.com/en-us/library/ms713696.aspx)に関するページを参照してください。  
  
 *nPropertySets*  
 \[入力\] *pPropSet* 引数で渡される [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) 構造体の数。  
  
 *pName*  
 \[入力\] 接続先のデータベース名。  
  
 *pUserName*  
 \[入力\] ユーザーの名前。  
  
 *pPassword*  
 \[入力\] ユーザーのパスワード。  
  
 `nInitMode`  
 \[入力\] データベースの初期化モード。  有効な初期化モードの一覧については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] に含まれる *OLE DB プログラマーズ リファレンス*の[初期化プロパティ](https://msdn.microsoft.com/en-us/library/ms723127.aspx)に関するページを参照してください。  `nInitMode` がゼロの場合、接続を開くために使用されるプロパティ セットには初期化モードが含まれません。  
  
 `szProgID`  
 \[入力\] プログラム ID。  
  
 `enumerator`  
 \[入力\] 呼び出し元が **CLSID** を指定しない場合に接続を開くためのモニカーを取得する際に使用される [CEnumerator](../../data/oledb/cenumerator-class.md) オブジェクト。  
  
 `hWnd`  
 \[入力\] ダイアログ ボックスの親であるウィンドウへのハンドル。  `hWnd` パラメーターを使用する関数のオーバーロードを使用すると、サービス コンポーネントが自動的に呼び出されます。詳細については、「解説」を参照してください。  
  
 `dwPromptOptions`  
 \[入力\] 表示するロケーター ダイアログ ボックスのスタイルを指定します。  使用できる値については、Msdasc.h を参照してください。  
  
## 戻り値  
 標準の `HRESULT`。  
  
## 解説  
 `hWnd` パラメーターを使用するメソッド オーバーロードは、oledb32.dll 内のサービス コンポーネントを使ってデータ ソース オブジェクトを開きます。この DLL には、リソース共有や自動トランザクション登録などのサービス コンポーネント機能の実装が含まれています。  詳細については、[http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true) で OLE DB プログラマーズ リファレンスの OLE DB サービスに関する説明を参照してください。  
  
 `hWnd` パラメーターを使用しないメソッド オーバーロードは、oledb32.dll 内のサービス コンポーネントを使用せずに、データ ソース オブジェクトを開きます。  これらの関数オーバーロードで開いた [CDataSource](../Topic/CDataSource%20Class.md) オブジェクトは、サービス コンポーネントの機能を利用できません。  
  
## 使用例  
 次のコードは、OLE DB テンプレートを使用して Jet 4.0 データ ソースを開く方法を示します。  Jet データ ソースは、OLE DB データ ソースとして扱います。  ただし、**Open** の呼び出しでは、**DBPROP\_JETOLEDB\_DATABASEPASSWORD** を設定できるように、**DBPROPSET\_DBINIT** と **DBPROPSET\_JETOLEDB\_DBINIT** の 2 つのプロパティ セットが必要です。  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/CPP/cdatasource-open_1.cpp)]  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataSource クラス](../Topic/CDataSource%20Class.md)