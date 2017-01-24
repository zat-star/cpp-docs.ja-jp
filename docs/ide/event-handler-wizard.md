---
title: "イベント ハンドラー ウィザード | Microsoft Docs"
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
  - "vc.codewiz.eventhandler.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "イベント ハンドラー ウィザード [C++]"
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イベント ハンドラー ウィザード
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このウィザードでは、ダイアログ ボックス コントロールのイベント ハンドラーを任意のクラスに追加します。  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)でイベント ハンドラーを追加すると、ダイアログ ボックスを実装するクラスだけにイベント ハンドラーが追加されます。  詳細については、「[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../mfc/adding-event-handlers-for-dialog-box-controls.md)」を参照してください。  
  
 **\[コマンド名\]**  
 イベント ハンドラーを追加するコントロールを識別します。  このボックスは使用できません。  
  
 **\[メッセージの種類\]**  
 選択したコントロールで現在使用できるメッセージ ハンドラーを一覧表示します。  
  
 **\[関数ハンドラー名\]**  
 イベントを処理するために追加された関数名を表示します。  既定では、名前はメッセージ タイプとコマンドに基づき、先頭に "On" が付きます。  たとえば、`IDC_BUTTON1` という名前のボタンの場合、メッセージ タイプ `BN_CLICKED` では、関数ハンドラー名 `OnBnClickedButton1` が表示されます。  
  
 **\[クラスの一覧\]**  
 イベント ハンドラーを追加できるクラスを表示します。  選択されたダイアログ ボックスのクラスは赤で表示されます。  
  
 **\[ハンドラーの説明\]**  
 \[メッセージの種類\] ボックスで選択された項目の説明が示されます。  このボックスは使用できません。  
  
 **\[追加して編集\]**  
 選択されたクラスまたはオブジェクトにメッセージ ハンドラーを追加し、コントロール通知ハンドラーのコードを追加できるように、新しい関数をテキスト エディターで開きます。  
  
 **\[コードを編集\]**  
 コントロール通知ハンドラーのコードを追加および編集できるように、選択された既存の関数をテキスト エディターで開きます。  
  
## 参照  
 [イベント ハンドラーの追加](../ide/adding-an-event-handler-visual-cpp.md)