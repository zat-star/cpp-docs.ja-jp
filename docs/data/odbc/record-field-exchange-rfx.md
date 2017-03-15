---
title: "レコード フィールド エクスチェンジ (RFX) | Microsoft Docs"
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
  - "データ [MFC]"
  - "データ [MFC], 移動 (ソースとレコードセット間の)"
  - "データベース クラス [C++], RFX"
  - "ODBC [C++], RFX"
  - "RFX (ODBC) [C++]"
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# レコード フィールド エクスチェンジ (RFX)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC ODBC データベース クラスは、データ ソースと[レコードセット](../../data/odbc/recordset-odbc.md) オブジェクトの間でデータを自動的にやり取りできます。  [CRecordset](../Topic/CRecordset%20Class.md) から派生したクラスでバルク行フェッチを使用しない場合、データはレコード フィールド エクスチェンジ \(RFX\) 機構を通じて転送されます。  
  
> [!NOTE]
>  `CRecordset` の派生クラスにバルク行フェッチが実装されている場合、フレームワークでは、バルク レコード フィールド エクスチェンジ \(Bulk RFX: Bulk Record Field Exchange\) 機構を使用してデータを転送します。  詳細については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 RFX は、ダイアログ データ エクスチェンジ \(DDX: Dialog Data Exchange\) に似た機構です。  データ ソースとレコードセットのフィールド データ メンバー間でデータをやり取りするには、レコードセットの関数 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) を何度も呼び出して、フレームワークと [ODBC](../../data/odbc/odbc-basics.md) の間で大量のデータをやり取りする必要があります。  RFX を利用すると、型の一貫性が保証され、**::SQLBindCol** などの ODBC 関数の呼び出しが自動化されます。  DDX の詳細については、「[ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../../mfc/dialog-data-exchange-and-validation.md)」を参照してください。  
  
 これらの機能は、RFX の存在を意識せずに利用できます。  MFC のアプリケーション ウィザードまたは クラスの追加 を使って宣言したレコードセット クラス \(手順については「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照\) には、RFX が自動的に組み込まれます。  各レコードセット クラスの派生元は、フレームワークが提供する基本クラス `CRecordset` です。  MFC のアプリケーション ウィザードでは、初期レコードセット クラスを作成できます。  クラスの追加 では、必要に応じて、その他のレコードセット クラスを追加できます。  詳細については、「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照してください。  
  
 ただし、次の 3 つの処理を行う場合は、RFX コードを手動で追加する必要があります。  
  
-   パラメーター化されたクエリを使用する場合。  詳細については、「[レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。  
  
-   レコードセット オブジェクトを使って複数のテーブルの列を結合する場合。  詳細については、「[レコードセット : 結合 \(ODBC\)](../Topic/Recordset:%20Performing%20a%20Join%20\(ODBC\).md)」を参照してください。  
  
-   データ列を動的に結び付ける場合。  この方法よりもパラメーターを用いた方法の方が一般的です。  詳細については、「[レコードセット : データ列を動的に結び付ける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。  
  
 RFX の詳細については、「[レコード フィールド エクスチェンジ : RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)」を参照してください。  
  
 レコードセット オブジェクトの使用方法の詳細については、次のトピックを参照してください。  
  
-   [レコード フィールド エクスチェンジ : RFX の使い方](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [レコード フィールド エクスチェンジ : RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [レコード フィールド エクスチェンジ : RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## 参照  
 [ODBC \(Open Database Connectivity\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)   
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [MFC ODBC コンシューマー](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [\[データベース サポート\] \(MFC アプリケーション ウィザード\)](../Topic/Database%20Support,%20MFC%20Application%20Wizard.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)