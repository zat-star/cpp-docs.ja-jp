---
title: "db_command | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_command 属性"
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# db_command
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE DB コマンドを作成します。  
  
## 構文  
  
```  
  
[ db_command(   
command  
,   
   name  
,   
   source_name  
,   
   hresult  
,   
   bindings  
,   
   bulk_fetch  
)  
]  
  
```  
  
#### パラメーター  
 `command`  
 OLE DB コマンドのテキストを含むコマンド文字列。 簡単な例を次に示します。  
  
```  
[ db_command ( command = "Select * from Products" ) ]  
```  
  
 *command* の構文は次のとおりです。  
  
```  
binding parameter block 1  
   OLE DB command  
binding parameter block 2  
   continuation of OLE DB command  
binding parameter block 3  
...  
```  
  
 *binding parameter block* は次のように定義します。  
  
 **\(\[** `bindtype` **\]** *szVar1* \[*, szVar2* \[, *nVar3* \[, ...\]\]\] **\)**  
  
 それぞれの文字について以下に説明します。  
  
 **\(** は、データ バインディング ブロックの開始を示します。  
  
 **\[** `bindtype` **\]** は次のいずれかの文字列です。大文字と小文字は区別されません。  
  
-   **\[db\_column\]** は、各メンバー変数を行セットの列にバインドします。  
  
-   **\[bindto\]** \(**\[db\_column\]** と同じ\)。  
  
-   **\[in\]** は、入力パラメーターとしてメンバー変数をバインドします。  
  
-   **\[out\]** は、出力パラメーターとしてメンバー変数をバインドします。  
  
-   **\[in,out\]** は、入力\/出力パラメーターとしてメンバー変数をバインドします。  
  
 *SzVarX* は、現在のスコープ内のメンバー変数に解決されます。  
  
 **\)** は、データ バインディング ブロックの終了を示します。  
  
 コマンド文字列に \[in\]、\[out\]、\[in\/out\] などの指定子が 1 つ以上含まれる場合、**db\_command** はパラメーター マップを作成します。  
  
 コマンド文字列に \[db\_column\] や \[bindto\] などのパラメーターが 1 つ以上含まれる場合、**db\_command** は行セットと、これらのバインドされた変数を提供するためのアクセサー マップを生成します。 詳しくは、「[db\_accessor](../windows/db-accessor.md)」をご覧ください。  
  
> [!NOTE]
>  \[`bindtype`\] 構文と `bindings` パラメーターは、**db\_command** をクラス レベルで使用するときは無効です。  
  
 バインディング パラメーター ブロックの例を次にいくつか示します。 次の例では、pubs データベースの authors テーブルの `au_fname` 列と `au_lname` 列に、それぞれ `m_au_fname` および `m_au_lname` データ メンバーをバインドします。  
  
```  
TCHAR m_au_fname[21];  
TCHAR m_au_lname[41];  
TCHAR m_state[3] = 'CA';  
  
[db_command (  
   command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \  
   "FROM dbo.authors " \  
   "WHERE state = ?([in]m_state)")  
```  
  
 \]  
  
 *name* \(省略可能\)  
 行セットの操作に使用するハンドルの名前。*name* を指定した場合、**db\_command** は指定された *name* のクラスを生成します。このクラスを使用して、行セットを走査したり、複数のアクション クエリを実行したりできます。*name* を指定しないと、複数の結果行をユーザーに返すことはできません。  
  
 *source\_name* \(省略可能\)  
 `CSession` 変数、または `db_source` 属性が適用された、コマンドが実行されるクラスのインスタンス。 「[db\_source](../windows/db-source.md)」をご覧ください。  
  
 **db\_command** は *source\_name* に使用されている変数が有効であることを確認するので、指定する変数は関数スコープまたはグローバル スコープに存在する必要があります。  
  
 `hresult` \(省略可能\)  
 このデータベース コマンドの `HRESULT` を受け取る変数を示します。 変数が存在しない場合は、属性によって自動的に挿入されます。  
  
 *bindings* \(省略可能\)  
 OLE DB コマンドからバインディング パラメーターを分離できます。  
  
 `bindings` の値を指定すると、**db\_command** は関連付けられている値を解析し、\[`bindtype`\] パラメーターを解析しません。 これにより、OLE DB プロバイダーの構文を使用できます。 解析を無効にするには、バインディング パラメーターのない **Bindings\=""** を指定します。  
  
 `bindings` の値を指定しないと、**db\_command** はバインディング パラメーター ブロックを解析し、"**\(**"、角かっこで囲まれた **\[**`bindtype`**\]**、前に宣言されている 1 つ以上の C\+\+ メンバー変数、"**\)**" という順番の記述を探します。 かっこで囲まれたすべてのテキストが最終的なコマンドから削除され、これらのパラメーターを使用してこのコマンドの列とパラメーターのバインディングが作成されます。  
  
 *bulk\_fetch* \(省略可能\)  
 フェッチする行数を指定する整数値。  
  
 既定値は 1 で、単一行のフェッチを指定します \(行セットは [CRowset](../Topic/CRowset%20Class.md) 型です\)。  
  
 1 より大きい値は、バルク行フェッチを指定します。 バルク行フェッチとは、複数の行ハンドルをフェッチするバルク行セットの機能のことです \(行セットは [CBulkRowset](../Topic/CBulkRowset%20Class.md) 型であり、指定された行数で `SetRows` を呼び出します\)。  
  
 *bulk\_fetch* が 1 より小さい場合は、`SetRows` は 0 を返します。  
  
