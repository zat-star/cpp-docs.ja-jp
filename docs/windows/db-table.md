---
title: "db_table | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_table"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_table attribute"
ms.assetid: ff9eb957-4e6d-4175-afcc-fd8ea916cec0
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# db_table
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE DB テーブルを開きます。  
  
## 構文  
  
```  
  
      [ db_table(   
   db_table,   
   name,   
   source_name,   
   hresult   
) ]  
```  
  
#### パラメーター  
 *db\_table*  
 指定した文字データベース テーブルの名前 \(「 Products 」など\)。  
  
 *名前* \(省略可能\)  
 テーブルを使用するハンドルの名前。  結果を複数の行に戻すにはこのパラメーターを指定する必要があります。  **db\_table** は行セットを行うかまたは複数のアクションのクエリを実行するために使用できる指定した名前の変数が生成されます。  
  
 *source\_name* \(省略可能\)  
 コマンドを実行するかを `db_source` の属性を持つクラスの `CSession` の変数またはインスタンスが要素に適用します。  [db\_source](../windows/db-source.md) を参照してください。  
  
 `hresult` \(省略可能\)  
 このデータベース コマンドの `HRESULT` を受け取る変数を識別します。  変数がない場合は属性によって自動的に挿入されます。  
  
## 解説  
 **db\_table** はテーブルを開くときに OLE DB コンシューマーが使用する [CTable](../data/oledb/ctable-class.md) のオブジェクトを構築します。  クラス レベルでのみこの属性を使用して ; インラインないと使用できません。  変数にテーブル列をバインドするに **db\_column** を使用してください ; パラメーター \(パラメーターの型を設定します\) 区切るには **db\_param** を使用します。  
  
 コンシューマー属性プロバイダーがクラスにこの属性を適用するとコンパイラは *YourClassName* はクラスを受け取るとコンパイラは\_YourClassNameAccessor から派生 *YourClassName と*  いうクラスを作成する名前です \_YourClassNameAccessor にクラスの名前を変更します。  \[クラス ビュー\] でこれらのクラスを参照してください。  
  
## 使用例  
 次の例では `CProducts` で Products テーブルを開きます。  
  
```  
// db_table.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_table(L"dbo.Products") ]  
class CProducts {  
   [ db_column("1") ] LONG m_ProductID;  
};  
```  
  
 アプリケーションで使用するこの属性の例のサンプル [AtlAgent](http://msdn.microsoft.com/ja-jp/52bef5da-c1a0-4223-b4e6-9e464b6db409) と [MultiRead](http://msdn.microsoft.com/ja-jp/5a2a915a-77dc-492f-94b2-1b809995dd5e) を参照してください。  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct`|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)