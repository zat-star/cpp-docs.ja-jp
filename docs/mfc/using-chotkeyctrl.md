---
title: "CHotKeyCtrl の使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CHotKeyCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHotKeyCtrl クラス, 使用"
  - "ホット キー コントロール"
  - "キー, ホットと CHotKeyCtrl"
ms.assetid: 9b207117-d848-4224-8888-c3d197bb0c95
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CHotKeyCtrl の使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)クラスによって表されるホット キー コントロールは、キーの組み合わせを表すテキストをユーザー定義型表示する CTRL\+SHIFT\+Q.などのウィンドウです。  また、フラグの仮想キー コードと Shift キーの状態を表す一連の形でこのキーの内部表現を保持します。  ホット キー コントロールは実際にはホット キーを設定していません。そのため、プログラムによって異なります。\(標準の仮想キー コードの一覧については、" Winuser.h を参照してください\)。  
  
 ウィンドウまたはスレッドに関連付けるどのホット キーを使用して、ユーザーが入力できるようにするためにホット キー コントロールを示します。  ホット キー コントロールは、ホット キーを割り当てるようにユーザーに要求するときなど、ダイアログ ボックスで使用されて表示される可能性があります。  これは、ホット キーを表す値がホット キー コントロールから取得し、ウィンドウまたはスレッドとホット キーを関連付けるには、適切な関数を呼び出すプログラムが行います。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [ホット キー コントロールを使用する](../Topic/Using%20a%20Hot%20Key%20Control.md)  
  
-   [ホット キーの設定](../Topic/Setting%20a%20Hot%20Key.md)  
  
-   [グローバルのホット キー](../Topic/Global%20Hot%20Keys.md)  
  
-   [スレッド固有のホット キー](../Topic/Thread-Specific%20Hot%20Keys.md)  
  
## 参照  
 [コントロール](../mfc/controls-mfc.md)