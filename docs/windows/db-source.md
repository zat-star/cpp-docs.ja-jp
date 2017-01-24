---
title: "db_source | Microsoft Docs"
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
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_source attribute"
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# db_source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データ ソースへの接続を作成します。  
  
## 構文  
  
```  
  
      [ db_source(   
   db_source,   
   name,   
   hresult   
) ]  
```  
  
#### パラメーター  
 *db\_source*  
 データ ソースに接続するための接続文字列。  接続文字列の形式についてはMicrosoft Data Access Components SDK [接続文字列データ リンク](https://msdn.microsoft.com/en-us/library/ms718376.aspx) を \(MDAC\) 参照してください。  
  
 *名前* \(省略可能\)  
 クラスの `db_source` を使用する場合  *は* そのフィールドに適用される `db_source` の属性を持つデータ ソース オブジェクトのインスタンスです \(例 1\) を参照してください。  メソッドの実装で `db_source` のインラインを使用する場合  *は*  データ ソースにアクセスするために使用できるメソッドのローカル変数 \(\) \(2\) 例を参照してください。  **db\_command** の `source_name` のパラメーターとデータ ソースにコマンドを関連付ける場合はこの  *名前を*  渡します。  
  
 `hresult` \(省略可能\)  
 このデータベース コマンドの `HRESULT` を受け取る変数を識別します。  変数がない場合は属性によって自動的に挿入されます。  
  
## 解説  
 `db_source` はOLE DB コンシューマーがデータ ソースとともに接続を表す [は CSession です。](../data/oledb/csession-class.md) のオブジェクトと [CDataSource](../Topic/CDataSource%20Class.md) を作成します。  
  
 クラスの `db_source` を使用すると`CSession` のオブジェクトがクラスのメンバーになります。  
  
 メソッドで `db_source` を使用すると挿入されたコードはメソッドのスコープ内で実行され`CSession` のオブジェクトはローカル変数として作成されます。  
  
 `db_source` はクラスまたはメソッド内でデータ ソースのプロパティを追加します。  \(`source_name` のパラメーターとして `db_source`  *名パラメーターを*  受け取る場合は **db\_command** とともに使用されます。  
  
 コンシューマー属性プロバイダーがクラスにこの属性を適用するとコンパイラは *YourClassName* はクラスを受け取るとコンパイラは\_YourClassNameAccessor から派生 *YourClassName と*  いうクラスを作成する名前です \_YourClassNameAccessor にクラスの名前を変更します。  \[クラス ビュー\] でこれらのクラスを参照してください。  
  
 アプリケーションで使用するこの属性の例のサンプル [AtlAgent](http://msdn.microsoft.com/ja-jp/52bef5da-c1a0-4223-b4e6-9e464b6db409) と [MultiRead](http://msdn.microsoft.com/ja-jp/5a2a915a-77dc-492f-94b2-1b809995dd5e) を参照してください。  
  
## 使用例  
 このサンプルではNorthwind データベースを使用してデータ ソース `ds` への接続を作成するにはクラスの `db_source` を呼び出します。  `ds` は `CMyCommand` のクラスによって内部的に使用できるデータ ソースのハンドルです。  
  
```  
// db_source_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[  
  db_source(L"my_connection_string", name="ds"),  
  db_command(L"select * from Products")  
]  
class CMyCommand {};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct` のメンバーはローカル メソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)