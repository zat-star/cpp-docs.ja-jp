---
title: "レコードの機能表示クラス (MFC データ アクセス) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d1a30742a538d941220cf099c33445089c9a907c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>レコード ビュー クラスの機能 (MFC データ アクセス)
クラスとフォーム ベースのデータ アクセス プログラミングを行うことができます[CFormView](../mfc/reference/cformview-class.md)が[CRecordView](../mfc/reference/crecordview-class.md)向上から派生するクラスでは、通常、します。 加え、`CFormView`機能、 `CRecordView`:  
  
-   フォーム コントロールと関連するレコード セット オブジェクトの間のダイアログ データ エクス (チェンジ DDX) を提供します。  
  
-   関連するレコード セット オブジェクト内のレコード間を移動するための Move First、Move Next、Move Previous、および Move Last のコマンドを処理します。  
  
-   更新プログラムは、ユーザーが別のレコードに移動すると、現在のレコードに変更されます。  
  
 ナビゲーションの詳細については、次を参照してください。[レコード ビュー: レコード ビュー内のナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)です。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビュー (MFC データ アクセス)](../data/record-views-mfc-data-access.md)   
 [ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)