---
title: "Changing the Font of Text on an Image (Image Editor for Icons) | Microsoft Docs"
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
  - "C++"
helpviewer_keywords: 
  - "fonts, changing on an image"
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changing the Font of Text on an Image (Image Editor for Icons)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次の操作を行うためには、以下の手順を実行します。  
  
-   Windows アプリケーション内でアイコンにテキストを追加する  
  
-   テキストのフォントを操作する  
  
### イメージのテキストのフォントを変更するには  
  
1.  C\+\+ Windows フォーム アプリケーションを作成します。  詳細については、「[Windows アプリケーション プロジェクトの作成](http://msdn.microsoft.com/ja-jp/b2f93fed-c635-4705-8d0e-cf079a264efa)」を参照してください。  [Windows フォーム アプリケーション テンプレート](http://msdn.microsoft.com/ja-jp/1babdebf-ab3f-4a64-a608-98499a5b9cea)では、既定で app.ico という名前のファイルがプロジェクトに追加されます。  
  
2.  ソリューション エクスプローラーで、app.ico ファイルをダブルクリックします。  [Image Editor](../mfc/image-editor-for-icons.md) が開きます。  
  
3.  \[イメージ\] メニューの \[ツール\] をポイントし、\[テキスト ツール\] をクリックします。  [&#91;テキスト ツール&#93; ダイアログ ボックス](../Topic/Text%20Tool%20Dialog%20Box%20\(Image%20Editor%20for%20Icons\).md)が表示されます。  
  
4.  \[テキスト ツール\] ダイアログ ボックスの空のテキスト領域に「`C++`」と入力します。  このテキストは、イメージ エディター内で、app.ico の左上隅のサイズ変更可能ボックスに表示されます。  
  
5.  イメージ エディター内で、テキストを読みやすくするために、サイズ変更可能ボックスを app.ico の中心に移動します。  
  
6.  \[テキスト ツール\] ダイアログ ボックスの \[フォント\] をクリックします。  [&#91;テキスト ツール フォント&#93; ダイアログ ボックス](../mfc/text-tool-font-dialog-box-image-editor-for-icons.md)が表示されます。  
  
7.  \[テキスト ツール フォント\] ダイアログ ボックスで、使用できるフォントが示された \[フォント\] ボックスの一覧の \[ＭＳ Ｐゴシック\] をクリックします。  
  
8.  使用できるフォント スタイルが示された \[スタイル\] ボックスの一覧の \[太字\] をクリックします。  
  
9. 使用できるポイント サイズが示された \[サイズ\] ボックスの一覧の \[10\] をクリックします。  
  
10. \[OK\] をクリックします。  \[テキスト ツール フォント\] ダイアログ ボックスが閉じ、新しいフォント設定がテキストに適用されます。  
  
11. \[テキスト ツール\] ダイアログ ボックスの \[閉じる\] をクリックします。  イメージエディターのテキストの周囲のサイズ変更可能ボックスの表示が消えます。  
  
## 参照  
 [Editing Graphical Resources](../mfc/editing-graphical-resources-image-editor-for-icons.md)   
 [Toolbar](../mfc/toolbar-image-editor-for-icons.md)