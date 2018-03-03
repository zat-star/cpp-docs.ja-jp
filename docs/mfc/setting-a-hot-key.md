---
title: "ホット キーの設定 |Microsoft ドキュメント"
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
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9cd52fca8415196fc1393cc49fe7830f6ca2cfd1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="setting-a-hot-key"></a>ホット キーの設定
アプリケーションは、ホット キーによって提供される情報を使用して ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) 2 つの方法のいずれかで制御します。  
  
-   送信することによって、子ウィンドウ以外のウィンドウをアクティブ化するためのグローバル ホット キーを設定、 [WM_SETHOTKEY](http://msdn.microsoft.com/library/windows/desktop/ms646284)メッセージをウィンドウをアクティブ化します。  
  
-   Windows の関数を呼び出すことによって、スレッド固有のホット キーを設定[RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309)です。  
  
## <a name="see-also"></a>参照  
 [CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

