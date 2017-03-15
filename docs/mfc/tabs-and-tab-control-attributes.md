---
title: "タブおよびタブ コントロールの属性 | Microsoft Docs"
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
  - "属性 [C++], 参照トピック"
  - "CTabCtrl クラス, タブ コントロール属性"
  - "タブ コントロール, 属性"
  - "タブ"
  - "タブ, 属性"
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# タブおよびタブ コントロールの属性
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

外観の多くのタブ コントロール \([CTabCtrl](../Topic/CTabCtrl%20Class.md)\) を構成するコントロールとタブの動作が異なります。  各タブ ラベルは、アイコン、および作業項目の状態と関連付けられるアプリケーション定義の 32 ビット値を持つことができます。  各タブには、アイコン、ラベル、またはその両方を表示できます。  
  
 また、各タブ アイテムは 3 とおりの状態を持つことができますが、T: アンプレスト、押された状態または強調表示されます。  この状態は、既存のタブ項目の変更でしか設定できません。  既存のタブ項目を変更するには、呼び出しを [GetItem](../Topic/CTabCtrl::GetItem.md)に取得して、`TCITEM` 構造体 \(具体的に **dwState** と **dwStateMask** のデータ メンバー\) を変更し、[SetItem](../Topic/CTabCtrl::SetItem.md)を呼び出して `TCITEM` の変更された構造体を返します。  すべての項目を削除する必要がある場合 `CTabCtrl` のタブ項目は [DeselectAll](../Topic/CTabCtrl::DeselectAll.md)呼び出しに、オブジェクトを作成します。  この関数は、すべてのタブ項目またはすべての項目の状態以外の現在オンにリセットします。  
  
 次のコードは、すべてのタブ アイテムの状態を削除し、3 番目の項目の状態を変更する:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/CPP/tabs-and-tab-control-attributes_1.cpp)]  
  
 タブの属性の詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [タブおよびタブの属性](http://msdn.microsoft.com/library/windows/desktop/bb760550) を参照します。  タブ コントロールにタブを追加する方法の詳細については、このトピックの [タブ コントロールにタブを追加します。](../mfc/adding-tabs-to-a-tab-control.md) を後で参照します。  
  
## 参照  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)