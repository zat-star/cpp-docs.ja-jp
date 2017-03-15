---
title: "スライダー コントロールのメンバー関数 | Microsoft Docs"
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
  - "CSliderCtrl クラス, メソッド"
  - "スライダー コントロール, メンバー関数"
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# スライダー コントロールのメンバー関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションでは、スライダー コントロールのメンバー関数を呼び出して、スライダー コントロール \([CSliderCtrl](../mfc/reference/csliderctrl-class.md)\) に関する情報を取得したり、その特性を変更したりできます。  
  
 スライダーの位置 \(つまり、ユーザーが選択した値\) を取得するには、[GetPos](../Topic/CSliderCtrl::GetPos.md) メンバー関数を使用します。  スライダーの位置を設定するには、[SetPos](../Topic/CSliderCtrl::SetPos.md) メンバー関数を使用します。  `VerifyPos` メンバー関数を使用すると、スライダーが最小値と最大値の間にあることをいつでも確認できます。  
  
 スライダー コントロールの範囲は、スライダー コントロールで表すことのできる一連の連続する値です。  ほとんどのアプリケーションでは、最初の作成時に [SetRange](../Topic/CSliderCtrl::SetRange.md) メンバー関数を使用して、スライダー コントロールの範囲を設定します。  スライダー コントロールの作成後に、[SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md) メンバー関数および [SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md) メンバー関数を使用して、範囲を動的に変更することもできます。  範囲を動的に変更できるアプリケーションでは、通常、ユーザーが最後にスライダー コントロールの操作を終了したときの範囲の設定値が取得されます。  これらの設定値を取得するには、[GetRange](../Topic/CSliderCtrl::GetRange.md)、[GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md)、および [GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md) の各メンバー関数を使用します。  
  
 `TBS_AUTOTICKS` スタイルを使用すると、スライダー コントロールの目盛りを自動的に表示できます。  ただし、アプリケーションで目盛りの位置と数を制御する必要がある場合は、複数のメンバー関数を使用できます。  
  
 目盛りの位置を設定するには、[SetTic](../Topic/CSliderCtrl::SetTic.md) メンバー関数を使用します。  [SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md) メンバー関数を使用すると、スライダー コントロールの範囲内に目盛りを一定の間隔で設定できます。  たとえば、アプリケーションでこのメンバー関数を使用すると、1 ～ 100 の範囲に 10 個の目盛りを表示できます。  
  
 目盛りに対応する、範囲内のインデックスを取得するには、[GetTic](../Topic/CSliderCtrl::GetTic.md) メンバー関数を使用します。  [GetTicArray](../Topic/CSliderCtrl::GetTicArray.md) メンバー関数を使用すると、これらのインデックスの配列を取得できます。  クライアント座標の目盛りの位置を取得するには、[GetTicPos](../Topic/CSliderCtrl::GetTicPos.md) メンバー関数を使用します。  [GetNumTics](../Topic/CSliderCtrl::GetNumTics.md) メンバー関数を使用すると、目盛りの数を取得できます。  
  
 [ClearTics](../Topic/CSliderCtrl::ClearTics.md) メンバー関数を使用すると、スライダー コントロールの目盛りをすべて削除できます。  
  
 スライダー コントロールの行サイズによって、アプリケーションが **TB\_LINEDOWN** 通知メッセージまたは **TB\_LINEUP** 通知メッセージを受け取るときにスライダーの移動する距離が決まります。  同様に、用紙サイズによって、**TB\_PAGEDOWN** 通知メッセージおよび **TB\_PAGEUP** 通知メッセージに対する応答が決まります。  アプリケーションでは、[GetLineSize](../Topic/CSliderCtrl::GetLineSize.md)、[SetLineSize](../Topic/CSliderCtrl::SetLineSize.md)、[GetPageSize](../Topic/CSliderCtrl::GetPageSize.md)、および [SetPageSize](../Topic/CSliderCtrl::SetPageSize.md) の各メンバー関数を使用して、行サイズと用紙サイズを取得または設定できます。  
  
 メンバー関数を使用して、スライダー コントロールの寸法を取得することもできます。  [GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md) メンバー関数を使用すると、スライダーの外接する四角形を取得できます。  [GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md) メンバー関数を使用すると、スライダー コントロールのチャネルの外接する四角形を取得できます。チャネルとは、スライダーが移動する領域であり、範囲が選択されると強調表示されます。  
  
 スライダー コントロールに `TBS_ENABLESELRANGE` スタイルが設定されている場合、ユーザーは連続する値の範囲をスライダー コントロールから選択できます。  選択範囲は、複数のメンバー関数を使用して動的に調整できます。  [SetSelection](../Topic/CSliderCtrl::SetSelection.md) メンバー関数を使用すると、選択範囲の開始位置と終了位置を設定できます。  ユーザーによる選択範囲の設定が終了している場合は、[GetSelection](../Topic/CSliderCtrl::GetSelection.md) メンバー関数を使用して設定値を取得できます。  ユーザーの選択範囲をクリアするには、[ClearSel](../Topic/CSliderCtrl::ClearSel.md) メンバー関数を使用します。  
  
## 参照  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)