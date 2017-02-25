---
title: "Creating a Tool Tip for a Toolbar Button | Microsoft Docs"
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
  - "tool tips [C++], adding to toolbar buttons"
  - "\n in tool tip"
  - "toolbar buttons [C++], tool tips"
  - "buttons [C++], tool tips"
  - "Toolbar editor, creating tool tips"
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Creating a Tool Tip for a Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### ツール ヒントを作成するには  
  
1.  ツール バー ボタンをクリックします。  
  
2.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)の \[Prompt\] フィールドで、ステータス バーのボタンの説明を追加し、メッセージの後に \\n およびツール ヒント名を追加します。  
  
 ツール ヒントの一般的な例は、ワードパッドの \[印刷\] ボタンです。  
  
 1.  ワードパッドを開きます。  
  
 2.  マウス ポインターをツール バーの \[印刷\] の上に置きます。  
  
 3.  マウス ポインターの下に "印刷" と表示されることに注意してください。  
  
 4.  ワードパッド ウィンドウの最下部にあるステータス バーを見ると、"現在のドキュメントを印刷します" というテキストが表示されていることがわかります。  
  
 手順 3. の "印刷" は「ツール ヒント名」で、手順 4. の "現在のドキュメントを印刷します" は「ステータス バーのボタンの説明」です。  
  
 ツール バー エディターを使用して同じ効果を得るには、\[Prompt\] プロパティを \[作業中のファイルを印刷\\n印刷\] に設定します。  
  
> [!NOTE]
>  プロンプトのテキストは、[&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)を使用して編集できます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 要件  
  
 MFC または ATL  
  
## 参照  
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)