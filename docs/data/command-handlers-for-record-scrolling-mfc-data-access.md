---
title: "レコード スクロール (MFC データ アクセス) のハンドラーをコマンド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dc91c19661bb8902ff15919d89e745e9966c72c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>レコード スクロール コマンドに対するコマンド ハンドラー (MFC データ アクセス)
[CRecordView](../mfc/reference/crecordview-class.md)クラスには、既定のコマンドを次の標準コマンドの処理が用意されています。  
  
-   **ID_RECORD_MOVE_FIRST**  
  
-   **ID_RECORD_MOVE_LAST**  
  
-   **ID_RECORD_MOVE_NEXT**  
  
-   **ID_RECORD_MOVE_PREV**  
  
 `OnMove`メンバー関数は既定のコマンド レコード間を移動するすべての 4 つのコマンドの処理を提供します。 これらのコマンドが発行されると、RFX (または DFX) によってレコードセットのフィールドに新しいレコードが読み込まれ、DDX によってレコード フォームのコントロールに値が移動されます。 RFX については、次を参照してください。[レコード フィールド エクス チェンジ (RFX)](../data/odbc/record-field-exchange-rfx.md)です。  
  
> [!NOTE]
>  標準的なレコード移動コマンドに関連付けられているユーザー インターフェイス オブジェクトには、必ずこれらの標準コマンド ID を使用してください。  
  
## <a name="see-also"></a>関連項目  
 [レコード ビューのナビゲーションをサポートします。](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)