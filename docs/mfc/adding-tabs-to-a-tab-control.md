---
title: "タブ コントロールへのタブの追加 | Microsoft Docs"
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
  - "CTabCtrl クラス, 追加 (タブを)"
  - "配置 (CTabCtrls にタブを)"
  - "タブ コントロール, 追加 (タブを)"
  - "タブ, 追加 (CTabCtrl クラスに)"
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# タブ コントロールへのタブの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

タブ コントロール[CTabCtrl](../Topic/CTabCtrl%20Class.md) \(\) を作成したら、必要な数のタブを追加します。  
  
### タブ項目を追加するには  
  
1.  [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) 構造体を準備します。  
  
2.  構造体を渡す呼び出し [CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md)。  
  
3.  タブ アイテムの追加手順 1 ~ 2 を繰り返します。  
  
 詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [タブ コントロールの作成](http://msdn.microsoft.com/library/windows/desktop/bb760550) を参照します。  
  
## 参照  
 [CTabCtrl の使い方](../mfc/using-ctabctrl.md)   
 [コントロール](../mfc/controls-mfc.md)