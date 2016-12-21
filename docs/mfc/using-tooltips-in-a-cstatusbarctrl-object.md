---
title: "CStatusBarCtrl オブジェクトでのツール ヒントの使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CStatusBarCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStatusBarCtrl クラス, ツール ヒント"
  - "ステータス バー, ツール ヒント"
  - "ツール ヒント [C++], 使用 (ステータス バーで)"
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStatusBarCtrl オブジェクトでのツール ヒントの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ステータス バー コントロールのツールヒントを有効にするには、**SBT\_TOOLTIPS** のスタイルと `CStatusBarCtrl` オブジェクトを作成します。  
  
> [!NOTE]
>  ステータス バーを実装したらに `CStatusBar` オブジェクトを使用して `CStatusBar::CreateEx` 関数を使用します。  これは **CStatusBarCtrl** の埋め込まれたなオブジェクトの追加スタイルを指定できるようにします。  
  
 `CStatusBarCtrl` が正常に作成された場合は、特定のペインのツールヒント テキストを設定し、取得する使用 [CStatusBarCtrl::SetTipText](../Topic/CStatusBarCtrl::SetTipText.md) と [CStatusBarCtrl::GetTipText](../Topic/CStatusBarCtrl::GetTipText.md)。  
  
 ツール ヒントを設定すると、パートはアイコンおよびテキストが存在しない場合にのみ、またはテキスト全体がパート内に表示する場合に表示されます。  ツール ヒントは簡易モードではサポートされていません。  
  
## 参照  
 [CStatusBarCtrl の使い方](../mfc/using-cstatusbarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)