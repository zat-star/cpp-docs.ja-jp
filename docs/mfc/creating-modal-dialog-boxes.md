---
title: "モーダル ダイアログ ボックスの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 815db891514eb03169dac2ad29e50469d74dcfee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-modal-dialog-boxes"></a>モーダル ダイアログ ボックスの作成
モーダル ダイアログ ボックスを作成するで宣言されているパブリック コンス トラクターを次の 2 つのいずれかを呼び出す[CDialog](../mfc/reference/cdialog-class.md)です。 次に、呼び出すダイアログ オブジェクトの[DoModal](../mfc/reference/cdialog-class.md#domodal) ダイアログ ボックスを表示し、ユーザーが [ok] を選択するまで対話操作を管理またはキャンセルするメンバー関数。 この管理によって`DoModal`はモーダル ダイアログ ボックスは、します。 モーダル ダイアログ ボックスの`DoModal`ダイアログ リソースを読み込みます。  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

