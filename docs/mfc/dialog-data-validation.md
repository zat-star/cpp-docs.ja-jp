---
title: "ダイアログ データ バリデーション | Microsoft Docs"
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
  - "データの妥当性検査 [C++], ダイアログ ボックス"
  - "データの妥当性検査 [C++], メッセージ ボックス"
  - "DDV (ダイアログ データ バリデーション) [C++]"
  - "ダイアログ ボックス [C++], 検証 (データを)"
  - "妥当性検査 (データを) [C++], ダイアログ ボックスのデータ入力"
  - "妥当性検査 (データを) [C++], メッセージ ボックス"
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ダイアログ データ バリデーション
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データ交換に加えて [ダイアログ データ エクスチェンジ \(DDX\)](../mfc/dialog-data-exchange.md)の例に示すように、DDV 関数を呼び出して検証を指定できます。  例の `DDV_MaxChars` の呼び出しは、テキスト ボックス コントロールに入力された文字列の長さが 20 文字以下であることを検証します。  DDV 関数は、検証が問題となっているコントロールにフォーカスをユーザーがデータを入力できる場合は失敗し、メッセージ ボックスを表示してユーザーに警告します。  指定したコントロールの DDV 関数は同じコントロールの DDX 関数の直後に呼び出す必要があります。  
  
 また、DDV DDX 独自のカスタム ルーチンを定義できます。  これで、DDX と DDV の他の要素については、[MFC のテクニカル ノート 26](../mfc/tn026-ddx-and-ddv-routines.md)を参照してください。  
  
 [メンバー変数の追加](../ide/add-member-variable-wizard.md) はデータ マップするための DDX と DDV すべての呼び出しを作成します。  
  
## 参照  
 [ダイアログ データ エクスチェンジとダイアログ データ バリデーション](../mfc/dialog-data-exchange-and-validation.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)   
 [ダイアログ データ エクスチェンジ](../mfc/dialog-data-exchange.md)