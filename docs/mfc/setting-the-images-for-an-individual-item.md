---
title: "各項目のイメージの設定 | Microsoft Docs"
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
  - "拡張コンボ ボックス, イメージ"
  - "イメージ [C++], コンボ ボックスの項目"
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 各項目のイメージの設定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

拡張コンボ ボックス項目に使用するイメージの種類に [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) 構造体の `iImage`、**iSelectedImage**と **iOverlay** のメンバーの値によって決まります。  それぞれの値は、コントロールに関連付けられたイメージ リスト内のイメージのインデックスです。  既定では 0 に、これらのメンバーに設定され、項目のイメージを表示するようにコントロールに指示します。  特定の項目のイメージを使用する場合は、コンボ ボックス アイテムを既存のコンボ ボックスの項目の変更で挿入すると構造体、いずれかを適宜変更できます。  
  
## 新しい項目のイメージの設定  
 新しい項目を挿入する場合は、適切な値を `iImage`、**iSelectedImage**と **iOverlay** の構造体メンバーを初期化し、[CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md)を呼び出して項目を挿入します。  
  
 次の例では、3 つすべてのイメージの状態のインデックスを指定する拡張コンボ ボックスのコントロール \(`m_comboEx`\) に新しい拡張コンボ ボックス項目 \(`cbi`\) を挿入します:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#12](../mfc/codesnippet/CPP/setting-the-images-for-an-individual-item_1.cpp)]  
  
## 既存の項目のイメージの設定  
 既存のアイテムを変更する場合、**COMBOBOXEXITEM** 構造体の **マスク** のメンバーを使用する必要があります。  
  
#### 既存のアイテムをイメージを使用するように変更するには  
  
1.  **COMBOBOXEXITEM** 構造体を宣言し、変更の対象となる値に **マスク** のデータ メンバーを TRUE に設定します。  
  
2.  この構造を使用すると、[CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md)に呼び出しを行ってください。  
  
3.  適切な値を使用して最近返された構造体の **マスク**、`iImage`と **iSelectedImage** のメンバーを変更します。  
  
4.  変更された構造体を渡す [CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md)に呼び出しを行ってください。  
  
 次の例では、3 番目の拡張コンボ ボックス項目の選択および選択解除にされたイメージの交換してこの手順です:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#13](../mfc/codesnippet/CPP/setting-the-images-for-an-individual-item_2.cpp)]  
  
## 参照  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)