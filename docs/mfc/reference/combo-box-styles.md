---
title: "コンボ ボックス スタイル | Microsoft Docs"
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
  - "CBS_LOWERCASE"
  - "CBS_SORT"
  - "CBS_OWNERDRAWVARIABLE"
  - "CBS_OEMCONVERT"
  - "CBS_AUTOHSCROLL"
  - "CBS_NOINTEGRALHEIGHT"
  - "CBS_SIMPLE"
  - "CBS_DROPDOWNLIST"
  - "CBS_DROPDOWN"
  - "CBS_UPPERCASE"
  - "CBS_HASSTRINGS"
  - "CBS_DISABLENOSCROLL"
  - "CBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBS_OWNERDRAWVARIABLE 定数"
  - "CBS_NOINTEGRALHEIGHT 定数"
  - "CBS_SIMPLE 定数"
  - "CBS_AUTOHSCROLL 定数"
  - "CBS_OEMCONVERT 定数"
  - "CBS_DISABLENOSCROLL 定数"
  - "CBS_HASSTRINGS 定数"
  - "CBS_LOWERCASE 定数"
  - "CBS_SORT 定数"
  - "CBS_DROPDOWN 定数"
  - "CBS_OWNERDRAWFIXED 定数"
  - "コンボ ボックス, スタイル"
  - "CBS_UPPERCASE 定数"
  - "CBS_DROPDOWNLIST 定数"
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コンボ ボックス スタイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC では、次のコンボ ボックス スタイルを使用できます。  
  
-   **CBS\_AUTOHSCROLL** ユーザーが行の末尾に文字を入力したときに、編集コントロール内のテキストを自動的に右方向にスクロールします。 このスタイルが設定されていないと、四角形境界内に収まる長さのテキストしか入力できません。  
  
-   **CBS\_DISABLENOSCROLL** リスト ボックス内の項目が少なく、スクロールする必要がない場合、垂直スクロール バーを使用できない状態で表示します。 このスタイルが設定されていないと、項目が少なくてスクロールする必要がない場合、スクロール バーは表示されません。  
  
-   **CBS\_DROPDOWN CBS\_SIMPLE** と似ていますが、リスト ボックスは、ユーザーが編集コントロールの横にあるアイコンを選択しないと表示されません。  
  
-   **CBS\_DROPDOWNLIST CBS\_DROPDOWN** と似ていますが、編集コントロールは、リスト ボックス内で現在選択されている項目を表示する静的なテキスト項目で置き換えられます。  
  
-   **CBS\_HASSTRINGS** オーナー描画コンボ ボックスには、文字列で構成される項目が格納されています。 コンボ ボックスは文字列に割り当てるメモリやポインターを維持するため、アプリケーションで、`GetText` メンバー関数を使用して特定の項目のテキストを取得できます。  
  
-   **CBS\_LOWERCASE** 選択フィールドとリスト両方のすべてのテキストを小文字に変換します。  
  
-   **CBS\_NOINTEGRALHEIGHT** コンボ ボックスのサイズが、そのコンボ ボックスがアプリケーションによって作成されたときの指定サイズと同じになるように指定します。 通常、コンボ ボックスのサイズは、すべての項目が表示されるように Windows によって調整されます。  
  
-   **CBS\_OEMCONVERT** コンボ ボックス編集コントロールに入力されたテキストを、ANSI 文字セットから OEM 文字セットに変換し、その後、ANSI 文字セットに戻します。 これにより、アプリケーションが Windows 関数 `AnsiToOem` を呼び出してコンボ ボックス内の ANSI 文字列を OEM 文字に変換するときに、文字変換が適切に実行されます。 このスタイルは、ファイル名を保持するコンボ ボックスで使用するときに役立ちます。また、**CBS\_SIMPLE** スタイルまたは **CBS\_DROPDOWN** スタイルで作成されたコンボ ボックスにのみ適用されます。  
  
-   **CBS\_OWNERDRAWFIXED** リスト ボックスのオーナーが、そのリスト ボックスの内容を描画します。リスト ボックス内の項目は、すべて同じ高さで描画されます。  
  
-   **CBS\_OWNERDRAWVARIABLE** リスト ボックスのオーナーが、そのリスト ボックスの内容を描画します。リスト ボックス内の項目の高さは固定されません。  
  
-   **CBS\_SIMPLE** リスト ボックスが常に表示されます。 編集コントロールには、リスト ボックス内で現在選択されている項目が表示されます。  
  
-   **CBS\_SORT** リスト ボックスに入力された文字列を自動的に並べ替えます。  
  
-   **CBS\_UPPERCASE** 選択フィールドとリスト両方のすべてのテキストを大文字に変換します。  
  
## 参照  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create](../Topic/CComboBox::Create.md)   
 [Combo Box Styles](_win32_combo_box_styles)