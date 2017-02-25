---
title: "リッチ エディット コントロールの概要 | Microsoft Docs"
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
  - "リッチ エディット コントロール"
ms.assetid: ad589b9f-a3fd-4820-bf1f-6b1965997e68
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# リッチ エディット コントロールの概要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!IMPORTANT]
>  ダイアログ ボックスのリッチ エディット コントロールをアプリケーションが SDI、MDI、ダイアログ ベースかどうかに関係なく、\(\) を使用すると、ダイアログ ボックスが表示される前に [AfxInitRichEdit](../Topic/AfxInitRichEdit.md) を一度呼び出す必要があります。  この関数を呼び出す一般的な場所は、プログラムの `InitInstance` のメンバー関数です。  ダイアログ ボックスを表示するたびに、まずだけに呼び出す必要はありません。  `CRichEditView`を使用して `AfxInitRichEdit` を呼び出す必要はありません。  
  
 リッチ エディット コントロール \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\)、テキストの書式設定にプログラミング インターフェイスを提供します。  ただし、アプリケーションでは、書式設定操作をユーザーが使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装しなければなりません。  つまり、リッチ エディット コントロールは選択した文字や段落の属性を変更することができます。  文字属性の例は太字、斜体、フォント ファミリ ポイント サイズです。  段落の属性の例については、" Alignment タブ ストップが含まれます。  ただし、ユーザー インターフェイスを提供するために、ツール バー ボタン、メニュー項目、または書式指定文字ダイアログ ボックスかどうかです。  また、現在の選択の属性のリッチ エディット コントロールを呼び出す関数があります。  選択に太字の文字書式属性があるコマンド UI にチェック マークを設定する属性の現在の設定を表示するには、これらの関数が存在する場合に使用します。  
  
 文字および段落の書式設定の詳細については、このトピックの [文字書式](../mfc/character-formatting-in-rich-edit-controls.md) と [段落書式](../Topic/Paragraph%20Formatting%20in%20Rich%20Edit%20Controls.md) を後で参照します。  
  
 リッチ エディット コントロールを使用して複数行エディット コントロールで操作と通知メッセージのほとんどをサポートします。  したがって、既にエディット コントロールを使用するアプリケーションは、リッチ エディット コントロールに簡単に変更できます。  追加のメッセージと呼ばれ、アプリケーションが一意のリッチ エディット コントロールの機能にアクセスできるようにします。  エディット コントロールについては、[CEdit](../Topic/CEdit%20Class.md)を参照してください。  
  
 通知の詳細については、このトピックの [リッチ エディット コントロールからの通知](../mfc/notifications-from-a-rich-edit-control.md) を後で参照します。  
  
## 参照  
 [CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)   
 [コントロール](../mfc/controls-mfc.md)