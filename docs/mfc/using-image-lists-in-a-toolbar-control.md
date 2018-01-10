---
title: "ツール バー コントロールでのイメージ リストの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 507f684a0c5c7a923cd5c8e16bc9578b8b68e511
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-image-lists-in-a-toolbar-control"></a>ツール バー コントロールでのイメージ リストの使い方
既定では、ツール バー コントロールのボタンが使用するイメージは、1 つのビットマップとして格納されます。 ただし、一連のイメージ リストのボタンのイメージを保存することもできます。 ツール バー コントロール オブジェクトは、最大 3 つの別々 のイメージ リストを使用できます。  
  
-   イメージ リストは、現在有効になっているツール バー ボタンのイメージを含むを有効になります。  
  
-   イメージ リストは、現在無効になっているツール バー ボタンのイメージを含むを無効になります。  
  
-   イメージ リストは、現在強調表示されているツール バー ボタンのイメージを含むを強調表示されます。 ツールバーを使用する場合のみ、このイメージ リストが使用される、 **TBSTYLE_FLAT**スタイル。  
  
 これらを関連付けるときにこれらのイメージ リストがツール バー コントロールで使用される、`CToolBarCtrl`オブジェクト。 この関連付けを呼び出すことで実現[CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist)、 [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist)、および[SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)です。  
  
 既定では、MFC を使用して、 `CToolBar` MFC アプリケーションのツールバーを実装するクラス。 ただし、`GetToolBarCtrl`埋め込みを取得するメンバー関数を使用できます`CToolBarCtrl`オブジェクト。 呼び出しを行うことができますし、`CToolBarCtrl`返されたオブジェクトを使用してメンバー関数。  
  
 次の例は、有効なを割り当てることでこの方法を示します (`m_ToolBarImages`)] と [無効 (`m_ToolBarDisabledImages`) イメージ リストを`CToolBarCtrl`オブジェクト (`m_ToolBarCtrl`)。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  ツール バー オブジェクトで使用されるイメージ リストは、パーマネント オブジェクトである必要があります。 このため、それらは通常、MFC クラスのデータ メンバーです。この例では、メイン フレーム ウィンドウ クラスです。  
  
 イメージ リストが関連付けられていると、`CToolBarCtrl`オブジェクト、フレームワークは、適切なボタンのイメージを自動的に表示されます。  
  
## <a name="see-also"></a>参照  
 [CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

