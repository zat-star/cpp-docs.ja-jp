---
title: "データ ソース: プログラムにおける ODBC データ ソースのテーブルの作成 | Microsoft Docs"
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
  - "ODBC データ ソース, 作成 (テーブルを)"
  - "プログラムによる作成 (ODBC テーブルの) [C++]"
  - "テーブル [C++]"
  - "テーブル [C++], 作成 (プログラムによる)"
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データ ソース: プログラムにおける ODBC データ ソースのテーブルの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、データ ソースのテーブルを作成する方法について説明します。テーブルを作成するには、`CDatabase` クラスの `ExecuteSQL` メンバー関数に、**CREATE TABLE** SQL ステートメントを含む文字列を渡します。  
  
 MFC の ODBC データ ソースについては、「[データ ソース \(ODBC\)](../../data/odbc/data-source-odbc.md)」を参照してください。  データ ソースの作成方法については、「[データ ソース : プログラムにおける ODBC データ ソースの設定](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md)」を参照してください。  
  
 データ ソースが確立したら、`ExecuteSQL` メンバー関数と **CREATE TABLE** SQL ステートメントを使用して簡単にテーブルを作成できます。  たとえば、`myDB` という `CDatabase` オブジェクトがある場合は、次の MFC コードでテーブルを作成できます。  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 このコード例では、`myDB` で保持される Microsoft Access データ ソース接続に "OFFICES" というテーブルを作成します。このテーブルには、"OfficeID" と "OfficeName" という 2 つのフィールドがあります。  
  
> [!NOTE]
>  **CREATE TABLE** SQL ステートメントで指定するフィールドの種類は、使用する ODBC ドライバーによって異なります。  Visual C\+\+ 1.5 に添付されている Microsoft Query プログラムを使うと、データ ソースに使えるフィールドの種類を調べることができます。  Microsoft Query で、\[ファイル\] メニューの \[テーブルの定義\] をクリックします。次に、データ ソースのテーブルを選択すると、使用できるフィールドの種類が **\[種類\]** ボックスに表示されます。  インデックスを作成するための SQL 構文もあります。  
  
## 参照  
 [データ ソース \(ODBC\)](../../data/odbc/data-source-odbc.md)