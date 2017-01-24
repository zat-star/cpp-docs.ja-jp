---
title: "リッチ エディット コントロールでの現在の選択項目 | Microsoft Docs"
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
  - "CRichEditCtrl クラス, 現在の選択項目"
  - "現在の選択項目 (CRichEditCtrls 内の)"
  - "リッチ エディット コントロール, 現在の選択項目"
  - "選択, 現在の値 (CRichEditCtrl の)"
ms.assetid: f6b2a2b6-5481-4ad3-9720-6dd772ea6fc8
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# リッチ エディット コントロールでの現在の選択項目
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザーがマウスまたはキーボードを使用してリッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) のテキストを選択できます。  現在の選択項目が文字が選択した文字の範囲、またはカーソルの位置です。  アプリケーションには、現在の選択項目が変更された、表示と非表示の強調表示を選択できます。設定された現在の選択項目を確認し、現在の選択範囲についての情報を取得できます。  
  
 リッチ エディット コントロールの現在の選択項目を確認するには、[GetSel](../Topic/CRichEditCtrl::GetSel.md) メンバー関数を使用します。  現在の選択項目を設定するには、[SetSel](../Topic/CRichEditCtrl::SetSel.md) メンバー関数を使用します。  これらの関数と [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 構造体は文字の範囲を指定するために使用されます。  現在の選択項目の内容に関する情報を取得するには、[GetSelectionType](../Topic/CRichEditCtrl::GetSelectionType.md) メンバー関数を使用できます。  
  
 フォーカスを取得し、失ったときに選択を強調表示する既定で、リッチ エディット コントロールの表示と非表示を切り替えます。  [HideSelection](../Topic/CRichEditCtrl::HideSelection.md) メンバー関数を使用して選択の枠をいつでも表示または非表示にできます。  たとえば、アプリケーションでリッチ エディット コントロールのテキストを検索ダイアログ ボックスを表示する場合があります。  アプリケーションでは、ダイアログ ボックスを閉じずに選択を強調表示するために `HideSelection` を使用する必要がある場合は、一致したテキストを選択している可能性があります。  
  
 リッチ エディット コントロールの選択されたテキストを取得するには、[GetSelText](../Topic/CRichEditCtrl::GetSelText.md) メンバー関数を使用します。  テキストは、指定された文字配列にコピーされます。  終端の NULL 文字と選択したテキストを保持するには配列が十分に大きいことを確認する必要があります。  
  
 リッチ エディット コントロールの文字列をこの関数で使用される [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) 構造体に検索対象と文字列を検索するには、テキスト範囲指定する [FindText](../Topic/CRichEditCtrl::FindText.md) メンバー関数を使用して検索できます。  検索では大文字と小文字を区別するかどうかなどのオプションを指定できます。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)