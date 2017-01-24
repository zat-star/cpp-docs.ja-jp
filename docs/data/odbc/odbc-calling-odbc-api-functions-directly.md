---
title: "ODBC: ODBC API 関数の直接呼び出し | Microsoft Docs"
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
  - "API [C++], 呼び出し"
  - "カタログ関数 (ODBC)"
  - "カタログ関数 (ODBC), 呼び出し"
  - "直接呼び出し (ODBC API)"
  - "ODBC [C++], API 関数"
  - "ODBC [C++], カタログ関数"
  - "ODBC API 関数 [C++]"
  - "ODBC API 関数 [C++], 呼び出し"
  - "ODBC クラス [C++], および ODBC API"
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC: ODBC API 関数の直接呼び出し
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース クラスを使うと、ODBC を使うより簡単なインターフェイスで[データ ソース](../../data/odbc/data-source-odbc.md)にアクセスできます。  ただし、データベース クラスは、すべての ODBC API をカプセル化するわけではありません。  データベース クラスがサポートしていない機能を使うには、ODBC API 関数を直接呼び出す必要があります。  たとえば、ODBC カタログ関数 \(**::SQLColumns**、**::SQLProcedures**、**::SQLTables** など\) は直接呼び出します。  
  
> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO \(Data Access Object\) クラス経由でもアクセスできます。  
  
 ODBC API 関数を直接呼び出すには、フレームワークを使わずに関数を呼び出すときと同じ手順で行います。  手順は次のとおりです。  
  
-   戻り値用の領域を確保します。  
  
-   関数のパラメーター書式に応じて、ODBC **HDBC** ハンドルか **HSTMT** ハンドルを渡します。  [AFXGetHENV](../Topic/AfxGetHENV.md) マクロを使って ODBC ハンドルを取得します。  
  
     メンバー変数 **CDatabase::m\_hdbc** および **CRecordset::m\_hstmt** を使えるため、領域の割り当てや初期化は必要はありません。  
  
-   呼び出しの準備または呼び出しの後始末のために、ODBC 関数を必要に応じて呼び出します。  
  
-   割り当てた領域を解放して、終了します。  
  
 各手順の詳細については、MSDN ドキュメントの [ODBC \(Open Database Connectivity\)](https://msdn.microsoft.com/en-us/library/ms710252.aspx) SDK を参照してください。  
  
 上記の手順に加え、関数の戻り値のチェックや、非同期呼び出しの終了を待たないようにするための手順なども必要です。  これらの追加手順については、`AFX_SQL_ASYNC` マクロや `AFX_SQL_SYNC` マクロを使うと簡単です。  詳細については、『MFC リファレンス』の「[マクロ、グローバル関数、およびグローバル変数](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)」を参照してください。  
  
## 参照  
 [ODBC の基礎](../../data/odbc/odbc-basics.md)