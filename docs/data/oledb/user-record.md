---
title: "ユーザー レコード | Microsoft Docs"
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
  - "OLE DB プロバイダー, ユーザー レコード"
  - "レコード, ユーザー"
  - "行セット, ユーザー レコード"
  - "ユーザー レコード"
  - "ユーザー レコード, 記述済み"
ms.assetid: 9c0d2864-2738-4f62-a750-1016d9c3523f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ユーザー レコード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザー レコードには、行セットの列データを表すコードとデータ構造体が用意されています。  ユーザー レコードは、コンパイル時または実行時に作成できます。  ATL OLE DB プロバイダー ウィザードを使用してプロバイダーを作成すると、次のような既定のユーザー レコードが作成されます。プロバイダー名 \(短縮名\) に "MyProvider" を指定したとします。  
  
```  
class CWindowsFile:  
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
  
 OLE DB プロバイダー テンプレートは、クライアントとのやり取りに関する OLE DB 固有のすべての処理を行います。  プロバイダーは、応答に必要な列データを取得するために `GetColumnInfo` 関数を呼び出します。この関数は、ユーザー レコードに記述する必要があります。  たとえば、次に示すように .h ファイルで宣言することにより、ユーザー レコードで `GetColumnInfo` を明示的にオーバーライドできます。  
  
```  
template <class T>  
static ATLCOLUMNINFO* GetColumnInfo(T* pThis, ULONG* pcCols)   
```  
  
 このようにすると、次の記述と同じ結果が得られます。  
  
```  
static ATLCOLUMNINFO* GetColumnInfo(CommandClass* pThis, ULONG* pcCols)  
static ATLCOLUMNINFO* GetColumnInfo(RowsetClass* pThis, ULONG* pcCols)  
```  
  
 ユーザー レコードの .cpp ファイルで、`GetColumnInfo` も実装する必要があります。  
  
 PROVIDER\_COLUMN\_MAP マクロを使用すると、`GetColumnInfo` 関数を簡単に作成できます。  
  
-   BEGIN\_PROVIDER\_COLUMN\_MAP は、関数プロトタイプと **ATLCOLUMNINFO** 構造体の静的配列を定義します。  
  
-   PROVIDER\_COLUMN\_ENTRY マクロは、1 つの **ATLCOLUMNINFO** を定義して初期化します。  
  
-   END\_PROVIDER\_COLUMN\_MAP は、配列と関数を終了します。  また、配列要素カウントをパラメーター `pcCols` に入れます。  
  
 ユーザー レコードが実行時に作成される場合、**GetColumnInfo** はパラメーター `pThis` を使用して、行セットまたはコマンド インスタンスへのポインターを受け取ります。  コマンドと行セットは必ず `IColumnsInfo` インターフェイスをサポートするため、列情報はこのポインターから取得できます。  
  
 **CommandClass** と **RowsetClass** は、ユーザー レコードを使用するコマンドと行セットです。  
  
 ユーザー レコードで `GetColumnInfo` をオーバーライドする方法の例については、「[コンシューマーに返される列の動的な判断](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)」を参照してください。  
  
## 参照  
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)