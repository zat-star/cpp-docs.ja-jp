---
title: "レコード フィールド エクスチェンジ: RFX 関数の使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データ型 [C++], ODBC レコード フィールド エクスチェンジ"
  - "DoFieldExchange メソッド, および RFX 関数"
  - "関数呼び出し, RFX 関数"
  - "ODBC [C++], データ型"
  - "ODBC [C++], RFX"
  - "RFX (ODBC) [C++], データ型"
  - "RFX (ODBC) [C++], 関数構文とパラメーター"
ms.assetid: c594300b-5a29-4119-a68b-e7ca32def696
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコード フィールド エクスチェンジ: RFX 関数の使い方
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、`DoFieldExchange` オーバーライドの中心部分となる RFX 関数呼び出しの使用方法について説明します。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない [CRecordset](../Topic/CRecordset%20Class.md) の派生クラスを対象にしています。  バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ \(Bulk RFX: Bulk Record Field Exchange\) が実装されています。  Bulk RFX と RFX は似ています。  両者の差異については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 RFX グローバル関数は、データ ソースの列とレコードセットのフィールド データ メンバー間でデータを交換します。  レコードセットのメンバー関数 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) に RFX 関数呼び出しコードを作成します。  ここでは、RFX 関数の概要と RFX 関数が用意されているデータ型について説明します。  新しく定義したデータ型に対する RFX 関数を独自に作成する方法については、「[テクニカル ノート 43: RFX ルーチン](../Topic/TN043:%20RFX%20Routines.md)」で説明されています。  
  
##  <a name="_core_rfx_function_syntax"></a> RFX 関数の構文  
 各 RFX 関数は、次の 3 つのパラメーターを使用します \(これ以外に 1 個または 2 個のオプション パラメーターを使用する関数もあります\)。  
  
-   [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) オブジェクトへのポインターを返します。  `DoFieldExchange` に渡された `pFX` ポインターをそのまま渡します。  
  
-   データ ソース中の列名。  
  
-   レコードセット クラス内の対応するフィールド データ メンバーまたはパラメーター データ メンバーの名前。  
  
-   転送する文字列または配列の最大長を指定できる関数もあります。  既定値は 255 バイトですが、必要に応じて変更できます。  最大値は、`CString` オブジェクトの最大値である **INT\_MAX** \(2,147,483,647 バイト\) ですが、通常はそれ以前にドライバーの限界に達します。  
  
-   `RFX_Text` 関数では、列のデータ型を指定する第 5 パラメーターを取る場合もあります。  
  
 詳細については、『MFC リファレンス』の「[マクロ、グローバル関数、およびグローバル変数](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)」で各 RFX 関数の解説を参照してください。  パラメーターの特殊な使い方の例については、「[レコードセット : 集計値の計算 \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)」を参照してください。  
  
##  <a name="_core_rfx_data_types"></a> RFX 関数とデータ型  
 クラス ライブラリには、データ ソースとレコードセット間で各種のデータ型を転送するための RFX 関数が多数用意されています。  次の表に、RFX 関数とデータ型の対応を示します。  RFX 関数を直接呼び出すには、データ型に応じてこれらの関数を使い分けます。  
  
|関数|データ型|  
|--------|----------|  
|`RFX_Bool`|**BOOL**|  
|`RFX_Byte`|**BYTE**|  
|`RFX_Binary`|`CByteArray`|  
|`RFX_Double`|**double**|  
|`RFX_Single`|**float**|  
|`RFX_Int`|`int`|  
|`RFX_Long`|**long**|  
|`RFX_LongBinary`|`CLongBinary`|  
|`RFX_Text`|`CString`|  
|`RFX_Date`|`CTime`|  
  
 詳細については、『MFC リファレンス』の「[マクロ、グローバル関数、およびグローバル変数](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)」で各 RFX 関数の解説を参照してください。  C\+\+ のデータ型の SQL のデータ型への対応については、「[SQL : SQL と C\+\+ のデータ型 \(ODBC\)](../../data/odbc/sql-sql-and-cpp-data-types-odbc.md)」の表「ANSI SQL データ型と C\+\+ データ型の対応」を参照してください。  
  
## 参照  
 [レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [レコードセット: パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [レコードセット: データ列を動的に結びつける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)