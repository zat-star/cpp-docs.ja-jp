---
title: "db_column | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_column"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_column attribute"
ms.assetid: 58da4afc-f69c-4ae6-af9a-3f9515f56081
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# db_column
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

行セットの変数に指定した列をバインドします。  
  
## 構文  
  
```  
  
      [ db_column(   
   ordinal,   
   dbtype,   
   precision,   
   scale,   
   status,   
   length   
) ]  
```  
  
#### パラメーター  
 `ordinal`  
 順序の行数 **DBCOLUMNINFO** \(序数\) または行セットの種類に対応する項目の名前 \(ANSI 形式または Unicode 文字列\) データをバインドする。  数値を使用すると実行中の序数をスキップできます \(例 : 1235\)。  名前はOLE DB プロバイダーがサポートを使用して空白が含まれている場合があります。  たとえば次の形式のいずれかを使用できます :  
  
```  
[db_column("2")] TCHAR szCity[30];  
[db_column(L"city_name")] TCHAR szCity[30];  
```  
  
 *dbtype* \(省略可能\)  
 列のエントリの OLE DB [インジケーター型](https://msdn.microsoft.com/en-us/library/ms711251.aspx)。  
  
 *精密* \(省略可能\)  
 列のエントリに使用される精度。  詳細については[DBBINDING 構造](https://msdn.microsoft.com/en-us/library/ms716845.aspx) の `bPrecision` の要素の説明を参照してください。  
  
 *スケール* \(省略可能\)  
 列のエントリに使用するスケール。  詳細については[DBBINDING 構造](https://msdn.microsoft.com/en-us/library/ms716845.aspx) の `bScale` の要素の説明を参照してください。  
  
 *状態* \(省略可能\)  
 この列の状態を保持するメンバー変数。  状態は列の値がデータ値またはそのほかの値であるかを示します **null** など\)。  有効な値については" *OLE DB Programmer's Reference " の* [状態](https://msdn.microsoft.com/en-us/library/ms722617.aspx) を参照してください。  
  
 *長さ* \(省略可能\)  
 バイト列のサイズを保持するメンバー変数。  
  
## 解説  
 **db\_column** は行セットの変数に指定したテーブルの列をバインドします。  これは OLE DB `IAccessor` のベースのバインディングに含めることができるメンバーのデータを区切ります。  この属性はOLE DB コンシューマー [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)マクロ [END\_COLUMN\_MAP](../data/oledb/end-column-map.md) と [COLUMN\_ENTRY](../data/oledb/column-entry.md) を使用して定義された列マップを作成します。  これらは指定された列をバインドする OLE DB [DBBINDING 構造](https://msdn.microsoft.com/en-us/library/ms716845.aspx) を処理します。  **db\_column**属性でマークする各メンバーは列のエントリの形式で列マップの 1 エントリを使用します。  このためコマンド クラスまたはテーブルに列をマップするつまりこの属性を呼び出します。  
  
 [db\_table](../windows/db-table.md) または [db\_command](../windows/db-command.md) 属性とともに **db\_column** を使用します。  
  
 コンシューマー属性プロバイダーがクラスにこの属性を適用するとコンパイラは *YourClassName* はクラスを受け取るとコンパイラは\_YourClassNameAccessor から派生 *YourClassName と*  いうクラスを作成する名前です \_YourClassNameAccessor にクラスの名前を変更します。  \[クラス ビュー\] でこれらのクラスを参照してください。  
  
 アプリケーションで使用するこの属性の例についてはサンプル [AtlAgent](http://msdn.microsoft.com/ja-jp/52bef5da-c1a0-4223-b4e6-9e464b6db409)[MultiRead](http://msdn.microsoft.com/ja-jp/5a2a915a-77dc-492f-94b2-1b809995dd5e) を参照してください。  
  
## 使用例  
 この例では **long** データ メンバーにテーブルの列をバインドしステータスと長さのフィールドを指定します。  
  
```  
// db_column_1.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   DBSTATUS m_dwProductIDStatus;  
   DBLENGTH m_dwProductIDLength;  
  
   [ db_column("1", status="m_dwProductIDStatus", length="m_dwProductIDLength") ] LONG m_ProductID;  
};  
```  
  
## 使用例  
 このサンプルでは順序で **long**文字列タイムスタンプおよび **DB\_NUMERIC** の整数を 4 列をバインドします。  
  
```  
// db_column_2.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_command(L"Select * from Products") ]  
class CProducts {  
   [db_column("1")] LONG m_OrderID;  
   [db_column("2")] TCHAR m_CustomerID[6];  
   [db_column("4")] DB_NUMERIC m_OrderDate;     
   [db_column("7", dbtype="DBTYPE_NUMERIC")] DB_NUMERIC m_ShipVia;  
};  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|**クラス**  `struct` のメンバーメソッド|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 属性コンテキストの詳細については、「[属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## 参照  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)