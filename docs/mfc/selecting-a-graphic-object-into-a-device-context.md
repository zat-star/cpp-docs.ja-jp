---
title: "グラフィック オブジェクトをデバイス コンテキストに選択する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "デバイス コンテキスト, グラフィック オブジェクト"
  - "デバイス コンテキスト, 選択 (グラフィック オブジェクトを)"
  - "GDI オブジェクト [C++], デバイス コンテキスト"
  - "グラフィック オブジェクト, 選択 (デバイス コンテキストに)"
  - "有効期間, グラフィック オブジェクト"
  - "SelectObject メソッド"
ms.assetid: cf54a330-63ef-421f-83eb-90ec7bd82eef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# グラフィック オブジェクトをデバイス コンテキストに選択する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、ウィンドウのデバイス コンテキストにグラフィック オブジェクトの使用に適用されます。  そこに格納されている既定のオブジェクトの代わりにデバイス コンテキストに [描画オブジェクトを作成します。](../mfc/one-stage-and-two-stage-construction-of-objects.md)で選択するリファクタリングした後:  
  
 [!code-cpp[NVC_MFCDocViewSDI#7](../mfc/codesnippet/CPP/selecting-a-graphic-object-into-a-device-context_1.cpp)]  
  
## グラフィック オブジェクトの有効期間  
 [SelectObject](../Topic/CDC::SelectObject.md) によって返されるグラフィック オブジェクトは「一時」。つまり、クラス `CWinApp` の [OnIdle](../Topic/CWinApp::OnIdle.md) のメンバー関数によってプログラムがアイドル時間を取得したときに削除されます。  一つの関数で返されるコントロールなしで `SelectObject` によって返されるのメイン メッセージ ループにオブジェクトを使用する場合、問題はありません。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md)  
  
-   [グラフィック オブジェクトは、一段と正常な構築式](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [デバイス コンテキスト](../Topic/Device%20Contexts.md)  
  
-   [ビューで描画できます。](../mfc/drawing-in-a-view.md)  
  
## 参照  
 [グラフィック オブジェクト](../mfc/graphic-objects.md)