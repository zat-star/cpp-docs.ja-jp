---
title: "ヘッダー コントロールでのイメージ リストの使い方 | Microsoft Docs"
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
  - "CHeaderCtrl クラス, イメージ リスト"
  - "ヘッダー コントロール, イメージ リスト"
  - "イメージ リスト [C++], ヘッダー コントロール"
ms.assetid: d5e9b310-6278-406c-909c-eefa09549a47
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘッダー コントロールでのイメージ リストの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ヘッダー項目にヘッダー項目内でイメージを表示できます。  関連するイメージ リストに格納されているイメージは 16 × 16 ピクセルで、リスト ビュー コントロールで使用されるアイコン イメージと同じ性質を持っています。  この動作を正常に実装するには、まずイメージ リストを作成し、初期化しなければ、ヘッダー コントロールでリストを関連付け、イメージを表示するヘッダー項目の属性を変更します。  
  
 次の手順では、ヘッダー コントロール \(`m_pHdrCtrl`\) へのポインター、ポインターを使用して、イメージ リスト \(`m_pHdrImages`\) に詳細を示します。  
  
### 項目ヘッダーのイメージを表示します。  
  
1.  生成されたポインターを格納する [CImageList](../Topic/CImageList%20Class.md) のコンストラクターを使用して新しいイメージ リストを設定する \(または、既存のイメージ リスト オブジェクトを使用\) 構築します。  
  
2.  [CImageList::Create](../Topic/CImageList::Create.md)を呼び出して新しいイメージ リスト オブジェクトを初期化してください。  次のコードは、この呼び出しの 1 例です。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#15](../mfc/codesnippet/CPP/using-image-lists-with-header-controls_1.cpp)]  
  
3.  各ヘッダー項目のイメージを追加します。  次のコードは、2 種類の定義済みのイメージを追加します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#16](../mfc/codesnippet/CPP/using-image-lists-with-header-controls_2.cpp)]  
  
4.  [CHeaderCtrl::SetImageList](../Topic/CHeaderCtrl::SetImageList.md)を呼び出してヘッダー イメージ リストをコントロールに関連付けます。  
  
5.  関連付けられたイメージ リスト内のイメージを表示するヘッダー項目を変更します。  次の例は、最初の項目ヘッダーに、最初のイメージを、`m_phdrImages`から `m_pHdrCtrl`割り当てます。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#17](../mfc/codesnippet/CPP/using-image-lists-with-header-controls_3.cpp)]  
  
 使用するパラメーター値の詳細については、適切な [CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)を参照してください。  
  
> [!NOTE]
>  同じイメージ リストを使用して、複数のコントロールを配置することもできます。  たとえば、標準リスト ビュー コントロールでは、リスト ビュー コントロールの小さいアイコン ビュー、およびリスト ビュー コントロールのヘッダー項目の両方で使用される \(16 x 16 ピクセルのイメージ\) のイメージ リストを指定できます。  
  
## 参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)