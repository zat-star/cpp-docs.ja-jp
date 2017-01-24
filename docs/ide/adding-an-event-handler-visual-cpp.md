---
title: "イベント ハンドラーの追加 (Visual C++) | Microsoft Docs"
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
  - "イベント ハンドラー, 追加"
  - "MSBuild, プロパティ"
  - "プロパティ [Visual Studio], MSBuild"
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# イベント ハンドラーの追加 (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソース エディターから、[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)を使用して、ダイアログ ボックス コントロールに新規イベント ハンドラーを追加したり、既存のイベント ハンドラーを編集したりできます。  
  
 [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)を使用すると、ダイアログ ボックスを実装するクラスにイベントを追加できます。  ダイアログ ボックス クラス以外のクラスにイベントを追加するには、イベント ハンドラー ウィザードを使用します。  
  
### ダイアログ ボックス コントロールにイベント ハンドラーを追加するには  
  
1.  [&#91;リソース ビュー&#93;](../windows/resource-view-window.md) でダイアログ ボックスのリソースをダブルクリックし、コントロールを含むダイアログ ボックスのリソースを[ダイアログ エディター](../mfc/dialog-editor.md)で開きます。  
  
2.  通知されたイベントを処理するコントロールを右クリックします。  
  
3.  ショートカット メニューの **\[イベント ハンドラーの追加\]** をクリックし、イベント ハンドラー ウィザードを表示します。  
  
4.  \[メッセージの種類\] ボックスからイベントを選択し、\[クラスの一覧\] ボックスに追加します。  
  
5.  \[関数ハンドラー名\] ボックスで、既定の名前を受け入れるか、または任意の名前を指定します。  
  
6.  \[追加して編集\] をクリックして、イベント ハンドラーをプロジェクトに追加して新しい関数をテキスト エディターで開いたら、適切なイベント ハンドラーのコードを追加します。  
  
     選択したメッセージ タイプに選択したクラスのイベント ハンドラーが既に存在した場合は、\[追加して編集\] は無効です。この場合は \[コードを編集\] が有効になります。  \[コードを編集\] をクリックすると、テキスト エディターで既存の関数が開きます。  
  
 [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)でイベント ハンドラーを追加することもできます。  詳細については、「[ダイアログ ボックス コントロールへのイベント ハンドラーの追加](../mfc/adding-event-handlers-for-dialog-box-controls.md)」を参照してください。  
  
## 参照  
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)   
 [メンバー関数の追加](../ide/adding-a-member-function-visual-cpp.md)   
 [MFC メッセージ ハンドラー](../mfc/reference/adding-an-mfc-message-handler.md)   
 [クラス各部へのジャンプ](../ide/navigating-the-class-structure-visual-cpp.md)