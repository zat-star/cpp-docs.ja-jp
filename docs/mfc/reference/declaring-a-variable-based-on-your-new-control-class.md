---
title: "新しいコントロール クラスに基づいた変数の宣言 | Microsoft Docs"
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
  - "vc.codewiz.classes.control.variable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], 宣言 (クラスをベースに変数を)"
  - "コントロール クラス, 変数"
  - "変数, コントロール クラス"
ms.assetid: 5722dc38-c0eb-40bd-93da-67a808140d03
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 新しいコントロール クラスに基づいた変数の宣言
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC コントロール クラスを作成したら、そのクラスに基づく変数を宣言できます。  新しい変数のコンテキストを用意するには、ダイアログ エディターを開き、再利用可能なコントロールを使用するダイアログ ボックスを編集します。  このダイアログ ボックスには、あらかじめクラスを関連付けておく必要があります。  ダイアログ エディターを使用する方法については、「[ダイアログ エディター](../../mfc/dialog-editor.md)」を参照してください。  
  
### 再利用可能なクラスに基づいた変数を宣言するには  
  
1.  ダイアログ ボックスの編集時に、新しいコントロールの基本クラスと同じ種類のコントロールを \[コントロール\] ツール バーからダイアログ ボックスにドラッグします。  
  
2.  ドロップしたコントロールにマウス ポインターを置きます。  
  
3.  Ctrl キーを押しながらコントロールをダブルクリックします。  
  
     [&#91;メンバー変数の追加&#93;](../../ide/add-member-variable-wizard.md) ダイアログ ボックスが表示されます。  
  
4.  \[アクセス\] ボックスの一覧で、コントロールの適切なアクセスを選択します。  
  
5.  \[コントロール変数\] チェック ボックスをオンにします。  
  
6.  \[変数名\] ボックスに名前を入力します。  
  
7.  \[カテゴリ\] の \[コントロール\] をクリックします。  
  
8.  \[コントロール ID\] ボックスの一覧で、追加したコントロールを選択します。  \[変数の種類\] ボックスの一覧に適切な変数型が表示され、\[コントロールの種類\] ボックスの一覧に適切なコントロールの種類が表示されます。  
  
9. コードに表示するコメントを \[コメント\] ボックスに追加します。  
  
10. \[OK\] をクリックします。  
  
## 参照  
 [関数へのメッセージの割り当て](../Topic/Mapping%20Messages%20to%20Functions.md)   
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー関数の追加](../../ide/adding-a-member-function-visual-cpp.md)   
 [メンバー変数の追加](../../ide/adding-a-member-variable-visual-cpp.md)   
 [仮想関数のオーバーライド](../Topic/Overriding%20a%20Virtual%20Function%20\(Visual%20C++\).md)   
 [MFC メッセージ ハンドラー](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../../ide/navigating-the-class-structure-visual-cpp.md)