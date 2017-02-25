---
title: "CMFCCaptionButton クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCaptionButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionButton クラス"
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCCaptionButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCCaptionButton` クラスは、ドッキング ペインまたはミニフレーム ウィンドウのキャプション バーに表示されるボタンを実装します。  通常は、フレームワークがキャプション ボタンを自動的に作成します。  
  
## 構文  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## メンバー  
  
### コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCCaptionButton::CMFCCaptionButton](../Topic/CMFCCaptionButton::CMFCCaptionButton.md)|CMFCCaptionButton オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCCaptionButton::GetHit](../Topic/CMFCCaptionButton::GetHit.md)|ボタンによって表されるコマンドを返します。|  
|[CMFCCaptionButton::GetIconID](../Topic/CMFCCaptionButton::GetIconID.md)|ボタンに関連付けられているイメージ ID を返します。|  
|[CMFCCaptionButton::GetRect](../Topic/CMFCCaptionButton::GetRect.md)|ボタンによって占有される四角形を返します。|  
|[CMFCCaptionButton::GetSize](../Topic/CMFCCaptionButton::GetSize.md)|ボタンの幅と高さを返します。|  
|[CMFCCaptionButton::IsMiniFrameButton](../Topic/CMFCCaptionButton::IsMiniFrameButton.md)|タイトル バーの高さをミニサイズに設定するかどうかを示します。|  
|[CMFCCaptionButton::Move](../Topic/CMFCCaptionButton::Move.md)|ボタンの描画位置とウィンドウの表示状態を設定します。|  
|[CMFCCaptionButton::OnDraw](../Topic/CMFCCaptionButton::OnDraw.md)|キャプション ボタンを描画します。|  
|[CMFCCaptionButton::SetMiniFrameButton](../Topic/CMFCCaptionButton::SetMiniFrameButton.md)|タイトル バーのミニサイズを設定します。|  
  
## 解説  
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)からクラスを派生し、プロテクト メソッド `AddButton` を使用して、ミニフレーム ウィンドウにキャプション ボタンを追加できます。  
  
 CPaneFrameWnd.h では、次の 2 種類のキャプション ボタンのコマンド ID が定義されています。  
  
-   `AFX_CAPTION_BTN_PIN`。ドッキング ペインが自動非表示モードをサポートする場合は、ピン ボタンを表示します。  
  
-   `AFX_CAPTION_BTN_CLOSE`。ペインを閉じるか、非表示にすることができる場合は、**\[閉じる\]** ボタンを表示します。  
  
## 使用例  
 `CMFCCaptionButton` オブジェクトを構築してタイトル バーのミニサイズを設定する方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/CPP/cmfccaptionbutton-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxcaptionbutton.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane クラス](../Topic/CDockablePane%20Class.md)