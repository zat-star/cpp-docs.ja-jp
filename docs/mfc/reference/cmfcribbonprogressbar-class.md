---
title: "CMFCRibbonProgressBar クラス | Microsoft Docs"
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
  - "CMFCRibbonProgressBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonProgressBar クラス"
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonProgressBar クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

時間のかかる操作の進行状況を視覚的に示すコントロールを実装します。  
  
## 構文  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](../Topic/CMFCRibbonProgressBar::CMFCRibbonProgressBar.md)|`CMFCRibbonProgressBar` オブジェクトを構築し、初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonProgressBar::GetPos](../Topic/CMFCRibbonProgressBar::GetPos.md)|現在の進行状況を返します。|  
|[CMFCRibbonProgressBar::GetRangeMax](../Topic/CMFCRibbonProgressBar::GetRangeMax.md)|現在の範囲の最大値を返します。|  
|[CMFCRibbonProgressBar::GetRangeMin](../Topic/CMFCRibbonProgressBar::GetRangeMin.md)|現在の範囲の最小値を返します。|  
|[CMFCRibbonProgressBar::GetRegularSize](../Topic/CMFCRibbonProgressBar::GetRegularSize.md)|リボン要素の標準サイズを返します。  \([CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md) をオーバーライドします。\)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](../Topic/CMFCRibbonProgressBar::IsInfiniteMode.md)|プログレス バーが無限モードで動作しているかどうかを指定します。|  
|[CMFCRibbonProgressBar::OnDraw](../Topic/CMFCRibbonProgressBar::OnDraw.md)|リボン要素を描画するために、フレームワークによって呼び出されます。  \([CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md) をオーバーライドします。\)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](../Topic/CMFCRibbonProgressBar::SetInfiniteMode.md)|プログレス バーが無限モードで動作するように設定します。|  
|[CMFCRibbonProgressBar::SetPos](../Topic/CMFCRibbonProgressBar::SetPos.md)|現在の進行状況を設定します。|  
|[CMFCRibbonProgressBar::SetRange](../Topic/CMFCRibbonProgressBar::SetRange.md)|最小値および最大値を設定します。|  
  
## 解説  
 `CMFCRibbonProgressBar` は、2 つのモード \(通常モードと無限モード\) で処理できます。  通常モードでは、プログレス バーが左から右に塗りつぶされ、最大値に達すると停止します。  無限モードでは、プログレス バーが最小値から最大値まで繰り返し、塗りつぶされます。  無限モードを使用すると、操作が進行中で、完了までの時間は不明であることを指定できます。  
  
## 使用例  
 `CMFCRibbonProgressBar` クラスのさまざまなメソッドの使用方法を次の例に示します。  この例では、無限モードで動作するようプログレス バーを設定する方法 \(処理の完了時間が不明な場合\)、プログレス バーの最小値と最大値を設定する方法、およびプログレス バーの現在の位置を設定する方法を示しています。  このコード スニペットは [MS の Office 2007 のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#11](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#11)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## 必要条件  
 **ヘッダー :** afxRibbonProgressBar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)