---
title: "CMFCRibbonApplicationButton クラス | Microsoft Docs"
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
  - "CMFCRibbonApplicationButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonApplicationButton クラス"
ms.assetid: beb81757-fabd-4641-9130-876ba8505b78
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonApplicationButton クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アプリケーション ウィンドウの左上隅に表示される特殊なボタンを実装します。  このボタンがクリックされると、通常は、**\[ファイル\]** メニューに表示されるコマンド \(**\[開く\]**、**\[上書き保存\]**、**\[終了\]** など\) を含むメニューが開かれます。  
  
## 構文  
  
```  
class CMFCRibbonApplicationButton : public CMFCRibbonButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonApplicationButton::CMFCRibbonApplicationButton](../Topic/CMFCRibbonApplicationButton::CMFCRibbonApplicationButton.md)|`CMFCRibbonApplicationButton` オブジェクトを構築し、初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCRibbonApplicationButton::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークによって使用されます。|  
|`CMFCRibbonApplicationButton::GetThisClass`|このクラス型に関連付けられた [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|  
|[CMFCRibbonApplicationButton::SetImage](../Topic/CMFCRibbonApplicationButton::SetImage.md)|イメージをリボン アプリケーション ボタンに割り当てます。|  
  
## 使用例  
 次の例は、`CMFCRibbonApplicationButton` クラスのさまざまなメソッドの使用方法を説明しています。  具体的には、イメージをアプリケーション ボタンに割り当てる方法と、ツールヒントを設定する方法が示されています。  このコード スニペットは [クライアント サンプルを描画](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#4](../../mfc/reference/codesnippet/CPP/cmfcribbonapplicationbutton-class_1.h)]  
[!code-cpp[NVC_MFC_DrawClient#5](../../mfc/reference/codesnippet/CPP/cmfcribbonapplicationbutton-class_2.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)  
  
## 必要条件  
 **ヘッダー :** afxRibbonBar.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)