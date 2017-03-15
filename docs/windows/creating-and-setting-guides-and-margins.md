---
title: "Creating and Setting Guides and Margins | Microsoft Docs"
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
  - "guides, clearing"
  - "guides"
  - "Dialog editor, guides and margins"
  - "dialog box controls, placement"
  - "controls [C++], guides and margins"
  - "guides, creating"
  - "guides, moving"
  - "margins, moving"
ms.assetid: fafa4545-8f00-436f-b590-300e76601156
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Creating and Setting Guides and Margins
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コントロールの移動および追加、または現在のレイアウトの再配置を行うときは、ガイドを使用すると、ダイアログ ボックス内でコントロールを正確に配置できます。  ガイドは、エディターに表示されたダイアログ ボックス上の青い点線と、ルーラーの対応する矢印で \(ダイアログ エディターの最上部と左側に沿って\) 表示されます。  
  
 ダイアログ ボックスの作成時には、4 つのマージンが表示されます。  マージンとは、青の点線で表示される変更済みのガイドです。  
  
### ガイドを作成するには  
  
1.  ルーラー内の任意の場所を 1 回クリックして、ガイドを作成します。  1 回クリックするとガイドが新規作成されます。ダブルクリックすると [&#91;ガイドの設定&#93; ダイアログ ボックス](../Topic/Guide%20Settings%20Dialog%20Box.md)が起動し、ガイドの設定を指定できます。  
  
### ガイドを設定するには  
  
1.  ダイアログ ボックスでガイドをクリックし、新しい位置にドラッグします。  ルーラーの矢印をクリックして、関連付けられたガイドをドラッグすることもできます。  
  
     ガイドの座標は、ウィンドウの下部にあるステータス バーとルーラーに表示されます。  ポインターをルーラーの矢印の上に移動すると、ガイドの正確な位置が表示されます。  
  
### ガイドを削除するには  
  
1.  ガイドをダイアログ ボックスの外側にドラッグします。  
  
 または  
  
-   対応する矢印をルーラーの外にドラッグします。  
  
#### マージンを移動するには  
  
1.  マージンを新しい位置にドラッグします。  
  
     マージンを非表示にするには、マージンを 0 の位置に移動します。  マージンを元に戻すには、ポインターをマージンの 0 の位置に置き、マージンを元の位置に戻します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
### 要件  
 Win32  
  
## 参照  
 [Dialog Editor States \(Guides and Grids\)](../mfc/dialog-editor-states-guides-and-grids.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)