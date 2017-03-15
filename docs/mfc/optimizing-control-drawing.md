---
title: "コントロールの描画の最適化 | Microsoft Docs"
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
  - "MFC ActiveX コントロール, 最適化"
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# コントロールの描画の最適化
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナーが指定されたデバイス コンテキストに描画するようにコントロールに指示するとデバイス コンテキストには、GDI オブジェクト \(ペン、ブラシやフォントなど\) を選択し、描画操作の実行、および前の GDI オブジェクトを復元します。  コンテナーが描画に複数のコントロールを同じデバイス コンテキストが発生した場合は、各コントロールに必要な GDI オブジェクトを選択すると、時間をコントロールが、選択したオブジェクトを復元して保存できます。  すべてのコントロールは、描画、コンテナーは自動的に、元のオブジェクトを復元できます。  
  
 コンテナー サポートが、この方法は、コントロール [COleControl::IsOptimizedDraw](../Topic/COleControl::IsOptimizedDraw.md) のメンバー関数を呼び出すことができるかどうかを確認する。  この関数の戻り値 **TRUE**コントロールが、選択したオブジェクトを復元することで既定の手順を省略できます。  
  
 `OnDraw` の次の \(特に\) 関数があるコントロールを検討する:  
  
 [!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/CPP/optimizing-control-drawing_1.cpp)]  
  
 この例のペンとブラシを意味するローカル変数 \(`OnDraw` 関数が終了すると、スコープの外に出たときにデストラクターを呼び出すことができます。  デストラクターは、対応する GDI オブジェクトを削除します。  ただし、これらを使用 `OnDraw`から戻るときにデバイス コンテキストに選択する場合は削除しないでください。  
  
 `OnDraw` が終了したら [CPen](../Topic/CPen%20Class.md) と [CBrush](../mfc/reference/cbrush-class.md) オブジェクトを格納し、ローカル変数ではなく、メンバー変数で破棄されるのを防ぐには、  コントロールのクラス宣言では、2 種類の新しいメンバー変数の宣言を追加する:  
  
 [!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/CPP/optimizing-control-drawing_2.h)]  
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/CPP/optimizing-control-drawing_3.h)]  
  
 次に、`OnDraw` 関数は次のように書き換えることができます。:  
  
 [!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/CPP/optimizing-control-drawing_4.cpp)]  
  
 この方法は `OnDraw` が呼び出されたときにペンとブラシの作成を回避できます。  速度が向上は追加インスタンス データを保持する損なわれます。  
  
 前景色または BackColor プロパティの変更、ペンまたはブラシを再作成する必要がある場合。  これを行うには、[OnForeColorChanged](../Topic/COleControl::OnForeColorChanged.md) と [OnBackColorChanged](../Topic/COleControl::OnBackColorChanged.md) のメンバー関数をオーバーライドする:  
  
 [!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/CPP/optimizing-control-drawing_5.cpp)]  
  
 次のように、最後に `SelectObject` の不要な呼び出しを削除するには、`OnDraw` を変更する:  
  
 [!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/CPP/optimizing-control-drawing_6.cpp)]  
  
## 参照  
 [MFC ActiveX コントロール : 最適化](../mfc/mfc-activex-controls-optimization.md)   
 [COleControl クラス](../mfc/reference/colecontrol-class.md)   
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX コントロール ウィザード](../mfc/reference/mfc-activex-control-wizard.md)   
 [MFC ActiveX コントロール : ActiveX コントロールの描画](../mfc/mfc-activex-controls-painting-an-activex-control.md)