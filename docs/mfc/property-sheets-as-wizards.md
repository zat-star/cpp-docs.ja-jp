---
title: "ウィザードとしてのプロパティ シート | Microsoft Docs"
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
  - "プロパティ シート, ウィザードとしての"
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィザードとしてのプロパティ シート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィザードのプロパティ シートの重要な特徴はナビゲーションが次にまたはタブではなく完了、戻るボタンおよびキャンセルすることです。  この機能を利用するには、プロパティ シート オブジェクトの [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md) を呼び出す前に [CPropertySheet::SetWizardMode](../Topic/CPropertySheet::SetWizardMode.md) を呼び出す必要があります。  
  
 ユーザーが 1 ページから別のページに移動する [CPropertyPage::OnKillActive](../Topic/CPropertyPage::OnKillActive.md) 間で同じ [CPropertyPage::OnSetActive](../Topic/CPropertyPage::OnSetActive.md) と通知を受け取ります。  次に完了ボタンは同時に指定できない;コントロールです。つまり、1 種類のうちの一つだけが一度に表示されます。  最初のページで、次のボタンが有効になります。  ユーザーが最後のページにある場合は、完了ボタンが有効になります。  これは、フレームワークによって自動的になります。  これを実現するには、最後のページの [CPropertySheet::SetWizardButton](../Topic/CPropertySheet::SetWizardButtons.md) を呼び出す必要があります。  
  
 既定のボタンは、すべて粥は完了ボタンを表示し、次のボタンを移動します。  次のボタンへの相対位置が保持されるように戻るボタンを移動します。  詳細については、サポート技術情報 Q143210 を検索します。  サポート技術情報の文書は、MSDN ライブラリで使用できます。  
  
## 例  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/CPP/property-sheets-as-wizards_1.cpp)]  
  
## 参照  
 [プロパティ シート](../mfc/property-sheets-mfc.md)