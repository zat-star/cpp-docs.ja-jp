---
title: "Creating a New Toolbar Button | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.toolbar"
dev_langs: 
  - "C++"
  - "C++"
helpviewer_keywords: 
  - "Toolbar editor, creating buttons"
  - "toolbar buttons (in Toolbar editor), button image"
  - "toolbar buttons (in Toolbar editor), creating"
  - "toolbar buttons (in Toolbar editor)"
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a New Toolbar Button
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### ツール バー ボタンを新規作成するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、リソース フォルダー \(\[Project1.rc\] など\) を展開します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  \[Toolbar\] フォルダーを展開し、編集するツール バーを選択します。  
  
3.  ツール バーの右端にある空白のボタンに ID を割り当てます。  この作業は [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)の \[ID\] プロパティを編集して行います。  たとえば、ツール バー ボタンにメニュー オプションと同じ ID を割り当てたい場合。  この場合は、ドロップダウン リストでメニュー オプションの ID を選択します。  
  
     または  
  
     ツール バー ビューのペインで、ツール バーの右端にある空白のボタンを選択し、描画を開始します。  既定のボタン コマンド ID が割り当てられます \(ID\_BUTTON\<n\>\)。  
  
 また、イメージを切り取り、新しいボタンとしてツール バーに貼り付けることもできます。  
  
#### イメージをボタンとしてツール バーに追加するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、ツール バーをダブルクリックして開きます。  
  
2.  ツール バーに追加するイメージを開きます。  
  
    > [!NOTE]
    >  Visual Studio では、イメージがイメージ エディターで開かれます。  グラフィック関連のほかのプログラムでイメージを開くこともできます。  
  
3.  \[編集\] メニューの \[コピー\] をクリックします。  
  
4.  ソース ウィンドウの上部の該当するタブをクリックして、そのツール バーに切り替えます。  
  
5.  \[編集\] メニューの \[貼り付け\] をクリックします。  
  
     イメージがツール バーの新しいボタンとして表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
### 要件  
 MFC または ATL  
  
## 参照  
 [Toolbar Button Properties](../mfc/toolbar-button-properties.md)   
 [Creating, Moving, and Editing Toolbar Buttons](../mfc/creating-moving-and-editing-toolbar-buttons.md)   
 [Toolbar Editor](../mfc/toolbar-editor.md)