---
title: "データ ソース: 接続 (ODBC) | Microsoft Docs"
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
  - "接続文字列 [C++], 汎用化"
  - "接続 [C++], データ ソース"
  - "データ ソース [C++], 接続"
  - "データベース接続 [C++], 作成"
  - "データベース接続 [C++], MFC ODBC クラス"
  - "データベース [C++], 接続"
  - "接続の解除 (データ ソースを)"
  - "汎用化 (接続文字列を)"
  - "GetDefaultConnect メソッド"
  - "ODBC [C++], 接続の解除 (データ ソースを)"
  - "ODBC 接続 [C++], 構成"
  - "ODBC 接続 [C++], 接続 (データ ソースに)"
  - "ODBC 接続 [C++], 接続の解除"
  - "ODBC データ ソース [C++], 接続"
  - "ODBC データ ソース [C++], マルチユーザー環境"
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# データ ソース: 接続 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 このトピックでは、次の内容について説明します。  
  
-   [データ ソースの設定](#_core_configuring_a_data_source)  
  
-   [マルチユーザー環境](#_core_working_in_a_multiuser_environment)  
  
-   [接続文字列の汎用化](#_core_generalizing_the_connection_string)  
  
-   [データ ソースへの接続](#_core_connecting_to_a_specific_data_source)  
  
-   [データ ソースとの接続の終了](#_core_disconnecting_from_a_data_source)  
  
-   [CDatabase オブジェクトの再利用](#_core_reusing_a_cdatabase_object)  
  
 データ ソースとの接続とは、データにアクセスするために DBMS との通信を確立することです。  ODBC ドライバーを通じてデータ ソースと接続すると、データ ソースの位置がローカルでもネットワークでも、自動的に接続されます。  
  
 ODBC ドライバーがあるデータ ソースならば、どのデータ ソースにでも接続できます。  アプリケーションのユーザーも、同じ ODBC ドライバーを持つ必要があります。  ODBC ドライバーの再配布方法の詳細については、「[ODBC の構成要素の配布](../../data/odbc/redistributing-odbc-components-to-your-customers.md)」を参照してください。  
  
##  <a name="_core_configuring_a_data_source"></a> データ ソースの設定  
 データ ソースの設定は、ODBC データ ソース アドミニストレーターを使って行います。  データ ソースの追加や削除も行うことができます。  アプリケーションを作成する際には、ODBC データ ソース アドミニストレーターを使用してデータ ソースを追加するようにアプリケーションのユーザーに指示するか、アプリケーション内で ODBC インストール呼び出しを直接行って ODBC データ ソース アドミニストレーターの機能を組み込むことができます。  詳細については、「[ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)」を参照してください。  
  
 Excel のファイルをデータ ソースとして使うこともできます。この場合は、ファイルを登録し、\[データ ソースの選択\] ダイアログ ボックスに表示されるように設定する必要があります。  
  
#### Excel のファイルをデータ ソースとして使うには  
  
1.  ODBC データ ソース アドミニストレーターを使ってファイルを設定します。  
  
2.  \[DSN\] タブの \[追加\] をクリックします。  
  
3.  \[データ ソースの新規作成\] ダイアログ ボックスで、Excel ドライバーを選択し、**\[次へ\]** をクリックします。  
  
4.  \[参照\] をクリックし、データ ソースとして使用するファイルの名前を選択します。  
  
> [!NOTE]
>  ドロップダウン メニューの **\[すべてのファイル\]** を選択しないと、.xls ファイルが表示されない場合もあります。  
  
1.  **\[次へ\]** をクリックし、\[完了\] をクリックします。  
  
2.  \[ODBC Microsoft Excel Setup\] ダイアログ ボックスで、データベースのバージョンとブックを選択します。  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> マルチユーザー環境  
 複数のユーザーが同じデータ ソースにアクセスする場合は、自分がアクセスしているレコードセットのデータが、ほかのユーザーによって変更されてしまうおそれがあります。  同じように、自分が他のユーザーのレコードセットを変更してしまう場合もあります。  詳細については、「[レコードセット : レコード更新のしくみ \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)」および「[トランザクション \(ODBC\)](../../data/odbc/transaction-odbc.md)」を参照してください。  
  
##  <a name="_core_generalizing_the_connection_string"></a> 接続文字列の汎用化  
 ウィザードは、既定の接続文字列を使ってデータ ソースとの接続を行います。  アプリケーションの開発時には、この接続を使ってテーブルや列を表示できます。  しかし、この既定の接続文字列は、アプリケーションのユーザーがデータ ソースに接続する際に適切ではない場合もあります。  たとえば、実際に使われるデータ ソースおよびその位置を表すパスは、開発時とは異なる場合があります。  そのような場合は、ウィザードによって実装されたメンバー関数 [CRecordset::GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md) をより汎用的なかたちに置き換える必要があります。  たとえば、次のような方法があります。  
  
-   ODBC データ ソース アドミニストレーターを使って接続文字列の登録、管理を行います。  
  
-   接続文字列を編集し、データ ソース名を削除します。  フレームワークによって、データ ソース名として ODBC が指定され、実行時には、ODBC では、データ ソース名などの必要な接続情報の入力を求めるダイアログ ボックスが表示されます。  
  
-   データ ソース名だけを指定します。  ODBC は、必要に応じて、ユーザー ID とパスワードの入力を求めます。  たとえば、元の接続文字列が次のようになっているとします。  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     この接続文字列は、Windows NT 統合セキュリティを使用する、信頼できる接続を指定します。  セキュリティ上の重大な弱点が生成されるため、パスワードのハードコーディングや空白のパスワードの指定は避けてください。  その代わりに、`GetDefaultConnect` に新しい接続文字列を指定して、ユーザー ID とパスワードの問い合わせができます。  
  
    ```  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> データ ソースへの接続  
 特定のデータ ソースに接続するには、あらかじめ [ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)でデータ ソースを設定しておきます。  
  
#### データ ソースに接続するには  
  
1.  `CDatabase` オブジェクトを構築します。  
  
2.  メンバー関数の `OpenEx` または **Open** を呼び出します。  
  
 ウィザードで指定したデータ ソース以外のデータ ソースを指定する方法については、『MFC リファレンス』の「[CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md)」または「[CDatabase::Open](../Topic/CDatabase::Open.md)」を参照してください。  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> データ ソースとの接続の終了  
 `CDatabase` のメンバー関数 **Close** を呼び出す前に、開いているすべてのレコードセットを閉じます。  閉じようとしている `CDatabase` オブジェクトに関連付けられているレコードセットでは、保留中の `AddNew` ステートメントまたは **Edit** ステートメントはキャンセルされ、保留中のすべてのトランザクションはロールバックされます。  
  
#### データ ソースとの接続を終了するには  
  
1.  `CDatabase` オブジェクトのメンバー関数 [Close](../Topic/CDatabase::Close.md) を呼び出します。  
  
2.  再利用しない場合にはオブジェクトを破棄します。  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> CDatabase オブジェクトの再利用  
 接続を終了した後で `CDatabase`オブジェクトを再利用できます。再利用時の接続先は、同じデータ ソースでも別のデータ ソースでもかまいません。  
  
#### CDatabase オブジェクトを再利用するには  
  
1.  オブジェクトの元の接続を閉じます。  
  
2.  オブジェクトを破棄せずに、そのメンバー関数の `OpenEx` または **Open** を再度呼び出します。  
  
## 参照  
 [データ ソース \(ODBC\)](../../data/odbc/data-source-odbc.md)   
 [データ ソース: データ ソースのスキーマの判定 \(ODBC\)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)