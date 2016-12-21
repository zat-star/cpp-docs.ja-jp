---
title: "CStatusBarCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl クラス"
  - "ステータス バー コントロール"
  - "Windows コモン コントロール [C++], CStatusBarCtrl"
ms.assetid: 8504ad38-7b91-4746-aede-ac98886eb47b
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBarCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン ステータス バー コントロール の機能が用意されています。  
  
## 構文  
  
```  
class CStatusBarCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CStatusBarCtrl::CStatusBarCtrl](../Topic/CStatusBarCtrl::CStatusBarCtrl.md)|`CStatusBarCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CStatusBarCtrl::Create](../Topic/CStatusBarCtrl::Create.md)|ステータス バー コントロールを作成し、`CStatusBarCtrl` のオブジェクトにアタッチします。|  
|[CStatusBarCtrl::CreateEx](../Topic/CStatusBarCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルのステータス バー コントロールを作成し、`CStatusBarCtrl` のオブジェクトにアタッチします。|  
|[CStatusBarCtrl::DrawItem](../Topic/CStatusBarCtrl::DrawItem.md)|オーナー描画のステータス バー コントロールの外観を変更するときに呼び出されます。|  
|[CStatusBarCtrl::GetBorders](../Topic/CStatusBarCtrl::GetBorders.md)|ステータス バー コントロールの水平方向と垂直方向の境界線の現在の幅を取得します。|  
|[CStatusBarCtrl::GetIcon](../Topic/CStatusBarCtrl::GetIcon.md)|現在のステータス バー コントロールの一部 \(または\) ウィンドウのアイコンを取得します。|  
|[CStatusBarCtrl::GetParts](../Topic/CStatusBarCtrl::GetParts.md)|ステータス バー コントロールの一部の数を取得します。|  
|[CStatusBarCtrl::GetRect](../Topic/CStatusBarCtrl::GetRect.md)|ステータス バー コントロールの一部の外接する四角形を取得します。|  
|[CStatusBarCtrl::GetText](../Topic/CStatusBarCtrl::GetText.md)|ステータス バー コントロールの特定の部分からテキストを取得します。|  
|[CStatusBarCtrl::GetTextLength](../Topic/CStatusBarCtrl::GetTextLength.md)|ステータス バー コントロールの特定の部分から長さを、テキスト文字で取得します。|  
|[CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md)|ステータス バー ペインのツールヒント テキストを取得します。|  
|[CStatusBarCtrl::IsSimple](../Topic/CStatusBarCtrl::IsSimple.md)|ステータス ペイン コントロールを単純なモードかどうかを確認します。|  
|[CStatusBarCtrl::SetBkColor](../Topic/CStatusBarCtrl::SetBkColor.md)|ステータス バーの背景色を設定します。|  
|[CStatusBarCtrl::SetIcon](../Topic/CStatusBarCtrl::SetIcon.md)|ステータス バー ペインのアイコンを設定します。|  
|[CStatusBarCtrl::SetMinHeight](../Topic/CStatusBarCtrl::SetMinHeight.md)|ステータス バー コントロールの描画領域の最小の高さを設定します。|  
|[CStatusBarCtrl::SetParts](../Topic/CStatusBarCtrl::SetParts.md)|ステータス バー コントロールの一部の数と各部分の右端の座標を設定します。|  
|[CStatusBarCtrl::SetSimple](../Topic/CStatusBarCtrl::SetSimple.md)|ステータス バー コントロールは、単純テキストを表示または `SetParts`への前の呼び出しによって配置されたコントロールの各部分を表示するかどうかを指定します。|  
|[CStatusBarCtrl::SetText](../Topic/CStatusBarCtrl::SetText.md)|ステータス バー コントロールの特定の部分のテキストを設定します。|  
|[CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md)|ステータス バー ペインのツールヒント テキストを設定します。|  
  
## 解説  
 「ステータス バー コントロール」は通常、アプリケーションがさまざまなステータス情報を表示できる親ウィンドウの下部に表示される水平方向のウィンドウです。  ステータス バー コントロールは、部分に複数の種類の情報を表示するために分割できます。  
  
 このコントロール \(したがって `CStatusBarCtrl` のクラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 `CStatusBarCtrl`の使用の詳細については、[コントロール](../../mfc/controls-mfc.md) と [を使用して CStatusBarCtrl](../../mfc/using-cstatusbarctrl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CStatusBarCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)