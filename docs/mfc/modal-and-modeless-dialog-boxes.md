---
title: "モーダルとモードレスのダイアログ ボックス |Microsoft ドキュメント"
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
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC]
- MFC dialog boxes [MFC], modal
- modal dialog boxes [MFC]
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 982bb8f195c3744246addc18d66bee953914dde4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="modal-and-modeless-dialog-boxes"></a>モーダルとモードレスのダイアログ ボックス
クラスを使用して[CDialog](../mfc/reference/cdialog-class.md)を 2 つの種類のダイアログ ボックスを管理します。  
  
-   *モーダル ダイアログ ボックス*ユーザーがプログラムを続行する前に応答を必要とします。  
  
-   *モードレス ダイアログ ボックス*画面とは、いつでも使用できるように維持するが、他のユーザー アクティビティを許可  
  
 リソースの編集とするダイアログ テンプレートを作成する手順については、モーダルとモードレスのダイアログ ボックスに同じです。  
  
 プログラムのダイアログ ボックスを作成するには、次の手順が必要です。  
  
1.  使用して、[ダイアログ エディター](../windows/dialog-editor.md)をダイアログ ボックスを設計し、そのダイアログ テンプレート リソースを作成します。  
  
2.  ダイアログ クラスを作成します。  
  
3.  接続、[ダイアログ リソースのコントロール メッセージのハンドラーを](../windows/adding-event-handlers-for-dialog-box-controls.md)ダイアログ クラスです。  
  
4.  関連付けられていると、ダイアログ ボックスのコントロールを指定するデータ メンバーを追加[ダイアログ データ エクス チェンジ](../mfc/dialog-data-exchange.md)と[ダイアログ データ バリデーション](../mfc/dialog-data-validation.md)コントロール。  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

