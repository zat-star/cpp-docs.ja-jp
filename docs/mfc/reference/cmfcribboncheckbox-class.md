---
title: "CMFCRibbonCheckBox クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonCheckBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonCheckBox クラス"
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCRibbonCheckBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonCheckBox` クラスは、リボン パネル、クイック アクセス ツール バー、またはポップアップ メニューに追加できるチェック ボックスを実装します。  
  
## 構文  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](../Topic/CMFCRibbonCheckBox::CMFCRibbonCheckBox.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonCheckBox::GetCompactSize](../Topic/CMFCRibbonCheckBox::GetCompactSize.md)|\([CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md) をオーバーライドします\)。|  
|[CMFCRibbonCheckBox::GetIntermediateSize](../Topic/CMFCRibbonCheckBox::GetIntermediateSize.md)|\([CMFCRibbonButton::GetIntermediateSize](../Topic/CMFCRibbonButton::GetIntermediateSize.md) をオーバーライドします\)。|  
|[CMFCRibbonCheckBox::GetRegularSize](../Topic/CMFCRibbonCheckBox::GetRegularSize.md)|\([CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md) をオーバーライドします\)。|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](../Topic/CMFCRibbonCheckBox::IsDrawTooltipImage.md)|\(`CMFCRibbonButton::IsDrawTooltipImage` をオーバーライドします\)。|  
|[CMFCRibbonCheckBox::OnDraw](../Topic/CMFCRibbonCheckBox::OnDraw.md)|\([CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md) をオーバーライドします\)。|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](../Topic/CMFCRibbonCheckBox::OnDrawMenuImage.md)|\([CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md) をオーバーライドします\)。|  
|[CMFCRibbonCheckBox::OnDrawOnList](../Topic/CMFCRibbonCheckBox::OnDrawOnList.md)|\(`CMFCRibbonButton::OnDrawOnList` をオーバーライドします\)。|  
|[CMFCRibbonCheckBox::SetACCData](../Topic/CMFCRibbonCheckBox::SetACCData.md)|\([CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md) をオーバーライドします\)。|  
  
## 解説  
 `CMFCRibbonCheckBox` をアプリケーションで使用するには、次のコンストラクターをコードに追加します。  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
  
 ここで、`nID` はチェック ボックスのコマンド ID を示し、`lpszText` はチェック ボックスのテキスト ラベルを示します。  
  
 [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md) を使用して、リボン パネルにチェック ボックスを追加できます。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## 必要条件  
 **ヘッダー:** afxribboncheckbox.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonPanel クラス](../../mfc/reference/cmfcribbonpanel-class.md)