---
title: "エディット スタイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ES_READONLY
- ES_WANTRETURN
- ES_UPPERCASE
- ES_NUMBER
- ES_AUTOHSCROLL
- ES_LOWERCASE
- ES_RIGHT
- ES_MULTILINE
- ES_PASSWORD
- ES_NOHIDESEL
- ES_OEMCONVERT
- ES_LEFT
- ES_CENTER
dev_langs:
- C++
helpviewer_keywords:
- ES_WANTRETURN constant
- edit styles [MFC]
- ES_RIGHT constant
- ES_READONLY constant
- ES_PASSWORD constant
- ES_MULTILINE constant
- ES_LEFT constant
- ES_AUTOVSCROLL constant
- ES_OEMCONVERT constant
- ES_LOWERCASE constant
- ES_NUMBER constant
- ES_UPPERCASE constant
- ES_NOHIDESEL constant
- ES_AUTOHSCROLL constant
- ES_CENTER constant
ms.assetid: e6291dd6-f2cb-4ce2-ac31-32272526625c
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 275e0d2dede038bdbe9061bc8051408442aa70bf
ms.lasthandoff: 02/24/2017

---
# <a name="edit-styles"></a>エディット スタイル
-   **ES_AUTOHSCROLL**ユーザーが行の末尾に文字を入力したときは、10 文字で右側にあるテキストを自動的にスクロールします。 ユーザーが ENTER キーを押すと、コントロールは、0 の位置にすべてのテキストをスクロールします。  
  
-   **ES_AUTOVSCROLL**最後の行で ENTER キーを押したときに、1 ページ上のテキストを自動的にスクロールします。  
  
-   **ES_CENTER**エディット コントロールの&1; 行または複数行の文字列を中央揃えされます。  
  
-   **ES_LEFT**エディット コントロールの単一行または複数行のテキストを左揃えにします。  
  
-   **ES_LOWERCASE**小文字にエディット コントロールに入力されたすべての文字に変換します。  
  
-   **ES_MULTILINE**複数行のエディット コントロールを設定します。 (既定値は、1 行です)。場合、 **ES_AUTOVSCROLL**スタイルが指定されている場合、エディット コントロールは、できるだけ多くの行を表示、ユーザーが ENTER キーを押したときに垂直方向にスクロールします。 場合**ES_AUTOVSCROLL**が指定されていないエディット コントロール数だけ行として表示可能なビープ音が行を表示するときに、入力が押された場合です。 場合、 **ES_AUTOHSCROLL**スタイルを指定すると、複数行のエディット コントロールに自動的に水平方向にスクロールすると、カレットがコントロールの右端。 新しい行を最初に、ユーザーは ENTER キーを押します必要があります。 場合**ES_AUTOHSCROLL**が指定されていないコントロールは、必要な場合に、次の行の先頭に単語を自動的に折り返される; ENTER キーを押した場合にも、新しい行が開始します。 折り返す位置については、ウィンドウのサイズによって決まります。 ウィンドウのサイズが変更された場合は、ワード ラップ位置変更され、テキストが表示されます。 複数行のエディット コントロールでは、スクロール バーを持つことができます。 スクロール バーのあるエディット コントロールでは、独自のスクロール バー メッセージを処理します。 上記で説明したようにスクロール バーのスクロールせずにコントロールを編集し、親ウィンドウによって送信されたスクロール メッセージを処理します。  
  
-   **ES_NOHIDESEL**通常は、エディット コントロールでは、制御が入力フォーカスを失い、コントロールが入力フォーカスを受け取ると、選択を反転する場合に、選択範囲が非表示にします。 指定する**ES_NOHIDESEL**この既定のアクションを削除します。  
  
-   **ES_NUMBER**エディット コントロールに入力する数字のみです。  
  
-   **ES_OEMCONVERT**エディット コントロールに入力したテキストは ANSI 文字セットから OEM 文字セットと ANSI 戻りますに変換します。 これにより、アプリケーションを呼び出す場合は適切な文字の変換、`AnsiToOem`エディット コントロールでの ANSI 文字列を OEM 文字に変換する Windows の機能です。 このスタイルは、ファイル名を格納している編集コントロールの方が適しています。  
  
-   **ES_PASSWORD**のすべての文字をアスタリスクが表示されます (**\***) エディット コントロールに入力されます。 アプリケーションで使用できる、`SetPasswordChar`表示される文字に変更します。  
  
-   **ES_READONLY**ユーザーが入力するか、エディット コントロールでテキストを編集できなくなります。  
  
-   **ES_RIGHT**単一行または複数行で右揃えのテキスト コントロールを編集します。  
  
-   **ES_UPPERCASE**エディット コントロールに入力されたと大文字をすべての文字に変換します。  
  
-   **ES_WANTRETURN**  ダイアログ ボックス内の複数行のエディット コントロールにテキストを入力するときに、ENTER キーを押したときに、キャリッジ リターンを挿入することを指定します。 このスタイルでは、いない場合は、ダイアログ ボックスの既定のプッシュ ボタンを押したときと同じ効果に ENTER キーを押します。 このスタイルには、エディット コントロールの単一行への影響がありません。  
  
## <a name="see-also"></a>関連項目  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)   
 [CEdit::Create](../../mfc/reference/cedit-class.md#create)   
 [コントロールのスタイルを編集します。](http://msdn.microsoft.com/library/windows/desktop/bb775464)