## 解説  
 OLE DB コンシューマーは、**db\_command** によって作成された [CCommand](../data/oledb/ccommand-class.md) オブジェクトを使用して、コマンドを実行します。  
  
 **db\_command** はクラス スコープまたは関数スコープで使用できます。主な違いは、`CCommand` オブジェクトのスコープです。 関数スコープでは、バインディングなどのデータは関数の終了時に終了します。 クラス スコープでも関数スコープでも OLE DB コンシューマー テンプレート クラスの **CCommand\<\>** が関係しますが、テンプレート引数は関数スコープとクラス スコープで異なります。 関数スコープではバインディングはローカル変数を構成する **Accessor** に対して行われますが、クラス スコープでは引数として `CAccessor` 派生クラスを予期します。 クラス属性として使用すると、**db\_command** は **db\_column** と共に動作します。  
  
 **db\_command** を使用して、結果セットを返さないコマンドを実行できます。  
  
 コンシューマー属性プロバイダーがこの属性をクラスに適用すると、コンパイラはクラスの名前を \_*YourClassName*Accessor に変更します。*YourClassName* は開発者がクラスに指定した名前です。コンパイラは、\_*YourClassName*Accessor から派生する *YourClassName* という名前のクラスも作成します。  クラス ビューでは、両方のクラスが表示されます。  
  
## 使用例  
 この例では、テーブルから state 列が 'CA' と一致する姓と名を選択するコマンドを定義しています。**db\_command** は、ウィザードで生成される [OpenAll and CloseAll](../Topic/Consumer%20Wizard-Generated%20Methods.md) などの関数および [MoveNext](../data/oledb/crowset-movenext.md) などの `CRowset` メンバー関数を呼び出すことができる行セットを作成して読み取ります。  
  
 このコードでは、pubs データベースに接続する独自の接続文字列を指定する必要があることに注意してください。 開発環境でこれを行う方法については、「[How to: Connect to a Database from Server Explorer](http://msdn.microsoft.com/ja-jp/7c1c3067-0d77-471b-872b-639f9f50db74)」および「[How to: Add New Data Connections in Server Explorer\/Database Explorer](http://msdn.microsoft.com/ja-jp/fb2f513b-ddad-4142-911e-856bba0054c8)」をご覧ください。  
  
```  
// db_command.h  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
#pragma once  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
  
struct CAuthors {  
   // In order to fix several issues with some providers, the code below may bind  
   // columns in a different order than reported by the provider  
  
   DBSTATUS m_dwau_lnameStatus;  
   DBSTATUS m_dwau_fnameStatus;  
   DBLENGTH m_dwau_lnameLength;  
   DBLENGTH m_dwau_fnameLength;  
  
   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];  
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];  
  
   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];  
  
   void GetRowsetProperties(CDBPropSet* pPropSet) {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   }  
};  
```  
  
## 使用例  
  
```  
// db_command.cpp  
// compile with: /c  
#include "db_command.h"  
  
int main(int argc, _TCHAR* argv[]) {  
   HRESULT hr = CoInitialize(NULL);  
  
   // Instantiate rowset  
   CAuthors rs;  
  
   // Open rowset and move to first row  
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));  
   hr = rs.OpenAll();  
   hr = rs.MoveFirst();  
  
   // Iterate through the rowset  
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {  
      // Print out the column information for each row  
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);  
      hr = rs.MoveNext();  
   }  
  
   rs.CloseAll();  
   CoUninitialize();  
}  
```  
  
## 使用例  
 この例では、データ ソース クラス `CMySource` で `db_source` を使用し、コマンド クラス `CCommand1` と `CCommand2` で `db_command` を使用します。  
  
```  
// db_command_2.cpp  
// compile with: /c  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
// class usage for both db_source and db_command  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
struct CMySource {  
   HRESULT OpenDataSource() {  
      return S_OK;  
   }  
};  
  
[db_command(command = "SELECT * FROM Products")]  
class CCommand1 {};  
  
[db_command(command = "SELECT FNAME, LNAME FROM Customers")]  
class CCommand2 {};  
  
int main() {  
   CMySource s;  
   HRESULT hr = s.OpenDataSource();  
   if (SUCCEEDED(hr)) {  
      CCommand1 c1;  
      hr = c1.Open(s);  
  
      CCommand2 c2;  
      hr = c2.Open(s);  
   }  
  
   s.CloseDataSource();  
}  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**class**、`struct`、member、method、local|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)