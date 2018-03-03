---
title: "ダイアログ ボックスの破棄 |Microsoft ドキュメント"
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
- dialog boxes [MFC], deleting
- destruction, dialog box
- dialog boxes [MFC], destroying
- dialog boxes [MFC], removing
- modeless dialog boxes [MFC], destroying
- MFC dialog boxes [MFC], destroying
- modal dialog boxes [MFC], destroying
ms.assetid: dabceee7-3639-4d85-bf34-73515441b3d0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0b1b6c94c4c7efe3bc3300d6c8c5c34fbe890fb4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-the-dialog-box"></a>ダイアログ ボックスの破棄
モーダル ダイアログ ボックスは通常、スタック フレーム上に作成し、それを作成した関数が終了すると破棄します。 ダイアログ オブジェクトのデストラクターは、オブジェクトがスコープ外に出るときに呼び出されます。  
  
 モードレス ダイアログ ボックスが通常作成され、親ビューまたはフレーム ウィンドウが所有する、アプリケーションのメイン フレーム ウィンドウまたはドキュメント フレーム ウィンドウです。 既定値[OnClose](../mfc/reference/cwnd-class.md#onclose)ハンドラーの呼び出し[DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)、ダイアログ ボックス ウィンドウを破棄します。 オーバーライドする場合は、ダイアログ ボックスがスタンドアロン、またはその他の特殊な所有権セマンティクスなしポインターの使用であり、 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy) C++ ダイアログ オブジェクトを破棄します。 オーバーライドする必要がありますも[OnCancel](../mfc/reference/cdialog-class.md#oncancel)を呼び出すと`DestroyWindow`から内にします。 それ以外の場合は、必要でなくなったときに ダイアログ ボックスのオーナーが C++ オブジェクトを破棄する必要があります。  
  
## <a name="see-also"></a>参照  
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

