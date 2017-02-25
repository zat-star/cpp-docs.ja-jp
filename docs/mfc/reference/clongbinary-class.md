---
title: "CLongBinary クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "BLOB"
  - "CLongBinary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB (バイナリ ラージ オブジェクト)"
  - "BLOB (バイナリ ラージ オブジェクト), CLongBinary クラス"
  - "CLongBinary クラス"
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CLongBinary クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データベース上の大きなバイナリ データ オブジェクト \(BLOB または "バイナリ ラージ オブジェクト" と呼びます\) を使った作業を単純にします。  
  
## 構文  
  
```  
class CLongBinary : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CLongBinary::CLongBinary ](../Topic/CLongBinary::CLongBinary.md)|`CLongBinary` オブジェクトを構築します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CLongBinary::m\_dwDataLength](../Topic/CLongBinary::m_dwDataLength.md)|ハンドルが `m_hData`に格納されているデータ オブジェクトのバイト単位のサイズが含まれています。|  
|[CLongBinary::m\_hData ](../Topic/CLongBinary::m_hData.md)|実際のイメージ オブジェクトに Windows `HGLOBAL` のハンドルが含まれます。|  
  
## 解説  
 たとえば、SQL テーブルのレコードのフィールドは画像を表すビットマップが含まれる場合があります。  `CLongBinary` のオブジェクトは、そのようなオブジェクトを格納およびサイズを追跡します。  
  
> [!NOTE]
>  一般に、これ [DFX\_Binary](../Topic/DFX_Binary.md) 関数とともに [CByteArray](../../mfc/reference/cbytearray-class.md) を使用するより良い方法です。  まだ `CLongBinary`を使用できますが、一般に `CByteArray` は、Win32 の下に、16 ビットの `CByteArray`で発生するサイズに制限がないため、より多くの機能を提供します。  この通知は Data Access Objects \(DAO\)、ODBC \(Open Database Connectivity\) を使用したプログラミングに適用されます。  
  
 `CLongBinary` のオブジェクトを使用するには、レコードセットのクラス型 `CLongBinary` のフィールド データ メンバーを宣言します。  このメンバーは、レコードセットを構築するレコードセット クラスの埋め込みメンバーで構築できます。  `CLongBinary` オブジェクトの構築後、レコード フィールド エクスチェンジ \(RFX\) 機構はレコードに戻るレコードを更新するとデータ ソースおよび格納の現在のレコードのフィールドからデータ オブジェクトを読み込み、  RFX は `m_hData`のデータにバイナリ ラージ オブジェクト \(BLOB のサイズのデータ ソースを割り当てます、のストレージ \( `CLongBinary` のオブジェクトの `m_hData` のデータ メンバー\)、および格納 `HGLOBAL` ハンドルを照会します。  RFX は、`m_dwDataLength` のデータ メンバーにデータ オブジェクトの実際のサイズを格納します。  Windows `HGLOBAL` ハンドルに格納されているデータを処理する、一般にある同じ方法を使用して、`m_hData`を使用してオブジェクト データを使用します。  
  
 自分のレコードセットを破棄するとき、`CLongBinary` の埋め込みオブジェクトも破棄され、デストラクターは `HGLOBAL` のデータのハンドルを解放します。  
  
 大きなオブジェクトの詳細については、`CLongBinary`の使用については、" " [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md) と [レコードセット: 大きなデータ項目 \(ODBC\) を使用](../../data/odbc/recordset-working-with-large-data-items-odbc.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CLongBinary`  
  
## 必要条件  
 **Header:** afxdb\_.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../Topic/CRecordset%20Class.md)