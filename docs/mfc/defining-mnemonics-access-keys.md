---
title: "Defining Mnemonics (Access Keys) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "access keys [C++], adding"
  - "keyboard shortcuts [C++], controls"
  - "dialog box controls, mnemonics"
  - "access keys [C++], checking"
  - "mnemonics, checking for duplicate"
  - "mnemonics"
  - "mnemonics, dialog box controls"
  - "keyboard shortcuts [C++], uniqueness checking"
  - "Check Mnemonics command"
  - "controls [C++], access keys"
  - "access keys [C++]"
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Defining Mnemonics (Access Keys)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

通常、キーボード ユーザーはダイアログ ボックス内のコントロール間で入力フォーカスを移動するときに、**Tab** キーと方向キーを使用します。  ユーザーがキーを 1 つ押してコントロールを選択できるように、アクセス キー \(ニーモニックまたは覚えやすい名前\) を定義できます。  
  
### 可視のキャプションを持つコントロール \(プッシュ ボタン、チェック ボックス、オプション ボタン\) のアクセス キーを定義するには  
  
1.  ダイアログ ボックス内のコントロールを選択します。  
  
2.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)の \[Caption\] プロパティに、新しいコントロールの名前を入力します。そのコントロールのアクセス キーにする文字の前にはアンパサンド \(&\) を付けます。  たとえば、`&Radio1` のようにします。  
  
3.  **Enter** キーを押します。  
  
     表示されるキャプションには、**R**adio1 のように、アクセス キーを示す下線が表示されます。  
  
### 可視のキャプションを持たないコントロールのアクセス キーを定義するには  
  
1.  [&#91;ツールボックス&#93; ウィンドウ](../Topic/Toolbox.md)の静的テキスト コントロールを使用して、コントロールのキャプションを作成します。  
  
2.  静的テキストのキャプションで、アクセス キーにする文字の前にアンパサンド \(&\) を入力します。  
  
3.  静的テキスト コントロールが、タブ オーダーでラベルとなるコントロールの直前にあることを確認します。  
  
 ダイアログ ボックス内のすべてのアクセス キーを一意にする必要があります。  
  
#### 重複するアクセス キーの有無をチェックするには  
  
1.  \[書式\] メニューの \[ニーモニックの確認\] をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
### 要件  
 Win32  
  
## 参照  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)