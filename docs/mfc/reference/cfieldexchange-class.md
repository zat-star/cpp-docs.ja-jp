---
title: "CFieldExchange クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFieldExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFieldExchange クラス"
  - "データ型 [C++], custom"
  - "FieldType 列挙型"
  - "FieldType 列挙型, CFieldExchange"
  - "FieldType 列挙型"
  - "RFX (レコード フィールド エクスチェンジ) [C++]"
  - "RFX (レコード フィールド エクスチェンジ) [C++], クラス"
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CFieldExchange クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース クラスで使うレコード フィールド エクスチェンジ \(RFX\) ルーチンとバルク レコード フィールド エクスチェンジ \(Bulk RFX\) ルーチンをサポートします。  
  
## 構文  
  
```  
  
class CFieldExchange  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFieldExchange::IsFieldType](../Topic/CFieldExchange::IsFieldType.md)|現在の操作が更新されるフィールドの種類に適したの場合はを返します。|  
|[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md)|RFX にすべての後続の呼び出しによって表されるレコードセット データ メンバーの型である列またはパラメーター—機能します `SetFieldType`に次の呼び出しまで指定します。|  
  
## 解説  
 `CFieldExchange` には、基本クラスはありません。  
  
 カスタム データ型のデータ エクスチェンジ ルーチンを作成する場合またはバルク行フェッチを実装している場合は、このクラスを使用してください; それ以外の場合は、このクラスを直接使用しません。  レコードセット オブジェクトのフィールド データ メンバーとデータ ソースの現在のレコードの対応するフィールド間の RFX や Bulk RFX データを交換します。  
  
> [!NOTE]
>  \(DAO\) ではなく、並べ替える Data Access Objects を使用すると、ODBC \(Open Database Connectivity\) クラスは、クラス [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) を代わりに使用します。  詳細については、" " [:概要データベース プログラミング](../../data/data-access-programming-mfc-atl.md)を参照してください。  
  
 `CFieldExchange` のオブジェクトは、レコード フィールド エクスチェンジのまたはバルク レコード フィールド エクスチェンジで発生するために必要なコンテキスト情報を提供します。  `CFieldExchange` のオブジェクトは、現在のレコードのフィールドの結合のパラメーター、フィールド データ メンバーと設定のさまざまなフラグが含まれる多数の操作をサポートしています。  RFX や Bulk RFX 処理は `CFieldExchange`で `enum`**FieldType** によって定義される型のレコードセット クラスのデータ メンバーで実行されます。  **FieldType** の値は次のとおりです:  
  
-   フィールド データ メンバーの**CFieldExchange::outputColumn**。  
  
-   入力パラメーター データ メンバーの**CFieldExchange::inputParam** か **CFieldExchange::param**。  
  
-   出力パラメーター データ メンバーの**CFieldExchange::outputParam**。  
  
-   入出力パラメーター データ メンバーごとの**CFieldExchange::inoutParam**。  
  
 クラスのメンバー関数とデータ メンバーのほとんどは、独自のカスタム RFX のルーチンを記述するために使用されます。  `SetFieldType` を頻繁に使用します。  詳細については、" " [レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md) と [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)を参照してください。  バルク行フェッチについては、" " [レコードセット: フェッチ サイズのレコードを \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)を参照してください。  RFX や Bulk RFX のグローバル関数の詳細については、この参照の MFC マクロとグローバル"の [フィールド エクスチェンジ関数を記録します。](../../mfc/reference/record-field-exchange-functions.md) を参照してください。  
  
## 継承階層  
 `CFieldExchange`  
  
## 必要条件  
 **Header:** afxdb.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)