---
title: "コンボ ボックス スタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBS_LOWERCASE
- CBS_SORT
- CBS_OWNERDRAWVARIABLE
- CBS_OEMCONVERT
- CBS_AUTOHSCROLL
- CBS_NOINTEGRALHEIGHT
- CBS_SIMPLE
- CBS_DROPDOWNLIST
- CBS_DROPDOWN
- CBS_UPPERCASE
- CBS_HASSTRINGS
- CBS_DISABLENOSCROLL
- CBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- CBS_OWNERDRAWVARIABLE constant
- CBS_NOINTEGRALHEIGHT constant
- CBS_SIMPLE constant
- CBS_AUTOHSCROLL constant
- CBS_OEMCONVERT constant
- CBS_DISABLENOSCROLL constant
- CBS_HASSTRINGS constant
- CBS_LOWERCASE constant
- CBS_SORT constant
- CBS_DROPDOWN constant
- CBS_OWNERDRAWFIXED constant
- combo boxes, styles
- CBS_UPPERCASE constant
- CBS_DROPDOWNLIST constant
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 57069f6e6cd0999773ab3872e671a65e1e880bba
ms.lasthandoff: 02/24/2017

---
# <a name="combo-box-styles"></a>コンボ ボックス スタイル
MFC では、次のコンボ ボックス スタイルを使用できます。  
  
-   **CBS_AUTOHSCROLL** ユーザーが行の末尾に文字を入力したときに、編集コントロール内のテキストを自動的に右方向にスクロールします。 このスタイルが設定されていないと、四角形境界内に収まる長さのテキストしか入力できません。  
  
-   **CBS_DISABLENOSCROLL** リスト ボックス内の項目が少なく、スクロールする必要がない場合、垂直スクロール バーを使用できない状態で表示します。 このスタイルが設定されていないと、項目が少なくてスクロールする必要がない場合、スクロール バーは表示されません。  
  
-   **CBS_DROPDOWN**   **CBS_SIMPLE**と似ていますが、リスト ボックスは、ユーザーが編集コントロールの横にあるアイコンを選択しないと表示されません。  
  
-   **CBS_DROPDOWNLIST**   **CBS_DROPDOWN**と似ていますが、編集コントロールは、リスト ボックス内で現在選択されている項目を表示する静的なテキスト項目で置き換えられます。  
  
-   **CBS_HASSTRINGS** オーナー描画コンボ ボックスには、文字列で構成される項目が格納されています。 コンボ ボックスは文字列に割り当てるメモリやポインターを維持するため、アプリケーションで、 `GetText` メンバー関数を使用して特定の項目のテキストを取得できます。  
  
-   **CBS_LOWERCASE** 選択フィールドとリスト両方のすべてのテキストを小文字に変換します。  
  
-   **CBS_NOINTEGRALHEIGHT** コンボ ボックスのサイズが、そのコンボ ボックスがアプリケーションによって作成されたときの指定サイズと同じになるように指定します。 通常、コンボ ボックスのサイズは、すべての項目が表示されるように Windows によって調整されます。  
  
-   **CBS_OEMCONVERT** コンボ ボックス編集コントロールに入力されたテキストを、ANSI 文字セットから OEM 文字セットに変換し、その後、ANSI 文字セットに戻します。 これにより、アプリケーションが Windows 関数 `AnsiToOem` を呼び出してコンボ ボックス内の ANSI 文字列を OEM 文字に変換するときに、文字変換が適切に実行されます。 このスタイルは、ファイル名を保持するコンボ ボックスで使用するときに役立ちます。また、 **CBS_SIMPLE** スタイルまたは **CBS_DROPDOWN** スタイルで作成されたコンボ ボックスにのみ適用されます。  
  
-   **CBS_OWNERDRAWFIXED** リスト ボックスのオーナーが、そのリスト ボックスの内容を描画します。リスト ボックス内の項目は、すべて同じ高さで描画されます。  
  
-   **CBS_OWNERDRAWVARIABLE** リスト ボックスのオーナーが、そのリスト ボックスの内容を描画します。リスト ボックス内の項目の高さは固定されません。  
  
-   **CBS_SIMPLE** リスト ボックスが常に表示されます。 編集コントロールには、リスト ボックス内で現在選択されている項目が表示されます。  
  
-   **CBS_SORT** リスト ボックスに入力された文字列を自動的に並べ替えます。  
  
-   **CBS_UPPERCASE** 選択フィールドとリスト両方のすべてのテキストを大文字に変換します。  
  
## <a name="see-also"></a>関連項目  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create](ccombobox class.md # ccombobox__create   




