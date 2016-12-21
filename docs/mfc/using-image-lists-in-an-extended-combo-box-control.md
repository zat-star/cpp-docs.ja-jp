---
title: "拡張コンボ ボックス コントロールでのイメージ リストの使い方 | Microsoft Docs"
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
  - "イメージ リスト [C++], コンボ ボックス"
  - "イメージ [C++], コンボ ボックスの項目"
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 拡張コンボ ボックス コントロールでのイメージ リストの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

拡張コンボ ボックスのコントロールの主な機能は、コンボ ボックス コントロールの個別の項目とイメージ リストからイメージを関連付ける機能です。  各項目は 3 個のイメージを表示する: 選択された状態の 1、nonselected 状態の 1、オーバーレイ イメージの省略されています。  
  
 次の手順では拡張コンボ ボックスのコントロールでイメージ リストを関連付ける:  
  
### イメージ リストを拡張コンボ ボックスのコントロールに関連付けるには  
  
1.  [CImageList](../Topic/CImageList%20Class.md) のコンストラクターおよび生成されたポインターを格納するために使用する新しいイメージ リストを設定する \(または、既存のイメージ リスト オブジェクトを使用\)、構築します。  
  
2.  [CImageList::Create](../Topic/CImageList::Create.md)を呼び出して新しいイメージ リスト オブジェクトを初期化してください。  次のコードは、この呼び出しの 1 例です。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_1.cpp)]  
  
3.  それぞれの可能な状態のオプションのイメージを追加する: 選択または nonselected、オーバーレイ。  次のコードは、3 種類の定義済みのイメージを追加します。  
  
     [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/CPP/using-image-lists-in-an-extended-combo-box-control_2.cpp)]  
  
4.  [CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md)を呼び出して、イメージ リストをコントロールに関連付けます。  
  
 イメージ リストをコントロールに関連付けられている場合、各項目が 3 とおりの状態に使用するイメージを指定できます。  詳細については、「[個々の項目のイメージの設定](../mfc/setting-the-images-for-an-individual-item.md)」を参照してください。  
  
## 参照  
 [CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)   
 [コントロール](../mfc/controls-mfc.md)