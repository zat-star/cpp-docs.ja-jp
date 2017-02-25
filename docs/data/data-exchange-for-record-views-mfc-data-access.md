---
title: "レコード ビューのデータ交換 (MFC データ アクセス) | Microsoft Docs"
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
  - "DDX (ダイアログ データ エクスチェンジ), レコード ビュー"
  - "DFX (DAO レコード フィールド エクスチェンジ)"
  - "DFX (DAO レコード フィールド エクスチェンジ), データ交換機構"
  - "DFX (DAO レコード フィールド エクスチェンジ), レコード ビュー"
  - "レコード ビュー, データ交換"
  - "RFX (レコード フィールド エクスチェンジ)"
  - "RFX (レコード フィールド エクスチェンジ), データ交換機構"
  - "RFX (レコード フィールド エクスチェンジ), レコード ビュー"
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# レコード ビューのデータ交換 (MFC データ アクセス)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\[[クラスの追加](../mfc/reference/adding-an-mfc-odbc-consumer.md)\] を使用してレコード ビューのダイアログ テンプレート リソース内のコントロールをレコードセットのフィールドに対応付けると、双方向のデータ交換 \(レコードセットとコントロール間\) がフレームワークで管理されます。  DDX 機構を使用すると、データを双方向で転送するコードを自分で記述する必要がなくなります。  
  
 レコード ビュー用の DDX は次の相手と連携して動作します。  
  
-   `CRecordset` クラスのレコードセットの [RFX](../data/odbc/record-field-exchange-rfx.md) \(ODBC の場合\)  
  
-   `CDaoRecordset` クラスのレコードセットの DFX \(DAO の場合\)  
  
 RFX と DFX は実装こそ異なりますが、インターフェイス レベルではよく似たデータ交換機構です。  DAO のバージョンの DFX は、初期の ODBC バージョンの RFX を基にモデル化されているからです。  RFX の使用方法がわかれば、DFX の使用方法もわかります。  
  
 RFX と DFX は、データ ソースの現在のレコードと、レコード セット オブジェクトのフィールド データ メンバーの間でデータを移動します。  DDX は、フィールド データ メンバーからフォーム内のコントロールにデータを移動します。  このように組み合わせると、フォーム コントロールに初期値が設定され、ユーザーがレコード間を移動したときにも値が設定されます。  更新されたデータをレコードセットに戻し、さらにデータ ソースまで移動することもできます。  
  
 次の図は、レコード ビュー用の DDX と RFX \(または DFX\) の関係を示しています。  
  
 ![ダイアログ データ エクスチェンジ &#40;DDX&#41; とレコード フィールド エクスチェンジ &#40;RFX&#41;](../data/media/vc37xt1.gif "vc37XT1")  
ダイアログ データ エクスチェンジ \(DDX\) とレコード フィールド エクスチェンジ \(RFX\)  
  
 DDX の詳細については、「[ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)」を参照してください。  RFX の詳細については、「[レコード フィールド エクスチェンジ \(RFX\)](../data/odbc/record-field-exchange-rfx.md)」を参照してください。  
  
## 参照  
 [レコード ビュー \(MFC データ アクセス\)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)