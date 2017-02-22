---
title: "db_param | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_param"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_param attribute"
ms.assetid: a28315f5-4722-459e-92ef-32e83c0b205a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# db_param
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したメンバー変数を入力または出力パラメーターに関連付け変数を区切ります。  
  
## 構文  
  
```  
  
      [ db_param(   
   ordinal,   
   paramtype="DBPARAMIO_INPUT",   
   dbtype,   
   precision,   
   scale,   
   status,   
   length  
) ]  
```  
  
#### パラメーター  
 `ordinal`  
 行セットの種類に対応する行数 **DBCOLUMNINFO** \(序数\) データをバインドする。  
  
 *paramtype* \(省略可能\)  
 パラメーターに対して設定する型。  プロバイダーは基になるデータ ソースによってサポートされるパラメーターの I\/O 型のみをサポートします。  型は **DBPARAMIOENUM** の一つまたは複数の値の組み合わせです :  
  
-   **DBPARAMIO\_INPUT** 入力パラメーター。  
  
-   **DBPARAMIO\_OUTPUT** 出力パラメーター。  
  
-   **DBPARAMIO\_NOTPARAM** にアクセサーパラメーターはありません。  パラメーターを無視して行のアクセサーでこの値に設定 **eParamIO** はを示します。  
  
 *dbtype* \(省略可能\)  
 列のエントリの OLE DB [インジケーター型](https://msdn.microsoft.com/en-us/library/ms711251.aspx)。  
  
 *精密* \(省略可能\)  
 列のエントリに使用される精度。  詳細については[DBBINDING 構造](https://msdn.microsoft.com/en-us/library/ms716845.aspx) の **bPrecision** の要素の説明を参照してください。  
  
 *スケール* \(省略可能\)  
 列のエントリに使用するスケール。  詳細については[DBBINDING 構造](https://msdn.microsoft.com/en-us/library/ms716845.aspx) の **bScale** の要素の説明を参照してください。  
  
 *状態* \(省略可能\)  
 この列の状態を保持するメンバー変数。  状態は列の値がデータ値またはそのほかの値であるかを示します **null** など\)。  有効な値については" *OLE DB Programmer's Reference " の* [状態](https://msdn.microsoft.com/en-us/library/ms722617.aspx) を参照してください。  
  
 *長さ* \(省略可能\)  
 バイト列のサイズを保持するメンバー変数。  
  
## 解説  
 **db\_param** はコマンドで使用するパラメーターを定義します ; したがって **db\_command** で使用できます。  たとえばSQL クエリまたはスト プロシージャのパラメーターにバインド **db\_param** を使用できます。  スト プロシージャのパラメーターは疑問符 \(\) が表示されパラメーターの順序でデータ メンバーをバインドする必要があります。  
  
 **db\_param** はOLE DB `ICommandWithParameters` のベースのバインディングに含めることができるメンバーのデータを区切ります。  このメソッドはパラメーターの型 \(\) の入力または出力指定したパラメーターの型はOLE DB の精度スケーリングステータスおよび長さを設定します。  この属性はOLE DB コンシューマー BEGIN\_PARAM\_MAP マクロを…  END\_PARAM\_MAP.  **db\_param**属性でマークする各メンバーはCOLUMN\_ENTRY の形式でマップ 1 エントリを使用します。  
  
 **db\_param** は [db\_table](../windows/db-table.md) または [db\_command](../windows/db-command.md) 属性とともに使用されます。  
  
 コンシューマー属性プロバイダーがクラスにこの属性を適用するとコンパイラは *YourClassName* はクラスを受け取るとコンパイラは\_YourClassNameAccessor から派生 *YourClassName と*  いうクラスを作成する名前です \_YourClassNameAccessor にクラスの名前を変更します。  \[クラス ビュー\] でこれらのクラスを参照してください。  
  
## 使用例  
 次の例ではNorthwind データベースの SalesbyYear ストのプロシージャに基づいてコマンド クラスを作成します。  これは `m_RETURN_VALUE` の変数とスト プロシージャの最初のパラメーターを関連付け出力パラメーターを定義します。  これは `m_Beginning_Date` と `m_Ending_Date` と最後の 2 回の入力パラメーター \(\) を関連付けます。  
  
 次の例では出力パラメーターと `nOutput` の変数に関連付けます。  
  
```  
// db_param.cpp  
// compile with: /LD  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
[ db_source(L"my_connection_string"),   
  db_command(L"{ ? = CALL dbo.\"Sales by Year\"(?,?) }")   
]  
struct CSalesbyYear {  
   DBSTATUS m_dwShippedDateStatus;  
   DBSTATUS m_dwOrderIDStatus;  
   DBSTATUS m_dwSubtotalStatus;  
   DBSTATUS m_dwYearStatus;  
  
   DBLENGTH m_dwShippedDateLength;  
   DBLENGTH m_dwOrderIDLength;  
   DBLENGTH m_dwSubtotalLength;  
   DBLENGTH m_dwYearLength;  
  
   // Bind columns  
   [ db_column("1", status="m_dwShippedDateStatus", length="m_dwShippedDateLength") ] DBTIMESTAMP m_ShippedDate;  
   [ db_column("2", status="m_dwOrderIDStatus", length="m_dwOrderIDLength") ] LONG m_OrderID;  
   [ db_column("3", status="m_dwSubtotalStatus", length="m_dwSubtotalLength") ] CURRENCY m_Subtotal;  
   [ db_column("4", status="m_dwYearStatus", length="m_dwYearLength") ] TCHAR m_Year[31];  
  
   // Bind parameters  
   [ db_param("1", paramtype="DBPARAMIO_OUTPUT") ] LONG m_RETURN_VALUE;  
   [ db_param("2", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Beginning_Date;  
   [ db_param("3", paramtype="DBPARAMIO_INPUT") ] DBTIMESTAMP m_Ending_Date;  
};  
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