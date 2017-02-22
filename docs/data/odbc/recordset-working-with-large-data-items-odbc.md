---
title: "レコードセット: 大量のデータの処理 (ODBC) | Microsoft Docs"
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
  - "バイナリ ラージ オブジェクト"
  - "BLOB (バイナリ ラージ オブジェクト), レコードセット"
  - "CLongBinary クラス, 使用 (レコードセットで)"
  - "ODBC レコードセット, バイナリ ラージ オブジェクト"
  - "レコードセット, バイナリ ラージ オブジェクト"
ms.assetid: 3e80b5a8-b6e7-43c6-a816-e54befc513a3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# レコードセット: 大量のデータの処理 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスと MFC DAO クラスの両方に該当します。  
  
> [!NOTE]
>  MFC DAO クラスを使用する場合、大量のデータ項目を管理するには、[CLongBinary](../../mfc/reference/clongbinary-class.md) クラスではなく [CByteArray](../../mfc/reference/cbytearray-class.md) クラスを使用します。  バルク行フェッチを実装した MFC ODBC クラスを使う場合は、`CByteArray` を使わずに `CLongBinary` を使います。  バルク行フェッチの詳細については、「[レコードセット : バルク行フェッチ \(ODBC\)](../Topic/Recordset:%20Fetching%20Records%20in%20Bulk%20\(ODBC\).md)」を参照してください。  
  
 データベースには、ビットマップ \(顔写真や地図、製品写真、OLE オブジェクトなど\) などの大きなデータを格納することがあります。  このようなデータは、以下の特徴があるため、バイナリ ラージ オブジェクト \(BLOB: Binary Large Object\) と呼ばれます。  
  
-   フィールド値が大きい。  
  
-   数値データなどの単純なデータ型とは異なり、あらかじめサイズを決定できない。  
  
-   プログラム上、定型処理を行いにくい。  
  
 このトピックでは、バイナリ ラージ オブジェクトを扱うデータベース クラスを作成する方法について説明します。  
  
##  <a name="_core_managing_large_objects"></a> 大型オブジェクトの管理  
 レコードセットには、バイナリ ラージ オブジェクトの管理作業を軽減する方法が 2 つあります。  [CByteArray](../../mfc/reference/cbytearray-class.md) クラスを使う方法と、[CLongBinary](../../mfc/reference/clongbinary-class.md) クラスを使う方法です。  通常、バイナリ ラージ オブジェクトを管理するには `CByteArray` の方を優先して使います。  
  
 `CByteArray` は、`CLongBinary` と比べてオーバーヘッドの面で劣りますが、機能的に優れています \(「[CByteArray クラス](#_core_the_cbytearray_class)」を参照\)。  `CLongBinary` については、「[CLongBinary クラス](#_core_the_clongbinary_class)」で簡単に説明します。  
  
 `CByteArray` を使って大量のデータを処理する方法の詳細については、「[テクニカル ノート 45: MFC\/データベースの Long Varchar\/Varbinary 型のサポート](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)」を参照してください。  
  
##  <a name="_core_the_cbytearray_class"></a> CByteArray クラス  
 `CByteArray` は、MFC コレクション クラスの 1 つです。  `CByteArray` オブジェクトは、バイトの動的な配列 \(必要に応じて拡張できる配列\) を格納します。  このクラスは、組み込み C\+\+ 配列と同様に、インデックスによる高速なアクセスを提供します。  `CByteArray` オブジェクトは、シリアル化することも、診断用にダンプすることもできます。  このクラスの提供するメンバー関数では、指定されたバイトの取得と設定、バイトの挿入と付加、バイトの個別\/一括除去を行うことができます。  これらの機能によって、バイナリ データを簡単に解析できます。  たとえば、バイナリ オブジェクトが OLE オブジェクトの場合は、ヘッダー バイトを通じて実際のオブジェクトに到達できます。  
  
##  <a name="_core_using_cbytearray_in_recordsets"></a> レコードセットでの CByteArray の使用  
 レコードセットに `CByteArray`型のフィールド データ メンバーを用意すると、[RFX](../../data/odbc/record-field-exchange-rfx.md) によってレコードセットとデータ ソースとの間でオブジェクトをやり取りするための固定ベースを提供できます。プログラムは、この固定ベースを通じてオブジェクト内のデータも操作できます。  RFX は取得したデータを保存するための専用のサイトを必要とし、プログラムはオブジェクトのデータにアクセスするための方法を必要とします。  
  
 `CByteArray` を使って大量のデータを処理する方法の詳細については、「[テクニカル ノート 45: MFC\/データベースの Long Varchar\/Varbinary 型のサポート](../../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md)」を参照してください。  
  
##  <a name="_core_the_clongbinary_class"></a> CLongBinary クラス  
 [CLongBinary](../../mfc/reference/clongbinary-class.md) オブジェクトは、ヒープ上に確保された領域を指す `HGLOBAL` ハンドルを中心に構成されています。  バイナリ ラージ オブジェクトを格納したテーブル列が `CLongBinary` オブジェクトに結び付けられると、RFX は、レコードセットにデータを転送するために `HGLOBAL` ハンドルにメモリを割り当てて、ハンドルをレコードセットの ClongBinary フィールドに保存します。  
  
 これにより、プログラムでは `HGLOBAL` ハンドル `m_hData` を通じてデータを操作できます。  この点において、[CByteArray](../../mfc/reference/cbytearray-class.md) は CLongBinary より機能的に優れています。  
  
> [!CAUTION]
>  CLongBinary オブジェクトは、関数呼び出しのパラメーターとして使用できません。  また、このオブジェクトの中では **::SQLGetData** が使われているため、スナップショットのスクロール速度が低下します。  動的なスキーマ列にアクセスするために直接 **::SQLGetData** を呼び出した場合も、スクロール速度が低下します。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [レコードセット: 集計値の計算 \(ODBC\)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [レコード フィールド エクスチェンジ \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)