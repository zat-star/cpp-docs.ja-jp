---
title: "SQL: SQL と C++ のデータ型 (ODBC) | Microsoft Docs"
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
  - "データ型 [C++], SQL と C++"
  - "SQL [C++], および C++ のデータ型"
  - "SQL データ型 [C++]"
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: SQL と C++ のデータ型 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  この内容は、MFC ODBC クラスに該当します。  MFC DAO クラスを使用している場合は、DAO ヘルプの「Comparison of Microsoft Jet Database Engine SQL and ANSI SQL」を参照してください。  
  
 次の表に、ANSI SQL のデータ型と C\+\+ のデータ型の対応を示します。  この表は、MSDN ライブラリ CD の『ODBC Programmer's Reference』の「Appendix D: Data Types」を補足したものです。  データ型の変換は、ほとんどウィザードが自動的に行います。  ウィザードを使わない場合は、この表を参照して各フィールドのデータ交換を行ってください。  
  
### ANSI SQL データ型と C\+\+ データ型の対応  
  
|ANSI SQL データ型|C\+\+ データ型|  
|-------------------|----------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**INTEGER**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**BINARY**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**TIME**|**CTime、CString**|  
|**TIMESTAMP**|**CTime、CString**|  
  
 1.  **SQL\_C\_CHAR** が既定の SQL 変換型なので、ANSI **DECIMAL** と **NUMERIC** は `CString` に変換されます。  
  
 2.  既定では、255 文字を超える文字データは、256 文字目以降が切り捨てられ、`CString` に変換されます。  `RFX_Text` の `nMaxLength` 引数を明示的に設定することにより、切り捨ての長さを拡張できます。  
  
 3.  既定では、255 文字を超えるバイナリ データは、256 文字目以降が切り捨てられ、`CByteArray` に変換されます。  `RFX_Binary` の `nMaxLength` 引数を明示的に設定することにより、切り捨ての長さを拡張できます。  
  
 ODBC カーソル ライブラリを使用しないと、Microsoft SQL Server ODBC ドライバーと MFC ODBC データベース クラスを使用して長い可変長フィールドを複数更新できないことがあります。  ODBC の **SQL\_LONGVARCHAR** 型と **SQL\_LONGVARBINARY** 型は、SQL サーバーの text 型と image 型に対応付けられています。  複数の長い可変長フィールドを 1 回の `CRecordset::Update` 呼び出しで更新すると、`CDBException` がスローされます。  したがって、`CRecordset::Update` の 1 回の呼び出しで長い列を複数同時に更新しないでください。  ODBC API 関数 **SQLPutData** では、長い列を複数同時に更新できます。  ODBC カーソル ライブラリも使用できます。ただし、SQL サーバー ドライバーなど、カーソルをサポートしていているドライバーの場合は、カーソル ライブラリは必要ありません。  
  
 MFC ODBC データベース クラスおよび Microsoft SQL Server ODBC ドライバーで ODBC カーソル ライブラリを使用すると、`CRecordset::Requery` を呼び出してから `CRecordset::Update` を呼び出したときに、`CDBException` と **ASSERT** が同時に発生します。  このような場合は、`CRecordset::Requery` ではなく、`CRecordset::Close` と `CRecordset::Open` を呼び出します。  または、ODBC カーソル ライブラリを使わないようにします。SQL サーバーと SQL サーバー ODBC ドライバーは、本来カーソルをサポートしているので、ODBC カーソル ライブラリは必要ないからです。  
  
## 参照  
 [SQL](../../data/odbc/sql.md)   
 [SQL: SQL の直接呼び出し \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)