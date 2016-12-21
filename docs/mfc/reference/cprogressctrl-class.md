---
title: "CProgressCtrl クラス | Microsoft Docs"
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
  - "CProgressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl クラス"
  - "Internet Explorer 4.0 コモン コントロール"
  - "プログレス コントロール [C++], CProgressCtrl クラス"
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CProgressCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン プログレス バー コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CProgressCtrl::CProgressCtrl](../Topic/CProgressCtrl::CProgressCtrl.md)|`CProgressCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CProgressCtrl::Create](../Topic/CProgressCtrl::Create.md)|進行状況バー コントロールを作成し、`CProgressCtrl` のオブジェクトにアタッチします。|  
|[CProgressCtrl::CreateEx](../Topic/CProgressCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルのプログレス コントロールを作成し、`CProgressCtrl` のオブジェクトにアタッチします。|  
|[CProgressCtrl::GetBarColor](../Topic/CProgressCtrl::GetBarColor.md)|現在の進行状況バー コントロールのプログレス インジケーター バーの色を取得します。|  
|[CProgressCtrl::GetBkColor](../Topic/CProgressCtrl::GetBkColor.md)|現在の進行状況バーの背景色を取得します。|  
|[CProgressCtrl::GetPos](../Topic/CProgressCtrl::GetPos.md)|プログレス バーの現在の位置を取得します。|  
|[CProgressCtrl::GetRange](../Topic/CProgressCtrl::GetRange.md)|進行状況バー コントロールの範囲の下限と上限を取得します。|  
|[CProgressCtrl::GetState](../Topic/CProgressCtrl::GetState.md)|現在の進行状況バー コントロールの状態を取得します。|  
|[CProgressCtrl::GetStep](../Topic/CProgressCtrl::GetStep.md)|現在の進行状況バー コントロールの進行状況バーの手順のインクリメントを取得します。|  
|[CProgressCtrl::OffsetPos](../Topic/CProgressCtrl::OffsetPos.md)|進行状況バー コントロールの現在位置をインクリメント指定に進め、新しい位置を反映してバーを再描画します。|  
|[CProgressCtrl::SetBarColor](../Topic/CProgressCtrl::SetBarColor.md)|現在の進行状況バー コントロールのプログレス インジケーター バーの色を設定します。|  
|[CProgressCtrl::SetBkColor](../Topic/CProgressCtrl::SetBkColor.md)|進行状況バーの背景色を設定します。|  
|[CProgressCtrl::SetMarquee](../Topic/CProgressCtrl::SetMarquee.md)|現在の進行状況バー コントロールに対してをオンまたはオフにマーキー モード。|  
|[CProgressCtrl::SetPos](../Topic/CProgressCtrl::SetPos.md)|進行状況バー コントロールの現在位置を設定し、新しい位置を反映してバーを再描画します。|  
|[CProgressCtrl::SetRange](../Topic/CProgressCtrl::SetRange.md)|進行状況バー コントロールの最小および最大範囲を設定し、新しいスコープを反映してバーを再描画します。|  
|[CProgressCtrl::SetState](../Topic/CProgressCtrl::SetState.md)|現在の進行状況バー コントロールの状態を設定します。|  
|[CProgressCtrl::SetStep](../Topic/CProgressCtrl::SetStep.md)|進行状況バー コントロールの増分インクリメントを指定します。|  
|[CProgressCtrl::StepIt](../Topic/CProgressCtrl::StepIt.md)|進行状況バー コントロールの現在の位置をインクリメントの手順に [SetStep](../Topic/CProgressCtrl::SetStep.md) \(を参照\) 進め、新しい位置を反映してバーを再描画します。|  
  
## 解説  
 プログレス バー コントロールは、アプリケーションが時間のかかる操作の進行状況を示すために使用できるウィンドウです。  これは、操作の進行に合わせて、システムの強調表示色で左から右へ少しずつ塗りつぶされる長方形によって構成されます。  
  
 プログレス バー コントロールは、範囲と現在位置を持っています。  範囲は操作の合計時間を表し、現在位置は、操作の完了に向けたアプリケーションの進度を表します。  ウィンドウ プロシージャは、これらの範囲と現在位置を使用して、プログレス バーを強調表示色で塗りつぶす割合を決定します。  範囲と現在位置の値は符号付き整数で表されるため、現在位置の値の有効な範囲は \-217,483,648 ～ 2,147,483,647 になります。  
  
 `CProgressCtrl` の使い方の詳細については、「[コントロール](../../mfc/controls-mfc.md)」および「[CProgressCtrl の使い方](../../mfc/using-cprogressctrl.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CProgressCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [MFC CMNCTRL2 サンプル](../../top/visual-cpp-samples.md)   
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)