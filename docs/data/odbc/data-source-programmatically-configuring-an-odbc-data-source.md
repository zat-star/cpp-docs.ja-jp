---
title: "データ ソース: プログラムにおける ODBC データ ソースの設定 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SQLConfigDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "構成 (ODBC データ ソースを)"
  - "ODBC 接続, 構成"
  - "ODBC データ ソース, 構成"
  - "SQLConfigDataSource メソッドの例"
ms.assetid: b8cabe9b-9e12-4d73-ae36-7cb12dee3213
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# データ ソース: プログラムにおける ODBC データ ソースの設定
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、ODBC \(Open Database Connectivity\) データ ソース名をプログラムで設定する方法について説明します。  この方法を使うと、柔軟なデータ アクセスが可能になり、ユーザーが ODBC データ ソース アドミニストレーターなどのプログラムを使って明示的にデータ ソースを指定する必要もありません。  
  
 通常、ユーザーは ODBC データ ソース アドミニストレーターを実行してデータ ソースを作成します。ただし、関連付けられたデータベース管理システム \(DBMS: Database Management System\) がこの操作をサポートすることが条件です。  
  
 ODBC データ ソース アドミニストレーターを使用して Microsoft Access ODBC データ ソースを作成する際には、既存の .mdb ファイルを使用するか、新しい .mdb ファイルを作成するかを選択できます。  MFC ODBC アプリケーションからプログラムを通じて .mdb ファイルを作成する方法はありません。  したがって、データを Microsoft Access データ ソース \(.mdb ファイル\) に格納する必要があるアプリケーションの場合は、空の .mdb ファイルを用意し、必要に応じて使用またはコピーできるようにします。  
  
 しかし、多くの DBMS では、プログラム上でデータ ソースを作成できます。  一部のデータ ソースは、データベースのフォルダー仕様を保持しています。  つまり、フォルダーがデータ ソースであり、データ ソース内の各テーブルは別個のファイルに格納されます。たとえば、dBASE の場合、各テーブルは .dbf ファイルです。  Microsoft Access や SQL サーバーなどのほかの ODBC データベースのドライバーは、データ ソースを確立する前に特定の基準を満たすことが必要です。  たとえば、SQL Server ODBC ドライバーを使用する場合は、SQL Server コンピューターを確立しておく必要があります。  
  
##  <a name="_core_sqlconfigdatasource_example"></a> SQLConfigDataSource の例  
 次の例では、**::SQLConfigDataSource** ODBC API 関数を使用して、New Excel Data Source という新しい Excel データ ソースを作成します。  
  
```  
SQLConfigDataSource(NULL,ODBC_ADD_DSN, "Excel Files (*.xls)",   
                   "DSN=New Excel Data Source\0"   
                   "Description=New Excel Data Source\0"   
                   "FileType=Excel\0"   
                   "DataDirectory=C:\\EXCELDIR\0"   
                   "MaxScanRows=20\0");  
```  
  
 このデータ ソースは、実際はフォルダー \(C:\\EXCELDIR\) です。このフォルダーは存在している必要があります。  Excel ドライバーは、フォルダーをそのデータ ソースとして使用し、ファイルを各テーブル \(.xls ファイルごとに 1 テーブル\) として使用するからです。  
  
 テーブルの作成の詳細については、「[データ ソース : プログラムにおける ODBC データ ソースのテーブルの作成](../../data/odbc/data-source-programmatically-creating-a-table-in-an-odbc-data-source.md)」を参照してください。  
  
 次に、**::SQLConfigDataSource** ODBC API 関数に渡す必要のあるパラメーターについて説明します。  **::SQLConfigDataSource** を使用するには、Odbcinst.h ヘッダー ファイルをインクルードし、Odbcinst.lib インポート ライブラリを使用する必要があります。  また、実行時には、パスに Odbccp32.dll \(16 ビットの場合は Odbcinst.dll\) を指定する必要があります。  
  
 ODBC データ ソース名は、ODBC データ ソース アドミニストレーターなどのユーティリティを使用して作成できます。  しかし、アプリケーションから直接データ ソース名を作成し、ユーザーが別のユーティリティを実行しなくてもアクセスできるようにする方が望ましい場合もあります。  
  
 通常、ODBC データ ソース アドミニストレーターは、コントロール パネルにインストールされます。ODBC データ ソース アドミニストレーターは、Windows レジストリ \(16 ビットの場合は Odbc.ini ファイル\) にエントリを追加することによって、新しいデータ ソースを作成します。  ODBC ドライバー マネージャーは、このファイルを問い合わせてデータ ソースに関する必要な情報を取得します。  レジストリに追加する情報は、**::SQLConfigDataSource** を呼び出して指定するため、確認しておく必要があります。  
  
 この情報は、**::SQLConfigDataSource** を使わずにレジストリに直接書き込むこともできます。しかし、これを直接書き込むアプリケーションは、ODBC ドライバー マネージャーがデータを保持するために現在使用している手法に依存しています。  新しいバージョンの ODBC ドライバー マネージャーでデータ ソースのレコードを保持する方法に変更があると、この手法を使うアプリケーションは動作しなくなります。  API 関数が提供されている場合はできるだけそれを使うようにしてください。  たとえば、**::SQLConfigDataSource** 関数を使用すると、Odbc.ini ファイルまたはレジストリへの書き込みが正しく行われるため、そのコードは 16 ビットから 32 ビットへ移植できます。  
  
