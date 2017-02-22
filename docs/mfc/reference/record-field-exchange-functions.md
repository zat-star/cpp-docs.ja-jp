---
title: "レコード フィールド エクスチェンジ (RFX) 関数 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (データ アクセス オブジェクト), レコード フィールド エクスチェンジ (DFX)"
  - "ODBC, バルク RFX データ交換関数"
  - "RFX (レコード フィールド エクスチェンジ), ODBC クラス"
  - "DFX (DAO レコード フィールド エクス チェンジ), データ交換関数"
  - "DFX 関数"
  - "バルク RFX 関数"
  - "DFX (DAO レコード フィールド エクスチェンジ)"
  - "RFX (レコード フィールド エクスチェンジ), DAO クラス"
  - "ODBC, RFX"
  - "RFX (レコード フィールド エクス チェンジ), データ交換関数"
  - "RFX (レコード フィールド エクスチェンジ)"
ms.assetid: 6e4c5c1c-acb7-4c18-bf51-bf7959a696cd
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# レコード フィールド エクスチェンジ (RFX) 関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、レコードセット オブジェクトとそのデータ ソース間のデータ転送を自動化したり、データに対してその他の操作を実行したりするためのレコード フィールド エクスチェンジの関数 \([RFX](#_mfc_rfx_functions_.28.odbc.29)、[バルク RFX](#_mfc_bulk_rfx_functions_.28.odbc.29)、および [DFX](#_mfc_dfx_functions_.28.dao.29)\) の一覧を示します。  
  
 ODBC ベースのクラスを使用し、バルク行フェッチを実装している場合は、データ ソース列に対応する各データ メンバーに対してバルク RFX 関数を呼び出すことによって、`CRecordset` の `DoBulkFieldExchange` メンバー関数を手動でオーバーライドする必要があります。  
  
 ODBC ベースのクラスにバルク行フェッチを実装していない場合または DAO ベースのクラスを使用している場合は、ClassWizard で、レコードセットの各フィールド データ メンバーに対して RFX 関数 \(ODBC クラスの場合\) または DFX 関数 \(DAO クラスの場合\) を呼び出すことで、`CRecordset` または `CDaoRecordset` の `DoFieldExchange` メンバー関数をオーバーライドします。  
  
 レコード フィールド エクスチェンジ関数は、フレームワークが `DoFieldExchange` または `DoBulkFieldExchange` を呼び出すたびにデータを転送します。 それぞれの関数が特定のデータ型を転送します。  
  
 これらの関数の使い方の詳細については、「[レコード フィールド エクスチェンジ: RFX のしくみ \(ODBC\)](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。 バルク行フェッチの詳細については、「[レコードセット: バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 動的にバインドするデータの列では、RFX 関数または DFX 関数を手動で呼び出すこともできます。詳細については、「[レコードセット: データ列を動的に結びつける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。 また、独自のカスタム RFX ルーチンまたは DFX ルーチンを記述することもできます。詳細については、テクニカル ノート [43](../Topic/TN043:%20RFX%20Routines.md) \(ODBC の場合\) およびテクニカル ノート [53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) \(DAO の場合\) を参照してください。  
  
 `DoFieldExchange` 関数と `DoBulkFieldExchange` 関数で使用する RFX 関数とバルク RFX 関数の例については、「[RFX\_Text](../Topic/RFX_Text.md)」と「[RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md)」を参照してください。 DFX 関数は RFX 関数によく似ています。  
  
### RFX 関数 \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary](../Topic/RFX_Binary.md)|[CByteArray](../../mfc/reference/cbytearray-class.md) 型のバイト配列を転送します。|  
|[RFX\_Bool](../Topic/RFX_Bool.md)|ブール型のデータを転送します。|  
|[RFX\_Byte](../Topic/RFX_Byte.md)|シングル バイトのデータを転送します。|  
|[RFX\_Date](../Topic/RFX_Date.md)|[CTime](../Topic/CTime%20Class.md) または **TIMESTAMP\_STRUCT** を使用して時刻と日付のデータを転送します。|  
|[RFX\_Double](../Topic/RFX_Double.md)|倍精度浮動小数点型のデータを転送します。|  
|[RFX\_Int](../Topic/RFX_Int.md)|整数型のデータを転送します。|  
|[RFX\_Long](../Topic/RFX_Long.md)|長整数型のデータを転送します。|  
|[RFX\_LongBinary](../Topic/RFX_LongBinary.md)|[CLongBinary](../../mfc/reference/clongbinary-class.md) クラスのオブジェクトを使用して、バイナリ ラージ オブジェクト \(BLOB\) データを転送します。|  
|[RFX\_Single](../Topic/RFX_Single.md)|浮動小数点型のデータを転送します。|  
|[RFX\_Text](../Topic/RFX_Text.md)|文字列型のデータを転送します。|  
  
### バルク RFX 関数 \(ODBC\)  
  
|||  
|-|-|  
|[RFX\_Binary\_Bulk](../Topic/RFX_Binary_Bulk.md)|バイト データの配列を転送します。|  
|[RFX\_Bool\_Bulk](../Topic/RFX_Bool_Bulk.md)|ブール型のデータの配列を転送します。|  
|[RFX\_Byte\_Bulk](../Topic/RFX_Byte_Bulk.md)|シングル バイトの配列を転送します。|  
|[RFX\_Date\_Bulk](../Topic/RFX_Date_Bulk.md)|**TIMESTAMP\_STRUCT** 型のデータの配列を転送します。|  
|[RFX\_Double\_Bulk](../Topic/RFX_Double_Bulk.md)|倍精度浮動小数点型のデータの配列を転送します。|  
|[RFX\_Int\_Bulk](../Topic/RFX_Int_Bulk.md)|整数型のデータの配列を転送します。|  
|[RFX\_Long\_Bulk](../Topic/RFX_Long_Bulk.md)|長整数型のデータの配列を転送します。|  
|[RFX\_Single\_Bulk](../Topic/RFX_Single_Bulk.md)|浮動小数点型のデータの配列を転送します。|  
|[RFX\_Text\_Bulk](../Topic/RFX_Text_Bulk.md)|**LPSTR** 型のデータの配列を転送します。|  
  
### DFX 関数 \(DAO\)  
  
|||  
|-|-|  
|[DFX\_Binary](../Topic/DFX_Binary.md)|[CByteArray](../../mfc/reference/cbytearray-class.md) 型のバイト配列を転送します。|  
|[DFX\_Bool](../Topic/DFX_Bool.md)|ブール型のデータを転送します。|  
|[DFX\_Byte](../Topic/DFX_Byte.md)|シングル バイトのデータを転送します。|  
|[DFX\_Currency](../Topic/DFX_Currency.md)|[COleCurrency](../Topic/COleCurrency%20Class.md) 型の通貨データを転送します。|  
|[DFX\_DateTime](../Topic/DFX_DateTime.md)|[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) 型の時刻と日付データを転送します。|  
|[DFX\_Double](../Topic/DFX_Double.md)|倍精度浮動小数点型のデータを転送します。|  
|[DFX\_Long](../Topic/DFX_Long.md)|長整数型のデータを転送します。|  
|[DFX\_LongBinary](../Topic/DFX_LongBinary.md)|`CLongBinary` クラスのオブジェクトを使用して、バイナリ ラージ オブジェクト \(BLOB\) データを転送します。 DAO の場合は、代わりに [DFX\_Binary](../Topic/DFX_Binary.md) を使用することをお勧めします。|  
|[DFX\_Short](../Topic/DFX_Short.md)|短整数型のデータを転送します。|  
|[DFX\_Single](../Topic/DFX_Single.md)|浮動小数点型のデータを転送します。|  
|[DFX\_Text](../Topic/DFX_Text.md)|文字列型のデータを転送します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)   
 [CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)   
 [CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)