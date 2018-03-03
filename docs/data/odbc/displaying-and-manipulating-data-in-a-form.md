---
title: "表示とフォームでのデータの操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- forms [C++], displaying data
- displaying data [C++], forms
- ODBC [C++], forms
- record views [C++], displaying data
- data [MFC]
- data [MFC], displaying in a form
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1a7960780f1f83833e25c9a094a36314a299a042
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="displaying-and-manipulating-data-in-a-form"></a>フォームでのデータの表示と操作
多くのデータ アクセス アプリケーションは、データを選択し、フォームのフィールドに表示します。 データベース クラス[CRecordView](../../mfc/reference/crecordview-class.md)できます、 [CFormView](../../mfc/reference/cformview-class.md)レコード セット オブジェクトに直接接続されているオブジェクト。 レコード ビューを使用して[ダイアログ データ エクス (チェンジ DDX)](../../mfc/dialog-data-exchange-and-validation.md)レコード セットから現在のレコードのフィールドの値をフォーム上のコントロールに移動して更新された情報をレコード セットに移動します。 さらに、レコード セットは、データ ソースでそのフィールドのデータ メンバーと、テーブル内の対応する列の間でデータを移動するのにレコード フィールド エクス (チェンジ RFX) を使用します。  
  
 MFC アプリケーション ウィザードを使用することができますか**クラスの追加**(」の説明に従って[MFC ODBC コンシューマーの追加](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) を組み合わせて表示クラスとその関連するレコード セット クラスを作成します。  
  
 レコード ビューと、レコード セットは、ドキュメントを閉じるときに破棄されます。 レコード ビューの詳細については、次を参照してください。[レコード ビュー](../../data/record-views-mfc-data-access.md)です。 RFX の詳細については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../../data/odbc/record-field-exchange-rfx.md)です。  
  
## <a name="see-also"></a>参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)