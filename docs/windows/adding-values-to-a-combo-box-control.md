---
title: "Adding Values to a Combo Box Control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.combo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combo boxes [C++], Data property"
  - "controls [Visual Studio], testing values in combo boxes"
  - "combo boxes [C++], adding values"
  - "combo boxes [C++], previewing values"
  - "controls [C++], testing values in combo boxes"
  - "Data property"
  - "combo boxes [C++], testing values"
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Adding Values to a Combo Box Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ダイアログ エディターを開くと、コンボ ボックス コントロールに値を追加できます。  
  
> [!TIP]
>  ダイアログ エディターでコンボ ボックスのサイズを変更する前に、そのボックスにすべての値を追加してください。逆の順序で操作すると、コンボ ボックス コントロールに表示されるテキストが切り捨てられることがあります。  
  
#### コンボ ボックス コントロールに値を入力するには  
  
1.  コンボ ボックス コントロールをクリックして選択します。  
  
2.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で、\[Data\] プロパティまでスクロールします。  
  
    > [!NOTE]
    >  種類別にグループ化されたプロパティを表示している場合、\[Data\] プロパティは \[その他\] プロパティの中にあります。  
  
3.  \[Data\] プロパティの値の領域をクリックし、データ値をセミコロンで区切って入力します。  
  
    > [!NOTE]
    >  空白があるとドロップダウン リストの項目がアルファベット順にならないため、値の間には空白を入れないでください。  
  
4.  値を追加したら、**Enter** キーを押します。  
  
 コンボ ボックスのドロップダウン部分を拡大する方法については、「[コンボ ボックスとドロップダウン リストのサイズの設定](../mfc/setting-the-size-of-the-combo-box-and-its-drop-down-list.md)」を参照してください。  
  
> [!NOTE]
>  Win32 プロジェクトに値を追加する場合は、この手順を使用できません。Win32 プロジェクトでは、\[Data\] プロパティが淡色表示されます。  Win32 プロジェクトにはこの機能を追加するライブラリがないため、コンボ ボックスに値を追加するにはプログラムを使用する必要があります。  
  
#### コンボ ボックスの値の外観をテストするには  
  
1.  \[Data\] プロパティに値を入力した後、[&#91;ダイアログ エディター&#93; ツール バー](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md)の \[ダイアログのテスト\] ボタンをクリックします。  
  
     値リストを下方向にスクロールします。  値は、\[プロパティ\] ウィンドウの \[Data\] プロパティに入力したとおりに表示されます。  スペル チェックや大文字小文字のチェックは行われません。  
  
     **Esc** キーを押してダイアログ エディターに戻ります。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
### 要件  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)