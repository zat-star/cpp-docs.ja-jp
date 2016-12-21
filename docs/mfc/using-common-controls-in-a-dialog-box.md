---
title: "ダイアログ ボックスでのコモン コントロールの使い方 | Microsoft Docs"
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
  - "コモン コントロール [C++], ダイアログ ボックスで"
  - "ダイアログ ボックス コントロール [C++], コモン コントロール"
  - "Windows コモン コントロール [C++], ダイアログ ボックスで"
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ダイアログ ボックスでのコモン コントロールの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows コモン コントロールは [ダイアログ ボックス](../mfc/dialog-boxes.md)、フォーム ビュー、レコード ビュー、およびダイアログ テンプレートに基づく他のウィンドウで使用できます。  次の手順は、軽微な変更を伴ってフォームでは、同じように動作します。  
  
## 手順  
  
#### コモン コントロールをダイアログ ボックスに使用します。  
  
1.  ダイアログ テンプレート [ダイアログ エディターを使用する](../mfc/using-the-dialog-editor-to-add-controls.md)にコントロールを配置します。  
  
2.  ダイアログ クラスにコントロールを表すメンバー変数を追加します。  **メンバー変数の追加** ダイアログ ボックスで、**コントロール変数\(O\)** を確認し、**コントロールカテゴリ**がオンになっていることを確認します。  
  
3.  このコモン コントロールがプログラムに入力を提供し、それらの入力値を処理すると、ダイアログ クラスの追加のメンバー変数を宣言します。  
  
    > [!NOTE]
    >  クラス ビューでコンテキスト メニューを使用してこれらのメンバー変数を追加できます。[メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)を参照してください。  
  
4.  ダイアログ クラスの [OnInitDialog](../Topic/CDialog::OnInitDialog.md) のコモン コントロールの最初の条件を設定します。  前の手順で作成したメンバー変数を使用して初期値とそのほかの設定を設定するには、メンバー関数を使用します。  設定の詳細については、"コントロールの次の説明を参照してください。  
  
     また、ダイアログ ボックスのコントロールを初期化するために [ダイアログ データ エクスチェンジ \(DDX\)](../mfc/dialog-data-exchange-and-validation.md) \(DDX\) を使用できます。  
  
5.  ダイアログ ボックスのコントロールのハンドラーでは、コントロールを操作するときにメンバー変数を使用します。  メソッドの詳細については、"コントロールの次の説明を参照してください。  
  
    > [!NOTE]
    >  メンバー変数はダイアログ ボックス自体がある場合のみです。  ダイアログ ボックスを閉じた後に値を入力するためのコントロールを呼び出されません。  コモン コントロールからの入力値を使用するには、ダイアログ クラスの `OnOK` をオーバーライドします。  このオーバーライドでは、値を入力するためのコントロールを呼び出し、ダイアログ クラスのメンバー変数にこれらの値を格納します。  
  
    > [!NOTE]
    >  やデータ交換ダイアログ ボックスのコントロールの値を設定または取得するためにダイアログを使用できます。  
  
## 解説  
 ダイアログ ボックスにあるコモン コントロールの追加とダイアログ ボックスは機能します。  この状況の処理の詳細については [Adding Controls to a Dialog Causes the Dialog to No Longer Function](../mfc/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) "を参照してください。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [ダイアログ エディターで、ダイアログ ボックスにコントロールを手動で追加します。](../mfc/adding-controls-by-hand.md)  
  
-   [標準の Windows コモン コントロールの 1 つがから次のコントロールを派生してください。](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [子ウィンドウとしてコモン コントロールを使用します。](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [コントロールからの通知メッセージを受け取ります。](../Topic/Receiving%20Notification%20from%20Common%20Controls.md)  
  
-   [ダイアログ データ エクスチェンジを使用します \(DDX\)](../mfc/dialog-data-exchange-and-validation.md)  
  
## 参照  
 [コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)