---
title: "モードレス ダイアログ ボックスの作成 |Microsoft ドキュメント"
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
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0549f898a076b140e7b5bed23c1c1e8c60d6adba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="creating-modeless-dialog-boxes"></a>モードレス ダイアログ ボックスの作成
モードレス ダイアログ ボックスのダイアログ クラスに、独自のパブリック コンス トラクターを提供する必要があります。 モードレス ダイアログ ボックスを作成する、パブリック コンス トラクターを呼び出すし、ダイアログ オブジェクトを呼び出す[作成](../mfc/reference/cdialog-class.md#create)ダイアログ リソースを読み込むためのメンバー関数。 呼び出すことができます**作成**中またはコンス トラクターの呼び出し後です。 ダイアログ リソースに、プロパティが設定されている場合**WS_VISIBLE**、ダイアログ ボックスがすぐに表示されます。 場合は、呼び出す必要があります、 [ShowWindow](../mfc/reference/cwnd-class.md#showwindow)メンバー関数。  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

