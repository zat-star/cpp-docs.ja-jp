---
title: "ヘッダー コントロールへの項目の追加 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "CHeaderCtrl クラス, 追加 (アイテムを)"
  - "コントロール [MFC], ヘッダー"
  - "ヘッダー コントロール, 追加 (アイテムを)"
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘッダー コントロールへの項目の追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

親ウィンドウのヘッダー コントロール \([CHeaderCtrl](../Topic/CHeaderCtrl%20Class.md)\) を作成したら、必要な数の「ヘッダー項目」を追加する: 列ごとの通常は 1 です。  
  
### ヘッダー項目を追加するには  
  
1.  [HD\_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) 構造体を準備します。  
  
2.  構造体を渡す呼び出し [CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md)。  
  
3.  項目の追加の手順 1 ~ 2 を繰り返します。  
  
 詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [ヘッダー コントロールに項目を追加します。](http://msdn.microsoft.com/library/windows/desktop/bb775238) を参照します。  
  
## 参照  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)