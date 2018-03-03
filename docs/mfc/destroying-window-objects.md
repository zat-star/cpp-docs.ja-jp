---
title: "ウィンドウ オブジェクトの破棄 |Microsoft ドキュメント"
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
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e7b8b2cf605e0f53418755b65151fd9eb2cff5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="destroying-window-objects"></a>ウィンドウ オブジェクトの破棄
注意が必要に子 windows のウィンドウで、ユーザーが終了すると、C++ ウィンドウ オブジェクトを破棄します。 これらのオブジェクトが破棄されない場合、アプリケーションはメモリを復元できません。 さいわい、フレームワークは、フレーム ウィンドウ、ビュー、およびダイアログ ボックスの作成とウィンドウの破棄を管理します。 その他のウィンドウを作成する場合を破棄します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)  
  
-   [割り当てとウィンドウのメモリを解放します。](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Cwnd と hwnd の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
-   [一般的なウィンドウ作成順序](../mfc/general-window-creation-sequence.md)  
  
-   [フレーム ウィンドウの破棄](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>参照  
 [Window オブジェクト](../mfc/window-objects.md)

