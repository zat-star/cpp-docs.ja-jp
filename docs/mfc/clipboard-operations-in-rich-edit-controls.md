---
title: "リッチ エディット コントロールでのクリップボード操作 | Microsoft Docs"
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
  - "クリップボードのトピック, 操作 (CRichEditCtrl での)"
  - "コピー操作 (リッチ エディット コントロールの)"
  - "CRichEditCtrl クラス, クリップボードの操作"
  - "CRichEditCtrl クラス, 貼り付け操作"
  - "切り取り操作 (CRichEditCtrl クラスの)"
  - "貼り付け (クリップボード データを)"
  - "リッチ エディット コントロール, クリップボードの操作"
ms.assetid: 15ce66bc-2636-4a35-a2ae-d52285dc1af6
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リッチ エディット コントロールでのクリップボード操作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションはリッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) に最適な使用できるクリップボード形式または特定のクリップボード形式を使用してクリップボードの内容を貼り付けることができます。  、リッチ エディット コントロールがクリップボード形式を貼り付けることができるかどうかを確認できます。  
  
 [コピー](../Topic/CRichEditCtrl::Copy.md) または [切り取り](../Topic/CRichEditCtrl::Cut.md) メンバー関数を使用して、現在の選択内容をコピーまたは切断できます。  同様に、リッチ エディット コントロールに [貼り付け](../Topic/CRichEditCtrl::Paste.md) メンバー関数を使用して、クリップボードの内容を貼り付けることができます。  コントロールが見積もり上最もわかりやすい形式である、認識される最初の使用できる形式を貼り付けます。  
  
 特定のクリップボード形式を貼り付けるには、[PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md) メンバー関数を使用できます。  この関数は、ユーザーがクリップボード形式を選択して貼り付け特殊なコマンドを使用してアプリケーションに役立ちます。  特定の形式がコントロールで認識されるかどうかを確認するに [CanPaste](../Topic/CRichEditCtrl::CanPaste.md) メンバー関数を使用できます。  
  
 また、使用できるクリップボード形式がリッチ エディット コントロールで認識されるかどうかを確認するに `CanPaste` を使用できます。  この関数は `OnInitMenuPopup` ハンドラーに役立ちます。  アプリケーションは、コントロールが使用する形式を貼り付けることができるかどうか、灰色貼り付けコマンドで有効になる可能性があります。  
  
 リッチ エディット コントロールは 2 個のクリップボード形式を登録する: リッチ テキスト形式および形式は RichEdit Text and Objects と呼ばれます。  アプリケーションは [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) 関数を使用してこれらの形式を登録できます。**CF\_RTF** と **CF\_RETEXTOBJ** 値を指定します。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)