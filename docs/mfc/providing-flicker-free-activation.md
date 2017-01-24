---
title: "ちらつきなしのアクティベーションの提供 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクティベーション [C++], ちらつきなし"
  - "ちらつき, MFC ActiveX コントロール"
  - "MFC ActiveX コントロール [C++], ちらつきなし"
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ちらつきなしのアクティベーションの提供
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールがアクティブでなく、アクティブ状態であると \(ウィンドウなしのアクティベーションを使用しない\)、同じ描画、通常発生するビジュアルのちらつきおよび描画操作を削除できますアクティブでなく、アクティブ状態間の遷移を行う場合。  これを行うには、[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md)によって返されるフラグを設定する **noFlickerActivate** フラグを含めます。  たとえば、次のようになります。  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/CPP/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-flicker-free-activation_3.cpp)]  
  
 このフラグが含まれるコードは自動的にコントロールを MFC ActiveX コントロール ウィザードを作成すると [コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md) ページの **ちらつきなしでアクティブ化\(V\)** オプションを選択すると生成されます。  
  
 ウィンドウなしでアクティブを使用する場合は、この最適化は無効です。  
  
## 参照  
 [MFC ActiveX コントロール : 最適化](../mfc/mfc-activex-controls-optimization.md)