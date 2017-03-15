---
title: "モーダルとモードレスのダイアログ ボックス | Microsoft Docs"
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
  - "MFC ダイアログ ボックス, モーダル"
  - "MFC ダイアログ ボックス, モードレス"
  - "モーダル ダイアログ ボックス"
  - "モードレス ダイアログ ボックス"
ms.assetid: e83df336-5994-4b8f-8233-7942f997315b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# モーダルとモードレスのダイアログ ボックス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 種類のダイアログ ボックスを管理するために [CDialog](../mfc/reference/cdialog-class.md) クラスを使用する場合:  
  
-   ユーザーがプログラムを続行に反応するように要求する*モーダル ダイアログ ボックス*、  
  
-   画面になり、使用のためにいつでも使用できる他のユーザー操作を割り当てます*モードレス ダイアログ ボックスは*  
  
 ダイアログ テンプレートを作成するためのリソースの編集および手順はモーダルおよびモードレス ダイアログ ボックスと同じです。  
  
 プログラムのダイアログ ボックスを作成するには、次の手順が必要です。T:  
  
1.  ダイアログ ボックスを設計し、ダイアログ テンプレート リソースを作成するには [ダイアログ エディター](../mfc/dialog-editor.md) を使用します。  
  
2.  ダイアログ クラスを作成します。  
  
3.  ダイアログ クラスの [メッセージ ハンドラーにダイアログ リソースのコントロール](../mfc/adding-event-handlers-for-dialog-box-controls.md) を接続します。  
  
4.  ダイアログ ボックスのコントロールに関連付けられたデータ メンバーを [ダイアログ データ エクスチェンジ \(DDX\)](../mfc/dialog-data-exchange.md) と [ダイアログ データ検証](../mfc/dialog-data-validation.md) をコントロールに対して指定する追加します。  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)