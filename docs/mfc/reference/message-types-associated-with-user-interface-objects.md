---
title: "ユーザー インターフェイス オブジェクトに関連付けられたメッセージ | Microsoft Docs"
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
  - "vc.codewiz.uiobject.msgs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メッセージ タイプとユーザー インターフェイス オブジェクト"
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ユーザー インターフェイス オブジェクトに関連付けられたメッセージ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

処理できるオブジェクトの種類とそれに対応するメッセージを次の表に示します。  
  
### ユーザー インターフェイス オブジェクトおよび対応するメッセージ  
  
|オブジェクト ID|メッセージ|  
|---------------|-----------|  
|含まれるウィンドウを表すクラス名|[CWnd](../Topic/CWnd%20Class.md) の派生クラス \(ダイアログ ボックス、ウィンドウ、子ウィンドウ、MDI 子ウィンドウ、または最上位のフレーム ウィンドウ\) に対応する Windows メッセージ|  
|メニュー識別子またはアクセラレータ識別子|-   **COMMAND** メッセージ \(プログラムの関数を実行\)<br />-   **UPDATE\_COMMAND\_UI** メッセージ \(メニュー項目を動的に更新\)|  
|コントロール識別子|選択したコントロールの種類に対応するコントロール通知メッセージ|  
  
## 参照  
 [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)