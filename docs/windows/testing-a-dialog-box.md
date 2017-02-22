---
title: "Testing a Dialog Box | Microsoft Docs"
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
  - "Test Dialog command"
  - "testing, dialog boxes"
  - "dialog boxes, testing"
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Testing a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ ボックスを設計する際には、プログラムをコンパイルせずに実行時の動作をシミュレートし、テストできます。 このモードでは、次を行うことができます。  
  
-   テキストの入力、コンボ ボックスの一覧での選択、オプションのオンとオフの切り替え、コマンドの選択。  
  
-   タブ オーダーのテスト。  
  
-   オプション ボタンやチェック ボックスなど、コントロールのグループ化のテスト。  
  
-   ダイアログ ボックスにあるコントロールのキーボード ショートカットのテスト。  
  
    > [!NOTE]
    >  ウィザードを使用したダイアログ ボックスのコードへの接続は、シミュレーションに含まれません。  
  
 通常、テストするダイアログ ボックスはメイン プログラム ウィンドウの相対位置に表示されます。 ダイアログ ボックスの \[Absolute Align\] を \[True\] に設定している場合、ダイアログ ボックスは画面の左上隅の相対位置に表示されます。  
  
### ダイアログ ボックスをテストするには  
  
1.  ダイアログ エディターがアクティブなウィンドウである場合は、メニュー バーの **\[書式\]**、**\[ダイアログのテスト\]** をクリックします。  
  
2.  シミュレーションを終了するには、Esc キーを押すか、またはテストしているダイアログ ボックスの **\[閉じる\]** をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、「[デスクトップ アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」をご覧ください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Dialog Editor](../mfc/dialog-editor.md)   
 [\[ダイアログ エディター\] ツール バーの表示と非表示](../Topic/Showing%20or%20Hiding%20the%20Dialog%20Editor%20Toolbar.md)