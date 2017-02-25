---
title: "CSliderCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSliderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl クラス"
  - "CSliderCtrl クラス, コモン コントロール"
  - "スライダー コントロール, CSliderCtrl クラス"
  - "Windows コモン コントロール [C++], CSliderCtrl"
ms.assetid: dd12b084-4eda-4550-a810-8f3cfb06b871
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CSliderCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン スライダー コントロールの機能を提供します。  
  
## 構文  
  
```  
class CSliderCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSliderCtrl::CSliderCtrl](../Topic/CSliderCtrl::CSliderCtrl.md)|`CSliderCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSliderCtrl::ClearSel](../Topic/CSliderCtrl::ClearSel.md)|スライダー コントロールの現在の選択を解除します。|  
|[CSliderCtrl::ClearTics](../Topic/CSliderCtrl::ClearTics.md)|スライダー コントロールの現在のスケールを削除します。|  
|[CSliderCtrl::Create](../Topic/CSliderCtrl::Create.md)|スライダー コントロールを作成し、`CSliderCtrl` のオブジェクトにアタッチします。|  
|[CSliderCtrl::CreateEx](../Topic/CSliderCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルのスライダー コントロールを作成し、`CSliderCtrl` のオブジェクトにアタッチします。|  
|[CSliderCtrl::GetBuddy](../Topic/CSliderCtrl::GetBuddy.md)|指定された位置にあるスライダー コントロールの関連ウィンドウへのハンドルを取得します。|  
|[CSliderCtrl::GetChannelRect](../Topic/CSliderCtrl::GetChannelRect.md)|スライダー コントロールのチャネルのサイズを取得します。|  
|[CSliderCtrl::GetLineSize](../Topic/CSliderCtrl::GetLineSize.md)|スライダー コントロールの行のサイズを取得します。|  
|[CSliderCtrl::GetNumTics](../Topic/CSliderCtrl::GetNumTics.md)|スライダー コントロールの目盛りの数を取得します。|  
|[CSliderCtrl::GetPageSize](../Topic/CSliderCtrl::GetPageSize.md)|スライダー コントロールのページ サイズを取得します。|  
|[CSliderCtrl::GetPos](../Topic/CSliderCtrl::GetPos.md)|スライダーの現在位置を取得します。|  
|[CSliderCtrl::GetRange](../Topic/CSliderCtrl::GetRange.md)|スライダーの最小値と最大位置を取得します。|  
|[CSliderCtrl::GetRangeMax](../Topic/CSliderCtrl::GetRangeMax.md)|スライダーの最大の位置を取得します。|  
|[CSliderCtrl::GetRangeMin](../Topic/CSliderCtrl::GetRangeMin.md)|スライダーの最小の位置を取得します。|  
|[CSliderCtrl::GetSelection](../Topic/CSliderCtrl::GetSelection.md)|現在の選択範囲を取得します。|  
|[CSliderCtrl::GetThumbLength](../Topic/CSliderCtrl::GetThumbLength.md)|現在の trackbar コントロールのスライダーの長さを取得します。|  
|[CSliderCtrl::GetThumbRect](../Topic/CSliderCtrl::GetThumbRect.md)|スライダーのつまみコントロールのサイズを取得します。|  
|[CSliderCtrl::GetTic](../Topic/CSliderCtrl::GetTic.md)|指定の目盛りの位置を取得します。|  
|[CSliderCtrl::GetTicArray](../Topic/CSliderCtrl::GetTicArray.md)|スライダー コントロールの目盛りの位置の配列を取得します。|  
|[CSliderCtrl::GetTicPos](../Topic/CSliderCtrl::GetTicPos.md)|クライアント座標で指定された目盛りの位置を取得します。|  
|[CSliderCtrl::GetToolTips](../Topic/CSliderCtrl::GetToolTips.md)|スライダー コントロールに割り当てられたヒント コントロールのハンドルです \(存在する場合\) を取得します。|  
|[CSliderCtrl::SetBuddy](../Topic/CSliderCtrl::SetBuddy.md)|スライダー コントロールの関連ウィンドウとしてウィンドウを割り当てます。|  
|[CSliderCtrl::SetLineSize](../Topic/CSliderCtrl::SetLineSize.md)|スライダー コントロールの行のサイズを設定します。|  
|[CSliderCtrl::SetPageSize](../Topic/CSliderCtrl::SetPageSize.md)|スライダー コントロールのページ サイズを設定します。|  
|[CSliderCtrl::SetPos](../Topic/CSliderCtrl::SetPos.md)|スライダーの現在位置を設定します。|  
|[CSliderCtrl::SetRange](../Topic/CSliderCtrl::SetRange.md)|スライダーの最小値と最大位置を設定します。|  
|[CSliderCtrl::SetRangeMax](../Topic/CSliderCtrl::SetRangeMax.md)|スライダーの最大の位置を設定します。|  
|[CSliderCtrl::SetRangeMin](../Topic/CSliderCtrl::SetRangeMin.md)|スライダーの最小の位置を設定します。|  
|[CSliderCtrl::SetSelection](../Topic/CSliderCtrl::SetSelection.md)|現在の選択範囲を設定します。|  
|[CSliderCtrl::SetThumbLength](../Topic/CSliderCtrl::SetThumbLength.md)|現在の trackbar コントロールのスライダーの長さを設定します。|  
|[CSliderCtrl::SetTic](../Topic/CSliderCtrl::SetTic.md)|指定の目盛りの位置を設定します。|  
|[CSliderCtrl::SetTicFreq](../Topic/CSliderCtrl::SetTicFreq.md)|スライダー コントロールのインクリメントごとの目盛りの間隔を設定します。|  
|[CSliderCtrl::SetTipSide](../Topic/CSliderCtrl::SetTipSide.md)|trackbar コントロールで使用するヒント コントロールを設定します。|  
|[CSliderCtrl::SetToolTips](../Topic/CSliderCtrl::SetToolTips.md)|スライダー コントロールにツールヒント コントロールを割り当てます。|  
  
## 解説  
 スライダー コントロール」は「とも呼ばれます\) trackbar スライダーと省略可能なグリッドを含むウィンドウです。  ユーザーがスライダーを、を使用して実行時のマウスまたは方向キーは、コントロール変更を表示するには、通知メッセージを送信します。  
  
 スライダー コントロールはユーザーの範囲の連続する値を個々の値または複数選択する場合に便利です。  たとえば、ユーザーが特定のグリッドにスライダーを動かすことによってキーボードのリピート間隔を設定できるようにするには、スライダー コントロールを使用する場合があります。  
  
 このコントロール \(したがって `CSliderCtrl` のクラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 スライダーは、指定した単位でそれを作成するときに実行されます。  スライダーは 5 の範囲が必要であることをたとえば、を指定すると、スライダーは 6 種類の位置を占有できる: スライダー コントロールの左端の位置と範囲の各インクリメントを表す 1 桁の位置。  通常、これらの位置はそれぞれ、グリッド識別されます。  
  
 `CSliderCtrl`のコンストラクターと **\[作成\]** のメンバー関数を使用してスライダーを作成します。  スライダー コントロールを作成する場合は、`CSliderCtrl` で複数のプロパティを変更するには、メンバー関数を使用できます。  スライダーの最小値と最大位置を設定すると、グリッドの描画、選択範囲の設定、およびスライダーを再配置を含むように適用できる変更します。  
  
 `CSliderCtrl`の使用の詳細については、[コントロール](../../mfc/controls-mfc.md) と [を使用して CSliderCtrl](../../mfc/using-csliderctrl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CSliderCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [MFC CMNCTRL2 サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CProgressCtrl クラス](../../mfc/reference/cprogressctrl-class.md)