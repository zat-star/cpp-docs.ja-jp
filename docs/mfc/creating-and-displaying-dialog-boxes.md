---
title: "作成して、ダイアログ ボックスを表示する |Microsoft ドキュメント"
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
- opening dialog boxes
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], displaying
ms.assetid: 1c5219ee-8b46-44bc-9708-83705d4f248b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d436301a979dbba2bc4a922f8427f355a398f654
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-displaying-dialog-boxes"></a>ダイアログ ボックスの作成と表示
2 フェーズの操作は、ダイアログ ボックスのオブジェクトを作成します。 最初に、ダイアログのオブジェクトを構築し、ダイアログ ウィンドウを作成します。 モーダルとモードレスのダイアログ ボックスでは、作成し、それらを表示するために使用するプロセスが少し異なります。 次の表は、どのモーダルとモードレスのダイアログ ボックスは通常構築し、表示されます。  
  
### <a name="dialog-creation"></a>ダイアログの作成  
  
|ダイアログの種類|それを作成する方法|  
|-----------------|----------------------|  
|[モードレス](../mfc/creating-modeless-dialog-boxes.md)|構築`CDialog`、まず**作成**メンバー関数。|  
|[モーダル](../mfc/creating-modal-dialog-boxes.md)|構築`CDialog`、まず`DoModal`メンバー関数。|  
  
 、する場合は、作成、ダイアログ ボックスから、[インメモリでダイアログ テンプレート](../mfc/using-a-dialog-template-in-memory.md)構築するダイアログ テンプレート リソースからではなくです。 ただし、高度なトピックでは、します。  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

