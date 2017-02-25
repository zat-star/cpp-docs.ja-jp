---
title: "CSpinButtonCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl クラス"
  - "CSpinButtonCtrl クラス, コモン コントロール"
  - "スピン ボタン コントロール"
  - "アップダウン コントロール, スピン ボタン コントロール"
  - "Windows コモン コントロール [C++], CSpinButtonCtrl"
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSpinButtonCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン スピン ボタン コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](../Topic/CSpinButtonCtrl::CSpinButtonCtrl.md)|`CSpinButtonCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSpinButtonCtrl::Create](../Topic/CSpinButtonCtrl::Create.md)|スピン ボタン コントロールを作成し、`CSpinButtonCtrl` のオブジェクトにアタッチします。|  
|[CSpinButtonCtrl::CreateEx](../Topic/CSpinButtonCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルのスピン ボタン コントロールを作成し、`CSpinButtonCtrl` のオブジェクトにアタッチします。|  
|[CSpinButtonCtrl::GetAccel](../Topic/CSpinButtonCtrl::GetAccel.md)|スピン ボタン コントロールの加速情報を取得します。|  
|[CSpinButtonCtrl::GetBase](../Topic/CSpinButtonCtrl::GetBase.md)|スピン ボタン コントロールの現在の条件を取得します。|  
|[CSpinButtonCtrl::GetBuddy](../Topic/CSpinButtonCtrl::GetBuddy.md)|現在の関連ウィンドウへのポインターを取得します。|  
|[CSpinButtonCtrl::GetPos](../Topic/CSpinButtonCtrl::GetPos.md)|スピン ボタン コントロールの現在位置を取得します。|  
|[CSpinButtonCtrl::GetRange](../Topic/CSpinButtonCtrl::GetRange.md)|スピン ボタン コントロールの上限と下限 \(範囲\) を取得します。|  
|[CSpinButtonCtrl::SetAccel](../Topic/CSpinButtonCtrl::SetAccel.md)|スピン ボタン コントロールのアクセラレータを設定します。|  
|[CSpinButtonCtrl::SetBase](../Topic/CSpinButtonCtrl::SetBase.md)|スピン ボタン コントロールに対して条件を設定します。|  
|[CSpinButtonCtrl::SetBuddy](../Topic/CSpinButtonCtrl::SetBuddy.md)|スピン ボタン コントロールの関連ウィンドウを設定します。|  
|[CSpinButtonCtrl::SetPos](../Topic/CSpinButtonCtrl::SetPos.md)|コントロールの現在位置を設定します。|  
|[CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md)|スピン ボタン コントロールの上限と下限 \(範囲\) を設定します。|  
  
## 解説  
 「スピン ボタン コントロール」は \(またはアップダウン コントロール\) 値を増加または減少するユーザーがクリックできる表示するコンパニオン コントロールのスクロール位置や数字などのペアの矢印ボタンです。  スピン ボタン コントロールに関連付けられた値は現在位置と呼ばれます。  スピン ボタン コントロールは「関連ウィンドウと呼ばれるコンパニオン コントロールとともに使用します」。  
  
 このコントロール \(したがって `CSpinButtonCtrl` のクラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 ユーザーは、スピン ボタン コントロールと関連ウィンドウは、単一のコントロールのようになります。  スピン ボタン コントロールが関連ウィンドウの横に自動的に設定すること、および現在位置に自動的に関連ウィンドウのキャプションを設定したことを指定できます。  数値入力をユーザーに求めるエディット コントロールを持つスピン ボタン コントロールを使用できます。  
  
 上方向キーをクリックすると最大の方向に現在位置を実行し、それぞれの矢印をクリックすると最小の方向に現在位置を移動します。  既定では、最小値は 100、最大値は 0 です。  最小限の設定が最大の設定値より大きい既定の設定を使用する場合、\(など\)、上向きの矢印をクリックすると、位置の値を小さくし、矢印をクリックすると、そのをインクリメントします。  
  
 単純種類のスクロール バーとして関連の Windows 関数のないスピン ボタン コントロール。  たとえば、タブ コントロールは、ビューに追加のタブをスクロールできるようにするために、スピン ボタン コントロールを表示します。  
  
 `CSpinButtonCtrl`の使用の詳細については、[コントロール](../../mfc/controls-mfc.md) と [を使用して CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CSpinButtonCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [MFC CMNCTRL2 サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl クラス](../../mfc/reference/csliderctrl-class.md)