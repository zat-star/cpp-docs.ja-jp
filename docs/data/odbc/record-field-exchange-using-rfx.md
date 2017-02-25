---
title: "レコード フィールド エクスチェンジ: RFX の使い方 | Microsoft Docs"
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
  - "RFX (ODBC), 実装"
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# レコード フィールド エクスチェンジ: RFX の使い方
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、フレームワークの動作に関連した RFX の使用方法について説明します。  
  
> [!NOTE]
>  このトピックの内容は、バルク行フェッチが実装されていない [CRecordset](../Topic/CRecordset%20Class.md) の派生クラスを対象にしています。  バルク行フェッチを使用している場合は、バルク レコード フィールド エクスチェンジ \(Bulk RFX: Bulk Record Field Exchange\) が実装されています。  Bulk RFX と RFX は似ています。  両者の差異については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 関連情報については、次のトピックを参照してください。  
  
-   「[レコード フィールド エクスチェンジ : ウィザード コードの操作](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md)」では、RFX の概要、MFC のアプリケーション ウィザードと クラスの追加 \(「[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)」を参照\) が RFX をサポートするために生成するコードの説明、およびウィザードのコードを更新する方法を説明します。  
  
-   「[レコード フィールド エクスチェンジ : RFX 関数の使い方](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)」では、オーバーライド関数 `DoFieldExchange` の中から RFX 関数を呼び出す方法について説明します。  
  
 次の表に、フレームワークが行う処理とプログラマが行う作業を示します。  
  
### RFX の使い方とフレームワークの動作  
  
|プログラマの役割|フレームワークの役割|  
|--------------|----------------|  
|ウィザードを使って、レコードセット クラスを宣言します。  フィールド データ メンバーの名前とデータ型を指定します。|ウィザードは、`CRecordset` クラスを派生し、オーバーライド関数 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) を作成します。オーバーライド関数 DoFieldExchange の中で、フィールド データ メンバーごとに RFX 関数が呼び出されます。|  
|\(省略可能\) 必要なパラメーター データ メンバーをクラスに手動で追加します。  パラメーター データ メンバーごとに、RFX 関数呼び出しを手作業で `DoFieldExchange` に追加します。パラメーターのグループに対しては、[CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) への呼び出しを追加し、パラメーターの総数を [m\_nParams](../Topic/CRecordset::m_nParams.md) で指定します。  「[レコードセット : パラメーターを利用したレコードセット \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)」を参照してください。||  
|\(省略可能\) テーブル列とフィールド データ メンバーを直接 \(ウィザードを使わずに\) 結び付けて、  [m\_nFields](../Topic/CRecordset::m_nFields.md) の値を増やします。  「[レコードセット : データ列を動的に結び付ける方法 \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。||  
|レコードセット クラスのオブジェクトを構築します。  パラメーター データ メンバーがあるときは、オブジェクトを使用する前にその値を設定します。|処理を効率化するため、フレームワークでは ODBC を使ってあらかじめパラメーターをデータ ソースに結び付けておきます。  パラメーターの値が与えられると、フレームワークはその値をデータ ソースに渡します。  並べ替え\/フィルター文字列を変更しない限り、クエリの再実行時にはパラメーター値だけが送られます。|  
|[CRecordset::Open](../Topic/CRecordset::Open.md) を使ってレコードセット オブジェクトを開きます。|レコードセットのクエリを実行し、列をレコードセットのフィールド データ メンバーに結び付けます。`DoFieldExchange` を呼び出して、最初に選択されたレコードとレコードセットのフィールド データ メンバー間でデータを交換します。|  
|[CRecordset::Move](../Topic/CRecordset::Move.md)、メニュー コマンドまたはツール バー コマンドを使ってレコードセットをスクロールします。|`DoFieldExchange` を呼び出して、新しい現在のレコードから、フィールド データ メンバーにデータを転送します。|  
|レコードを追加、更新、または削除します。|`DoFieldExchange` を呼び出して、データ ソースへデータを転送します。|  
  
## 参照  
 [レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [レコード フィールド エクスチェンジ: RFX の動作のしくみ](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [レコードセット: 集計値の計算 \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)   
 [CFieldExchange クラス](../../mfc/reference/cfieldexchange-class.md)   
 [マクロ、グローバル関数、およびグローバル変数](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)