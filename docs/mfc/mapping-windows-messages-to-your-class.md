---
title: "ダイアログ クラスと Windows メッセージの対応 | Microsoft Docs"
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
  - "マップ, メッセージ (ダイアログ クラスに)"
  - "メッセージ マップ [C++], ダイアログ クラスで"
  - "メッセージ マップ [C++], マップ (クラスに Windows メッセージを)"
  - "メッセージ (ダイアログ クラスに)"
  - "メッセージ (ダイアログ クラスに), マップ"
  - "MFC ダイアログ ボックス, Windows メッセージ"
  - "Windows メッセージ [C++], マップ (ダイアログ クラスでの)"
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ダイアログ クラスと Windows メッセージの対応
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスは、Windows メッセージを処理することが必要な場合は、適切なハンドラー関数をオーバーライドします。  そのためには、ダイアログ クラスに [メッセージを割り当てます。](../Topic/Mapping%20Messages%20to%20Functions.md) にプロパティ ウィンドウを使用します。  これは、メッセージごとにメッセージ マップのエントリを作成し、そのクラスにメッセージ ハンドラー メンバー関数を追加します。  メッセージ ハンドラーにコードを記述する Visual C\+\+ ソース・コード エディターを使用します。  
  
 また [CDialog](../mfc/reference/cdialog-class.md) と基本クラス、特に [CWnd](../Topic/CWnd%20Class.md)のメンバー関数をオーバーライドします。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [メッセージの処理とマップ](../mfc/message-handling-and-mapping.md)  
  
-   [一般的にオーバーライドされるメンバー関数](../mfc/commonly-overridden-member-functions.md)  
  
-   [通常追加されるメンバー関数](../Topic/Commonly%20Added%20Member%20Functions.md)  
  
## 参照  
 [ダイアログ ボックス](../mfc/dialog-boxes.md)   
 [ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)