##  <a name="_core_sqlconfigdatasource_parameters"></a> SQLConfigDataSource のパラメーター  
 ここでは **::SQLConfigDataSource** 関数のパラメーターについて説明します。  説明する内容の大半は、Visual C\+\+ バージョン 1.5 以降で提供されている『ODBC API Programmer's Reference』に収められています。  
  
###  <a name="_core_function_prototype"></a> 関数プロトタイプ  
  
```  
BOOL SQLConfigDataSource(HWND hwndParent,UINT fRequest, LPCSTR lpszDriver, LPCSTR lpszAttributes);  
```  
  
### 解説  
  
####  <a name="_core_parameters_and_usage"></a> パラメーターとその使い方  
 *hwndParent*  
 新しいデータ ソースに関する追加情報をユーザーから得るために ODBC ドライバー マネージャーまたは特定の ODBC ドライバーが作成するダイアログ ボックスのオーナーとして指定するウィンドウ。  `lpszAttributes` パラメーターの提供する情報が不十分な場合は、ダイアログ ボックスが表示されます。  *hwndParent* パラメーターが **NULL** である場合もあります。  
  
 `lpszDriver`  
 ドライバーの名前。  ユーザーに示す名前であり、物理ドライバー名 \(DLL\) ではありません。  
  
 `lpszAttributes`  
 "キー名\=値" 形式で指定する属性リスト。  各文字列は NULL ターミネータで区切ります。属性リストの最後には NULL ターミネータを 2 つ続けます。  これらの属性は、主として既定のドライバー固有のエントリであり、新しいデータ ソースのレジストリに入ります。  『ODBC API Reference』には説明されていないこの関数の重要なエントリとして、"DSN \(data source name\)" があります。DSN では、新しいデータ ソースの名前を指定します。  残りのエントリは、新しいデータ ソースのドライバー固有のエントリです。  エントリをすべて指定する必要はありません。ドライバーは、ダイアログ ボックスを表示してユーザーに新しい値を指定させることができるからです。ユーザーに新しい値の指定を要求する場合は、*hwndParent* に **NULL** を設定します。ユーザーに値の指定を要求しないときは、明示的に既定値を提供します。  
  
###### ODBC データ ソース アドミニストレーターを使用して lpszDriver パラメーターのドライバー名を指定するには  
  
1.  ODBC データ ソース アドミニストレーターを実行します。  
  
2.  **\[追加\]** をクリックします。  
  
 これにより、インストールされているドライバーとその記述の一覧が表示されます。  この記述を `lpszDriver` パラメーターとして使います。  なお、その際には記述全体を使います。たとえば、"Excel Files \(\*.xls\)" という記述の場合は、ファイル拡張子とかっこも含めます。  
  
 別の方法として、レジストリ \(16 ビットの場合は Odbcinst.ini ファイル\) でレジストリ キー "ODBC Drivers" \(Odbcinst.ini の場合は \[ODBC Drivers\] セクション\) の下のすべてのドライバー エントリと記述の一覧を調べることもできます。  
  
 `lpszAttributes` パラメーターのキー名と値を検索する 1 つの方法として、既に設定されているデータ ソース \(通常は ODBC データ ソース アドミニストレーターで設定したデータ ソース\) の Odbc.ini ファイルを調べることもできます。  
  
###### lpszAttributes パラメーターのキー名と値を探すには  
  
1.  Windows レジストリ エディターを実行します \(16 ビットの場合は Odbc.ini ファイルを開きます\)。  
  
2.  次のいずれかの方法を使用して ODBC データ ソース情報を検索します。  
  
    -   32 ビットの場合は、左ペインで **HKEY\_CURRENT\_USER\\Software\\ODBC\\ODBC.INI\\ODBC Data Sources** キーを検索します。  
  
         右側のペインには、"pub: REG\_SZ:*\<data source name\>*" という形式のエントリが一覧表示されます。*\<data source name\>* は、使用するドライバーに対して必要な設定が既に行われているデータ ソースを示します。  必要なデータ ソース \(SQL サーバーなど\) を選択します。  文字列 "pub:" の後に続くのは、`lpszAttributes` パラメーターで使う順のキー名と値です。  
  
    -   16 ビットの場合は、Odbc.ini ファイル内で \[*\<data source name\>*\] というセクションを検索します。  
  
         この行の後には、"キー名\=値" という形式の行が続きます。  これらの行が、`lpszAttributes` パラメーターで使うエントリです。  
  
 使用する特定のドライバーに関するドキュメントを調べるには、ドライバーのオンライン ヘルプを参照してください。  ドライバーのオンライン ヘルプにアクセスするには、ODBC データ ソース アドミニストレーターを実行します。  通常、これらのヘルプ ファイルは、Windows NT、Windows 3.1、または Windows 95 の WINDOWS\\SYSTEM ディレクトリにあります。  
  
###### ODBC ドライバーのオンライン ヘルプを参照するには  
  
1.  ODBC データ ソース アドミニストレーターを実行します。  
  
2.  **\[追加\]** をクリックします。  
  
3.  ドライバー名を選択します。  
  
4.  \[OK\] をクリックします。  
  
 選択したドライバーの新しいデータ ソースを作成するための情報が表示されたら、\[ヘルプ\] をクリックします。  このドライバーのヘルプ ファイルが開き、通常は、ドライバーの使い方に関する重要な情報が表示されます。  
  
## 参照  
 [データ ソース \(ODBC\)](../../data/odbc/data-source-odbc.md)