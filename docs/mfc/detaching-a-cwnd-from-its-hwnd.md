---
title: "Cwnd と hwnd の分離 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CWnd
dev_langs:
- C++
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa24e0e9a0d9ee50a0c5c69e280ea7a727ca38b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd と HWND の分離
オブジェクトを回避する必要がある場合`HWND`リレーションシップを MFC には、別`CWnd`メンバー関数は、[デタッチ](../mfc/reference/cwnd-class.md#detach)Windows のウィンドウから C++ ウィンドウ オブジェクトを切断します。 これは、デストラクターが、オブジェクトが破棄されるときに、Windows のウィンドウを破棄することを防ぎます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [ウィンドウの作成](../mfc/creating-windows.md)  
  
-   [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)  
  
-   [割り当てとウィンドウのメモリを解放します。](../mfc/allocating-and-deallocating-window-memory.md)  
  
## <a name="see-also"></a>参照  
 [Window オブジェクト](../mfc/window-objects.md)

