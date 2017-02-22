---
title: "Changing the Tab Order of Controls | Microsoft Docs"
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
  - "controls [C++], tab order"
  - "focus, tab order"
  - "tab controls, tab order"
  - "Tabstop property for controls"
  - "controls [C++], focus"
  - "dialog box controls, tab order"
ms.assetid: e2cee764-4367-42d7-9563-65a68f76f5ff
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Changing the Tab Order of Controls
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

タブ オーダーとは、**Tab** キーを押したときに、ダイアログ ボックス内で入力フォーカスがコントロール間を移動する順序です。  通常、タブ オーダーはダイアログ ボックスの左から右、および上から下の順序になっています。  各コントロールには、コントロールが入力フォーカスを受け取るかどうかを決定する \[TabStop\] プロパティがあります。  
  
### コントロールの入力フォーカスを設定するには  
  
1.  [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)で、\[TabStop\] プロパティを \[True\] または \[False\] に設定します。  
  
 \[TabStop\] プロパティが \[True\] に設定されていないコントロールでも、タブ オーダーに含める必要があります。  これは、キャプションのないコントロールに対して[アクセス キー \(ニーモニック\) を定義する](../mfc/defining-mnemonics-access-keys.md)ときなどに重要になる場合があります。  関連するコントロールに対するアクセス キーを含む静的テキストは、タブ オーダーでそのコントロールの直前に置く必要があります。  
  
> [!NOTE]
>  ダイアログ ボックスでコントロールが重複配置されている場合にタブ オーダーを変更すると、コントロールの表示方法が変更される可能性があります。  タブ オーダーが下位のコントロールは、タブ オーダーが上位の重複配置されているコントロールの上に常に表示されます。  
  
#### ダイアログ ボックスにあるすべてのコントロールの現在のタブ オーダーを表示するには  
  
1.  \[書式\] メニューの \[タブ オーダー\] をクリックします。  
  
 または  
  
-   **Ctrl** キーを押しながら **D** キーを押します。  
  
#### ダイアログ ボックスにあるすべてのコントロールのタブ オーダーを変更するには  
  
1.  \[書式\] メニューの \[タブ オーダー\] をクリックします。  
  
     各コントロールの左上隅にある番号は、現在のタブ オーダーでの位置を示します。  
  
2.  **Tab** キーに対応する順序で各コントロールをクリックして、タブ オーダーを設定します。  
  
3.  Enter キーを押して、タブ オーダー モードを終了します。  
  
    > [!TIP]
    >  タブ オーダー モードでは、Esc キーまたは Enter キーを押すと、タブ オーダーの変更機能を無効にできます。  
  
#### 複数のコントロールのタブ オーダーを変更するには  
  
1.  \[書式\] メニューの \[タブ オーダー\] をクリックします。  
  
2.  順序の変更の開始位置を指定します。  そのためには、**Ctrl** キーを押しながら、変更後の順序の開始位置の直前にあるコントロールをクリックします。  
  
     たとえば、7 ～ 9 のコントロールの順序を変更する場合は、**Ctrl** キーを押しながら最初にコントロール 6 を選択します。  
  
    > [!NOTE]
    >  特定のコントロールを番号 1、つまりタブ オーダーの先頭にするには、そのコントロールをダブルクリックします。  
  
3.  **Ctrl** キーを離し、その位置から **Tab** キーに対応させる順序で各コントロールをクリックします。  
  
4.  Enter キーを押して、タブ オーダー モードを終了します。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[チュートリアル : Windows フォームのローカリゼーション](http://msdn.microsoft.com/ja-jp/9a96220d-a19b-4de0-9f48-01e5d82679e5)」および「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
### 要件  
 Win32  
  
## 参照  
 [Arrangement of Controls on Dialog Boxes](../mfc/arrangement-of-controls-on-dialog-boxes.md)   
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)